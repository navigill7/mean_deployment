# Stage 1: Build Angular app
FROM node:18-alpine AS build

WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build --prod

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Remove default Nginx HTML
RUN rm -rf /usr/share/nginx/html/*

# Copy Angular build output
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

# Copy custom Nginx config
COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
