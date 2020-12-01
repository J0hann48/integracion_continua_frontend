FROM node:12.13.1 as node
WORKDIR /app
COPY . /app/
RUN pwd
RUN ls -R
USER root
RUN npm install
RUN npm run build -- --prod

# Stage 2
FROM nginx:alpine
COPY --from=node /app/dist/carritoComprasFrontend /usr/share/nginx/html
COPY ./nginx.conf /etc/nginx/conf.d/default.conf