FROM nginx:1.19.1


RUN rm -f /etc/nginx/conf.d/default.conf && \
  mkdir -p /var/www/rails/rails-with-nginx/public

COPY ./config/rails-with-nginx.conf /etc/nginx/conf.d


CMD ["nginx", "-g", "daemon off;"] 