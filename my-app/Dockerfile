# Use a separate image for building
FROM node:14 as builder

WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Use a smaller image for production
FROM node:14-alpine

WORKDIR /app
COPY --from=builder /app/build /app
CMD ["npm", "start"]
EXPOSE 3000
