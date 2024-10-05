# 1. Building the Svelte app
FROM node:20.14-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install --only=production

COPY . .
RUN npm run build

# 2. Deploying the app with Nginx and Certbot
FROM jonasal/nginx-certbot:5.4.0-alpine

# Remove default Nginx content
RUN rm -rf /var/www/*

# Copy the built app to the web root
COPY --from=builder /app/build /var/www/html

# Copy your custom Nginx configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Start the initialization script
ENTRYPOINT ["./init.sh"]
