# Use the official Odoo image as a base
FROM odoo:16.0

# Set the working directory inside the container
WORKDIR /opt/odoo/custom

# Copy the application code into the container
COPY . /opt/odoo/custom/

# Install Python dependencies if any (assuming requirements.txt is present)
RUN pip3 install --no-cache-dir -r /opt/odoo/custom/requirements.txt

# Copy custom addons to the container's addons directory
COPY ./addons /mnt/extra-addons

# Copy Odoo configuration file
COPY ./odoo.conf /etc/odoo/odoo.conf

# Expose the default Odoo port
EXPOSE 8069

# Set the default command to run Odoo
CMD ["odoo"]
