# Docusaurus documentation app Dockerfile
# Place this file in your Docusaurus project root (e.g., docs-site/)

FROM node:18-alpine3.19 AS builder
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
