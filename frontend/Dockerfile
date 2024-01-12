FROM node:18.16.0-alpine 
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . . 

RUN addgroup -g 1001 -S nodejs && adduser -u 1001 -S nodejs -G nodejs
USER nodejs
EXPOSE 3000
CMD ["node", "app.js"]
