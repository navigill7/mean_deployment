FROM node:18-alpine AS build

WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build --prod

# Stage 2: keep only built files, no server
FROM alpine:3.18
WORKDIR /app
COPY --from=build /app/dist/angular-15-crud ./dist
