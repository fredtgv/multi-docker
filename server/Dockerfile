#FROM node:14.14.0-alpine
FROM node:16-alpine
#USER node
#RUN mkdir -p /app
WORKDIR /app
# RUN mkdir -p /home/node/app
# WORKDIR /home/node/app
COPY ./package.json ./
RUN npm install
COPY ./ ./
CMD ["npm","run","start"]
