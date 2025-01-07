# Use an official Python runtime as the base image
FROM python:3.10.12

# Set environment variables
ENV LANG C.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LC_ALL C.UTF-8

# Install system dependencies
RUN rm -rf /var/lib/apt/lists/* /var/cache/apt/archives/lock /var/lib/dpkg/lock*

# Ensure the package list is updated and force repositories to be refreshed
RUN echo "deb http://archive.ubuntu.com/ubuntu focal main universe" > /etc/apt/sources.list 
RUN apt-get update


# Set the working directory inside the container
WORKDIR /mnt/odoo

# Copy the current directory contents into the container (including requirements.txt)
COPY . /mnt/odoo

# List the contents of /mnt/odoo to verify the structure
RUN ls -la /mnt/odoo

# Install Python dependencies from the correct path (inside the 'odoo' directory)
RUN pip install --upgrade pip
RUN pip install -r /mnt/odoo/requirements.txt --verbose

# Expose the necessary port
EXPOSE 8069

# Command to run Odoo (replace with your specific command if needed)
CMD ["python", "/mnt/odoo/odoo/odoo-bin", "-c", "/mnt/odoo/odoo/debian/odoo.conf"]
