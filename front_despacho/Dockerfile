# Stage 1: Build con Node
FROM node:18 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Servidor Nginx para el Front
FROM nginx:alpine
# Usamos /dist que es lo que genera Vite/proyectos modernos
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]