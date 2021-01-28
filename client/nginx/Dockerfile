FROM node:alpine as bulder
WORKDIR 'app'
COPY ./package.json ./
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=bulder /app/build /usr/shere/nginx/html
