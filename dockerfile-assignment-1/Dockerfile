# use this empty Dockerfile to build your assignment
# NOTE: The instructions are now in the README.md file in this directory.

# docker build -t testnode .
# docker container run --rm -p 80:3000 testnode
# docker tag testnode butchdean/testing-node
# docker push butchdean/testing-node
# docker image rm butchdean/testing-node
# docker system df
# docker system prune
# docker system prune -a

FROM node:6-alpine

EXPOSE 3000

RUN apk add --no-cache tini
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean --force

COPY . .

CMD [ "tini", "--", "node", "./bin/www" ]
