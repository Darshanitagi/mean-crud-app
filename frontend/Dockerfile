# frontend/Dockerfile
# ----------------------------------------------------------------

# Stage 1: Build the Angular application
FROM node:18-alpine as build

WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy source code and run the production build
COPY . .
RUN npm run build -- --configuration=production

# Stage 2: Serve the application with Nginx
FROM nginx:alpine

# *** DEFINITIVE CORRECTION ***
# The correct path is taken from angular.json's "outputPath": "dist/angular-15-crud"
COPY --from=build /usr/src/app/dist/angular-15-crud /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]