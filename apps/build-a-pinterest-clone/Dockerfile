FROM node:24-bookworm-slim

WORKDIR /app

RUN npm install --global pnpm@12.21.0

# Copy over all the files in the project directory to /app early
# for rollup bundling
COPY . . 

ENV PORT=3000
ENV GITHUB_KEY=${BUILD_A_PINTEREST_CLONE_GITHUB_KEY}
ENV GITHUB_SECRET=${BUILD_A_PINTEREST_CLONE_GITHUB_SECRET}
ENV DB_URI=${BUILD_A_PINTEREST_CLONE_DB_URI}
ENV APP_URL=${BUILD_A_PINTEREST_CLONE_APP_URL}

RUN pnpm install --frozen-lockfile

CMD ["pnpm", "start"]
