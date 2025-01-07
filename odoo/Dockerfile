# Use an official Python runtime as the base image
FROM python:3.10.12

# Set environment variables
ENV LANG C.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LC_ALL C.UTF-8

# Install system dependencies
RUN apt-get update 

# Set the working directory inside the container
WORKDIR /mnt/odoo

# Copy the current directory contents into the container
COPY . /mnt/odoo

# Install Python dependencies from requirements.txt
RUN pip install --upgrade pip
RUN pip install -r /mnt/odoo/requirements.txt

# Expose the necessary port
EXPOSE 8069

# Command to run Odoo (replace with your specific command if needed)
CMD ["python", "/mnt/odoo/odoo-bin", "-c", "/mnt/odoo/debian/odoo.conf"]
