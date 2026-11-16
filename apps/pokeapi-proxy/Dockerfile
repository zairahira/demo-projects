FROM node:24-bookworm-slim

WORKDIR /app

RUN npm install --global pnpm@12.21.0

# Copy over all the files in the project directory to /app early
# for rollup bundling
COPY . . 

ENV PORT=3000
ENV CACHE_TTL_HOURS=${POKEAPI_PROXY_CACHE_TTL_HOURS}

RUN pnpm install --frozen-lockfile

CMD ["pnpm", "start"]
