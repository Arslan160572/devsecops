# Use official MySQL image as the base image
FROM mysql:latest

# Copy SQL script to initialize database
COPY initialize.sql /docker-entrypoint-initdb.d/

# Expose MySQL port
EXPOSE 3306
