FROM node:10-alpine

WORKDIR /usr/src/myapp

ENV NODE_ENV production

COPY package*.json ./

RUN npm ci 

COPY . /usr/src/myapp

RUN npm install --dev && npm run build

CMD [ "npm", "start" ]
