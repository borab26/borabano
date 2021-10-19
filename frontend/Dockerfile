FROM node:latest AS build
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:latest AS prod-stage
COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /usr/src/app/dist/quiz-frontend /usr/share/nginx/html
EXPOSE 80
#CMD ["nginx","-g","deamon off;"]
