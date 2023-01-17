FROM node:16-alpine as builder
USER node
RUN mkdir -p /app
 WORKDIR /app
# RUN mkdir -p /home/node/app
# WORKDIR /home/node/app
COPY --chown=node:node ./package.json ./
RUN npm install
COPY --chown=node:node ./ ./
RUN npm run build
#CMD ["npm","run", "start"]

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/default.conf
#COPY --from=builder /home/node/app/build /user/share/html
COPY --from=builder /app/build /usr/share/nginx/html