# Stage 1
FROM node:14-alpine as build-stage

WORKDIR /usr/frontend-ptech
COPY stackFE/ .

RUN npm install

RUN npm run build

# Stage 2
FROM nginx:1.23

COPY --from=build-stage /usr/frontend-ptech/build /usr/share/nginx/html

CMD nginx -g 'daemon off;'