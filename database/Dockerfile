FROM mysql:8.0

# Set environment variables
ENV MYSQL_DATABASE=flightdb \
    MYSQL_USER=admin \
    MYSQL_PASSWORD=admin123 \
    MYSQL_ROOT_PASSWORD=admin123

# Copy SQL file to initialize database
COPY sql.txt /docker-entrypoint-initdb.d/

# Health check for database container
HEALTHCHECK --interval=10s --timeout=5s --retries=5 CMD mysqladmin ping -h localhost -u root -padmin123 || exit 1

EXPOSE 3306

