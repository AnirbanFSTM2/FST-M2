# Bulid Phase
FROM node:18-alpine as builder  
WORKDIR /usr/app
COPY ./package.json ./
RUN npm install
COPY . .

# Run Phase
FROM node:18-alpine
WORKDIR /usr/app
COPY ./package.json ./
RUN npm install
COPY --from=builder /usr/app/dist ./
CMD ["npm", "server.js"]