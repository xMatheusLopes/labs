FROM node:14.13.1 as build
WORKDIR /app/src
COPY . .
RUN npm install
RUN npm install -g @angular/cli
RUN ng build

FROM nginx:1.19.3
COPY --from=build /app/src/dist/frontend /usr/share/nginx/html
EXPOSE 80