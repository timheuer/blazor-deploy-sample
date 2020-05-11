FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build-env
WORKDIR /app

COPY . ./
WORKDIR /app/
RUN dotnet publish -c Release

#FROM nginx:alpine

ARG NGINX_VERSION=1.18.0

FROM nginx:$NGINX_VERSION AS build
WORKDIR /src
RUN apt-get update && apt-get install -y git wget build-essential libssl-dev libpcre3-dev zlib1g-dev
ARG NGINX_VERSION
RUN CONFARGS=$(nginx -V 2>&1 | sed -n -e 's/^.*arguments: //p') \
    git clone https://github.com/google/ngx_brotli.git && \
    cd ngx_brotli && git submodule update --init && cd .. && \
    wget -nv http://nginx.org/download/nginx-$NGINX_VERSION.tar.gz -O - | tar -xz && \
    cd nginx-$NGINX_VERSION && \ 
    ./configure --with-compat $CONFARGS --add-dynamic-module=../ngx_brotli

WORKDIR nginx-$NGINX_VERSION
RUN	make modules

FROM nginx:$NGINX_VERSION as final

ARG NGINX_VERSION
COPY --from=build /src/nginx-$NGINX_VERSION/objs/*.so /etc/nginx/modules/

WORKDIR /var/www/web
COPY --from=build-env /app/bin/Release/netstandard2.1/publish/wwwroot .
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80