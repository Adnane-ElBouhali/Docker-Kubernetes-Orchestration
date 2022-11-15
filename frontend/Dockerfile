# This is a multi-stage docker file (multi-stage build)

# Stage 1 (build environment)
FROM node:12-alpine as build
WORKDIR /app
COPY ./package.json /app/package.json
COPY ./package-lock.json /app/package-lock.json
RUN npm install 
COPY . .
RUN npm run build

# Stage 2 (production environment)
FROM nginx:stable-alpine
COPY --from=build /app/build /usr/share/nginx/html
COPY ./nginx/nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]