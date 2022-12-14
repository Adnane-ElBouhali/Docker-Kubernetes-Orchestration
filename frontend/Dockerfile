# This is a multi-stage build docker file

# Stage 1 (build environment)
FROM node:10-alpine as build
WORKDIR /frontend
COPY ./package.json /frontend//package.json
COPY ./package-lock.json /frontend//package-lock.json
RUN npm ci
RUN npm install react-scripts -g
COPY . /frontend
RUN npm run build

# Stage 2 (production environment)
FROM nginx:1.16.0-alpine
COPY --from=build /frontend/build /usr/share/nginx/html
# COPY ./nginx/nginx.conf /etc/nginx/conf.d/default.conf   #since we deleted this file, this line is useless
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
