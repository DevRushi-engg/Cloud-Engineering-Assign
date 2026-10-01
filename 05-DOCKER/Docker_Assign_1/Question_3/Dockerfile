FROM node:20-alpine

RUN apk add --no-cache curl

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

USER node

EXPOSE 3000

HEALTHCHECK --interval=30s --timeout=3s \
    CMD curl -f http://localhost:3000/ || exit 1

CMD ["node", "server.js"]
