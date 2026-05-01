# Stage 1: Build the React app
FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

# Build the React app for production (creates /app/build folder)
RUN npm run build

# Stage 2: Serve it with a lightweight web server (nginx)
FROM nginx:alpine

# Copy the production build output to nginx's serve directory
COPY --from=build /app/build /usr/share/nginx/html

# nginx listens on port 80
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
