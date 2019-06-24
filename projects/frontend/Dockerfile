# Specify a Base Image
FROM node:alpine as builder

WORKDIR '/app'

# Install some dependencies
COPY ./package.json ./
RUN npm install
COPY ./ ./

# Default command
CMD ["npm", "run", "build"]

FROM nginx
COPY --from=builder ./app/build /usr/share/nginx/html