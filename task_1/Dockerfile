FROM node:alpine as basement
WORKDIR /base
COPY package*.json ./
RUN npm install
COPY ./ ./

FROM node:alpine
COPY --from=basement /base ./

EXPOSE 8800
CMD [ "npm", "start" ]
