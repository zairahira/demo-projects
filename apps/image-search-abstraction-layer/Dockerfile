FROM node:24-bookworm-slim

WORKDIR /app

RUN npm install --global pnpm@12.21.0

# Copy over all the files in the project directory to /app early
# for rollup bundling
COPY . . 

ENV PORT=3000
ENV MONGO_URI=${IMAGE_SEARCH_ABSTRACTION_LAYER_MONGO_URI}
ENV CSEID=${IMAGE_SEARCH_ABSTRACTION_LAYER_CSEID}
ENV APIKEY=${IMAGE_SEARCH_ABSTRACTION_LAYER_APIKEY}

RUN pnpm install --frozen-lockfile

CMD ["pnpm", "start"]
