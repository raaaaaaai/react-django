# Use an official Python image as the base image
FROM python:3.9

# Set environment variables for Python to run in unbuffered mode (recommended for Docker)
ENV PYTHONUNBUFFERED 1

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file to the container
COPY requirements.txt /app/

# Install dependencies
RUN pip install -r requirements.txt

# Copy the rest of the application code to the container
COPY . /app/

# Expose the port on which the Django app will run (default is 8000)
EXPOSE 8000

# Start the Django development server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
