#--------------------------------------Stage 1: Build Stage--------------------------------------------
  
FROM node:21 AS backend-builder

# Set the working directory to /app
WORKDIR /app

# Copy the code into current dir
COPY . .

RUN npm i

#--------------------------------------Stage 2: Final Stage----------------------------------------------------
FROM node:21-slim

#Setup the workdir
WORKDIR /app

# Copy the above stage as compressed
COPY --from=backend-builder /app .

COPY .env.sample .env

EXPOSE 5000

CMD ["npm","start"]
