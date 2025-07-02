FROM python:3.9-slim

# Install distutils (required by Django)
RUN apt-get update && apt-get install -y python3-distutils

# Set work directory
WORKDIR /app

# Copy requirements file and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy rest of the project files
COPY . .

# Expose port
EXPOSE 8000

# Run migration and then server at container startup
CMD ["sh", "-c", "python manage.py migrate && python manage.py runserver 0.0.0.0:8000"]
