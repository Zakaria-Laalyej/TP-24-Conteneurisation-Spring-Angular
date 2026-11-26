FROM node:14.15.0-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
RUN npm install --save-dev @types/node@14
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist/smart-home /usr/share/nginx/html
