# Use an existing Nginx image as the base
FROM nginx

LABEL version="1.0"
LABEL description="This is the base docker image for nginx."
LABEL maintainer = ["maaroufioussama2020@gmail.com"]

ARG NGINX_HTTP_PORT
ARG NGINX_HTTPS_PORT


# Your Nginx configuration
COPY nginx.conf  /etc/nginx/
COPY templates /etc/nginx/templates/
RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf



# Expose the default Nginx port
EXPOSE ${NGINX_HTTP_PORT}
EXPOSE ${NGINX_HTTPS_PORT}

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]