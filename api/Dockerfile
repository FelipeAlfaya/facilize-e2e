FROM node:20-alpine

WORKDIR /app

# Instala dependências para o Prisma
RUN apk add --no-cache openssl

# Instala Prisma CLI globalmente
RUN npm install -g prisma

# Copia os arquivos do BE-Facilize para o container
COPY ./BE-Facilize/package*.json ./
COPY ./BE-Facilize/prisma ./prisma

# Instala dependências
RUN npm install

# Gera o cliente Prisma
RUN npx prisma generate

# Copia o resto da aplicação
COPY ./BE-Facilize .

# Build da aplicação (se necessário)
RUN npm run build

EXPOSE 3000
CMD ["npm", "run", "start:prod"]