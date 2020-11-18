# stage 1: compile the app
FROM node:latest as node
WORKDIR /app

COPY . .
RUN npm install
RUN npm run build --prod

# stage 2: serve the app
FROM nginx:alpine
COPY --from=node /app/dist/AngularApp /usr/share/nginx/html
