# Stage 1: Build Angular app
FROM node:18-alpine AS build

WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build --prod

# Stage 2: Serve Angular with http-server
FROM node:18-alpine

WORKDIR /app
COPY --from=build /app/dist/angular-15-crud ./

# Install http-server globally
RUN npm install -g http-server

# Expose port 4200
EXPOSE 4200

# Start the Angular app
CMD ["http-server", "-p", "4200", "-c-1"]
