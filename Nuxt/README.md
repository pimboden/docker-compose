# docker-nuxt

> Nuxt using docker

## Build Setup

``` bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn run dev

# build for production and launch server
$ yarn run build
$ yarn start

# generate static project
$ yarn run generate
```

For detailed explanation on how things work, checkout [Nuxt.js docs](https://nuxtjs.org).


# Docker Commands

Build Image:

docker build -t docker-nuxt-app .

Docker start instance
docker run -it -p 5000:5000 docker-nuxt-app 