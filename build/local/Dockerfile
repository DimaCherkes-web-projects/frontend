FROM node:18-alpine

WORKDIR /app

# Install curl
RUN apk add curl

# Copy the package.json and install the dependencies
COPY package.json .
RUN npm install

# Copy the rest of the files
COPY . .

# Start the app
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0", "--port", "80"]