#Multi-stage build
FROM node:20 AS build

WORKDIR /app

COPY package*.json ./

#npm instala dependencias y librerias React/Vite
RUN npm install

COPY . .
#compila el front para la produccion
RUN npm run build


#nginx sirve para navegar y publicar la app en el EC2
FROM nginx:alpine

COPY --from=build /app/dist /usr/share/nginx/html
#expone el puerto
EXPOSE 80