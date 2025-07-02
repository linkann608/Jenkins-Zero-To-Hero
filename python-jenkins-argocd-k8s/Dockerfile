FROM python:3.10

# Set work directory
WORKDIR /app

# Copy project files
COPY . .

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Run migrations
RUN python manage.py migrate

# Expose port
EXPOSE 8000

# Run server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
