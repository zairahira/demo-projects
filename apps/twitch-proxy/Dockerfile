FROM node:24-bookworm-slim

WORKDIR /app

RUN npm install --global pnpm@12.21.0

# Copy over all the files in the project directory to /app early
# for rollup bundling
COPY . . 

ENV PORT=3000
ENV TWITCH_CLIENT_ID=${TWITCH_PROXY_TWITCH_CLIENT_ID}
ENV TWITCH_CLIENT_SECRET=${TWITCH_PROXY_TWITCH_CLIENT_SECRET}

RUN pnpm install --frozen-lockfile

CMD ["pnpm", "start"]
