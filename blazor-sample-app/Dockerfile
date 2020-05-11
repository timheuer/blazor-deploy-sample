FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build-env
WORKDIR /app

COPY . ./
WORKDIR /app/
RUN dotnet publish -c Release

FROM nginx:alpine

WORKDIR /var/www/web
COPY --from=build-env /app/bin/Release/netstandard2.1/publish/wwwroot .
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80