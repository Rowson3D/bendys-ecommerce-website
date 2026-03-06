FROM node:22-slim

WORKDIR /app

RUN npm install -g corepack@latest && corepack enable

COPY package.json pnpm-lock.yaml ./

RUN pnpm install --frozen-lockfile

COPY . .

RUN pnpm build

EXPOSE 9000

ENV NODE_ENV=production

CMD ["pnpm", "start"]
