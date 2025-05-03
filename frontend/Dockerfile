FROM node:20-alpine

WORKDIR /app

COPY /FE-Facilize/package.json /FE-Facilize/yarn.lock ./
RUN yarn install --production --frozen-lockfile

COPY /FE-Facilize/.next ./.next
COPY /FE-Facilize/public ./public
COPY /FE-Facilize/node_modules ./node_modules

EXPOSE 3001
CMD ["yarn", "start"]