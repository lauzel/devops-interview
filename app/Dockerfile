FROM node:12-alpine

WORKDIR /usr/src/app

# only copy package json first, for better docker layers caching
# explaination : http://bitjudo.com/blog/2014/03/13/building-efficient-dockerfiles-node-dot-js/
COPY package*.json ./

RUN npm install

# add app source code.
COPY . .

EXPOSE 8000

ENTRYPOINT npm run start