FROM binwiederhier/ntfy

# Install Nginx using the Alpine package manager
RUN apk update && apk add nginx

# Remove the default Nginx configuration
RUN rm /etc/nginx/nginx.conf

# Copy your Nginx configuration
COPY nginx.conf /etc/nginx/sites-available/ntfy
RUN ln -s /etc/nginx/sites-available/ntfy /etc/nginx/sites-enabled

# Copy ntfy configuration
COPY server.yml /etc/ntfy/server.yml

# Expose Nginx ports
EXPOSE 80
EXPOSE 443

# Start Nginx and ntfy
CMD service nginx start && ntfy serve
