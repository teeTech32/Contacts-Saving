FROM node:latest as build
# set working directory
WORKDIR /code

ENV PATH /app/node_modules/.bin:$PATH
# install app dependencies
COPY package.json /code/package.json
COPY package-lock.json /code/package-lock.json
# Silent clean install of npm
RUN npm ci --silent
# Build productiond
RUN npm install -g serve
# add app
COPY ./ /code

CMD ["npm", "start"]
