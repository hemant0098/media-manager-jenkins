FROM node:18-slim AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

FROM gcr.io/distroless/nodejs:18
WORKDIR /app
COPY --from=build /app ./
EXPOSE 3000
CMD ["server.js"]
