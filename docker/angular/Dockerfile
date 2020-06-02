FROM node:12.11.1-buster AS builder
RUN mkdir /myapp
ADD . /myapp
WORKDIR /myapp
RUN yarn && yarn build--verbose

FROM nginx:1.17.0 AS prod
RUN rm -rf /usr/share/nginx/html/*  /etc/nginx/nginx.conf
COPY ./nginx/ /etc/nginx/
COPY --from=builder /uness/dist/myapp /usr/share/nginx/html
ENTRYPOINT [ "bash", "/etc/nginx/nginx.sh" ]