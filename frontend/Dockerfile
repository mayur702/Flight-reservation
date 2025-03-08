FROM node:18 as build

# Set working directory
WORKDIR /app

# Copy frontend files
COPY . .

# Install dependencies and build frontend
RUN npm install && npm run build

# Serve frontend with Apache
FROM httpd:2.4

# Copy built files to Apache web directory
COPY --from=build /app/dist/ /usr/local/apache2/htdocs/

# Health check for frontend
HEALTHCHECK --interval=10s --timeout=5s --retries=5 CMD curl --fail http://18.117.145.160:80 || exit 1

EXPOSE 80

