# => Build container
FROM node:10 as build

WORKDIR /frontend

COPY package.json /frontend/package.json

RUN npm install

RUN npm install react-scripts -g

COPY . /frontend

RUN npm run build

# => Run container
FROM nginx:1.16.0

COPY --from=build /frontend/build /usr/share/nginx/html

COPY --from=build /app/dist /frontend/static

RUN rm /etc/nginx/conf.d/default.conf

EXPOSE 80

# Start Nginx server
CMD ["/bin/bash", "-c", "nginx -g \"daemon off;\""]