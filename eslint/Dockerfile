FROM node:8.11-alpine

MAINTAINER doanhpv

RUN npm i -g eslint eslint-plugin-react babel-eslint

WORKDIR /var/www/laravel

ENTRYPOINT ["eslint"]
CMD ["--version"]
