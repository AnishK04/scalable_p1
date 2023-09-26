# build stage
FROM node:16.3.0-alpine as build-stage
WORKDIR /app
COPY ./codebase/scalable-ums-frontend /app
RUN yarn install
RUN yarn build

# production stage
FROM nginx:stable-alpine as production-stage
COPY --from=build-stage /app/dist /usr/share/nginx/html
