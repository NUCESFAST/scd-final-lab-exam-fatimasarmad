# Use a Node.js base image suitable for back-end development
# SAME BACKEND DOCKER FILES FOR ALL EPISODES 
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the back-end source code to the working directory
COPY . .

# Expose the port your app runs on (adjust as needed)
EXPOSE 3000

# Command to run your back-end app (replace 'start' with your actual start command)
CMD ["npm", "start"]
