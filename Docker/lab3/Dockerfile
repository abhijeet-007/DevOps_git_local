FROM node:18-alpine AS builder
WORKDIR /apps
COPY package.json .
RUN npm install --production

FROM node:18-alpine
WORKDIR /apps
COPY --from=builder /apps/node_modules ./node_modules
COPY index.html .
EXPOSE 8080
CMD ["npx", "http-server", "-p", "8080"]