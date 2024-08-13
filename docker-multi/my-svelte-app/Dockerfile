# Etapa 1: Construcción
FROM node:18 AS build

# Establece el directorio de trabajo en /app
WORKDIR /app

# Copia los archivos necesarios para instalar las dependencias
COPY package.json package-lock.json ./

# Instala las dependencias de la aplicación
RUN npm install

# Copia todo el código de la aplicación al contenedor
COPY . .

# Genera la build de producción
RUN npm run build

# Etapa 2: Servidor Nginx para servir la aplicación
FROM nginx:1.23-alpine

# Copia los archivos construidos desde la etapa anterior al contenedor de Nginx
COPY --from=build /app/static /usr/share/nginx/html

# Expone el puerto 80 para acceso a la aplicación
EXPOSE 80

# Comando por defecto para correr Nginx
CMD ["nginx", "-g", "daemon off;"]
