#!/bin/bash

# Stop execution if an error occurs
set -e

echo "🚀 Starting Deployment..."

# 1. Create the Docker Network
# Check if network exists, if not create it
docker network inspect mongo-network >/dev/null 2>&1 || \
    docker network create mongo-network

# 2. Start MongoDB
echo "🐳 Starting MongoDB Container..."
docker run -d \
  -p 27017:27017 \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=password \
  --name mongodb \
  --net mongo-network \
  mongo

# 3. Start Mongo Express (UI)
echo "🐳 Starting Mongo Express Container..."
docker run -d \
  -p 8081:8081 \
  -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
  -e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
  -e ME_CONFIG_MONGODB_SERVER=mongodb \
  --name mongo-express \
  --net mongo-network \
  mongo-express

echo "✅ Setup complete!"
echo "➡️  Mongo Express UI: http://localhost:8081"