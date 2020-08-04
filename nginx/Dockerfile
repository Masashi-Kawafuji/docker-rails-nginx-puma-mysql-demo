FROM nginx:1.19.1


RUN rm -f /etc/nginx/conf.d/default.conf

COPY ./config/rails-with-nginx.conf /etc/nginx/conf.d


CMD ["nginx", "-g", "daemon off;"]