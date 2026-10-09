
FROM nginx:latest AS build

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY . /usr/share/nginx/html

FROM gcr.io/distroless/nginx:latest

COPY --from=build /etc/nginx /etc/nginx
COPY --from=build /usr/share/nginx/html /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
