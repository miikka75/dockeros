# FROM node:current-alpine AS builder
# WORKDIR /app
# COPY package.json ./
# RUN npm install
# COPY . .
# RUN npm run build

# Build react app locally and just serve it with Docker
FROM nginx:stable-alpine AS server
COPY ./etc/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf
COPY ./build/ /usr/share/nginx/html/

# If using a separate builder (above), copy files from there
# COPY --from=builder ./app/build /usr/share/nginx/html

