FROM node:18-alpine AS build

WORKDIR /app

# Install curl
RUN apk add --no-cache curl


# Install dependencies
COPY package.json .
COPY package-lock.json .
RUN npm install

# Copy the rest of the files
COPY . .

RUN npm run build

# Production image
FROM httpd:2.4-alpine

RUN apk add --no-cache curl

COPY --from=build /app/dist /usr/local/apache2/htdocs/

