#Tell Docker we want to use Node v10 installed in a alpine Linux image.
FROM node:10-alpine
RUN mkdir -p /nisarg/app/server
# The base node image sets a very verbose log level.
ENV NPM_CONFIG_LOGLEVEL warn

WORKDIR /nisarg/app/server
# Copy all local files into the image.
COPY ./steg-ws /nisarg/app/server

# Tell Docker about the port we'll run on.
EXPOSE 1234

# Install image preview generator tools
RUN apk add --no-cache file
RUN apk --update add imagemagick

# Install dependencies to run the application.
RUN npm install

# Set the command to start the node server.
CMD ["node","index.js", "1234"]
