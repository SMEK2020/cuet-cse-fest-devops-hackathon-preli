FROM node:18-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY src ./src

FROM node:18-alpine
WORKDIR /app
COPY --from=build /app .
EXPOSE 5921
CMD ["node", "src/index.js"]
