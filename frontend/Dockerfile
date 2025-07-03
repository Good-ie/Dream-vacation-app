# Use Node to build the React app
FROM node:18

WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install react-scripts@latest

# ⬅️ Add this to ensure .env is included
COPY .env .   

# Now copy the rest of the app
COPY . .

# Build the app (this uses .env values at build time)
RUN npm run build

# Serve the build using a static server
RUN npm install -g serve

EXPOSE 3000

CMD ["serve", "-s", "build"]
