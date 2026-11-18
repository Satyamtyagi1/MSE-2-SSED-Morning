
# Stage 1: Production dependencies
FROM node:20-alpine

WORKDIR /app

ENV NODE_ENV=production

# Copy package configuration
COPY package*.json ./

# Install production dependencies
RUN npm install --omit=dev && npm cache clean --force

# Copy application source
COPY --chown=node:node src ./src

# Run as non-root user
USER node

EXPOSE 3000

CMD ["npm", "start"]
