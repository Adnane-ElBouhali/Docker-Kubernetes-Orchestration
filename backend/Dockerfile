FROM node:10-alpine
ENV NODE_ENV=production
WORKDIR /backend
COPY ["package.json", "package-lock.json*", "./"]
RUN npm ci --only=production
COPY . .
EXPOSE 5000
USER node
CMD ["node", "server.js"]