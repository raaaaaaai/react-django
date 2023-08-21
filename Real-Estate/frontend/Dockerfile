# Use the official Node.js image as the base image
FROM node:14

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

RUN . ~/.nvm/nvm.sh && \
    nvm install 10.24.1 && \
    nvm use 10.24.1 && \
    npm install -g npm@6.14.12

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package.json /app/
COPY package-lock.json /app/

# Install app dependencies
RUN npm install

# Copy the entire app to the container
COPY . .

# Build the React app for production
RUN npm run build

# Expose the port that your React app listens on
EXPOSE 3000

# Command to run your app when the container starts
CMD ["npm", "start"]
