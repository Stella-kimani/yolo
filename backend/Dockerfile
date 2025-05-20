FROM node:14  # Or your preferred version

WORKDIR /app

# First copy package files to leverage Docker cache
COPY package*.json ./

# Install ALL dependencies including devDependencies
RUN npm install --include=dev

# Now copy the rest of the files
COPY . .

# Build step if needed (for TypeScript, etc)
RUN npm run build

# Production dependencies only
RUN npm prune --production

EXPOSE 3000
CMD ["node", "server.js"]
