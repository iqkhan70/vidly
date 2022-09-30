#this is just a comment to test123
FROM node:14.16.0-alpine3.13

RUN addgroup app && adduser -S -G app app

RUN mkdir /app && chown app:app /app

USER app

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
ENV REACT_APP_API_URL=http://localhost:3001/api
RUN npm run build

EXPOSE 3000 

CMD ["npm", "start"]
