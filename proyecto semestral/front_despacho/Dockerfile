# Etapa 1: Construcción de los archivos estáticos
FROM node:20-alpine AS build
WORKDIR /app
# Copiamos los archivos de dependencias
COPY package*.json ./
RUN npm install
# Copiamos el resto del código y compilamos el sitio
COPY . .
RUN npm run build

# Etapa 2: Servidor de producción con Nginx
FROM nginx:alpine
# Copiamos la carpeta 'dist' generada por Vite hacia la ruta de Nginx
COPY --from=build /app/dist /usr/share/nginx/html
# Exponemos el puerto estándar HTTP
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]