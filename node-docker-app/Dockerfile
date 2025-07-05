FROM node:18 AS backend
WORKDIR /app
COPY backend ./backend
WORKDIR /app/backend
RUN npm install -g pm2 && npm install

FROM nginx:alpine AS frontend
COPY frontend /usr/share/nginx/html
COPY nginx/default.conf /etc/nginx/conf.d/default.conf

FROM node:18 AS final
WORKDIR /app
COPY --from=backend /app/backend /app/backend
COPY --from=frontend /usr/share/nginx/html /app/frontend
COPY nginx/default.conf /etc/nginx/conf.d/default.conf
WORKDIR /app/backend
CMD ["pm2-runtime", "index.js"]