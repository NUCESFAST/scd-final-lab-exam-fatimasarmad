
FROM node:14 as builder


WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the front-end source code to the working directory
COPY . .

# Build your front-end application (replace 'build' with your actual build command)
RUN npm run build

# Use a lightweight Node.js base image for serving the front-end
FROM nginx:alpine

# Copy the built files from the builder stage to nginx's web directory
COPY --from=builder /app/build /usr/share/nginx/html

# Expose the port your app runs on (typically not needed for front-end in Docker)
EXPOSE 80

# Command to start nginx (automatically starts when the container runs)
CMD ["nginx", "-g", "daemon off;"]
