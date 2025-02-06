# Flask App Dockerfile
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Copy the requirements and install dependencies
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the Flask app code
COPY . /app/

# Expose Flask app port
EXPOSE 5000

# Run the Flask app
CMD ["python", "app.py"]


 