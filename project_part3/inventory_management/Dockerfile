# Use an official Python runtime as a parent image
FROM python:3.10-slim

# Set the working directory in the container
WORKDIR /inventory_management

# Copy the requirements.txt file into the container
COPY requirements.txt .

# Install any dependencies specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the contents of the app folder into /inventory_management/app
COPY app/ /inventory_management/app

# Ensure that the app directory is treated as a package by adding __init__.py
RUN touch /inventory_management/app/__init__.py

# Expose port 80 to the world outside this container
EXPOSE 80

# Command to run the FastAPI app with Uvicorn
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "80"]