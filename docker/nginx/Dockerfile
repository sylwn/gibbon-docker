FROM debian:jessie
ARG DNS_NAME

MAINTAINER Laurent Breleur <laurent.breleur@gmail.com>

RUN apt-get update && apt-get install -y \
    nginx

COPY ./conf/nginx.conf /etc/nginx/
RUN echo ${DNS_NAME}
COPY ./conf/gibbon.conf /etc/nginx/sites-available/
RUN sed -i -e "s/__DNS__/${DNS_NAME}/g" /etc/nginx/sites-available/gibbon.conf

RUN ln -s /etc/nginx/sites-available/gibbon.conf /etc/nginx/sites-enabled/gibbon.conf
RUN rm /etc/nginx/sites-enabled/default

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
