FROM node:24-bookworm-slim

WORKDIR /app

RUN npm install --global pnpm@12.21.0

# Copy over all the files in the project directory to /app early
# for rollup bundling
COPY . . 

ENV PORT=3000
ENV GITHUB_KEY=${MANAGE_A_BOOK_TRADING_CLUB_GITHUB_KEY}
ENV GITHUB_SECRET=${MANAGE_A_BOOK_TRADING_CLUB_GITHUB_SECRET}
ENV MONGO_URI=${MANAGE_A_BOOK_TRADING_CLUB_MONGO_URI}
ENV APP_URL=${MANAGE_A_BOOK_TRADING_CLUB_APP_URL}

RUN pnpm install --frozen-lockfile

CMD ["pnpm", "start"]
