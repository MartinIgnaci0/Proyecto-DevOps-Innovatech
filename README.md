# Proyecto Innovatech - Sistema de Gestion de Ventas y Despachos

Este repositorio contiene la arquitectura de microservicios y el flujo de integracion continua para el sistema Innovatech. La solucion esta diseñada bajo principios DevOps, utilizando contenedores para asegurar la paridad entre los entornos de desarrollo y produccion.

## Descripcion del Proyecto
Innovatech es una plataforma distribuida que permite la gestion de operaciones comerciales. El sistema ha sido desagregado en microservicios independientes para garantizar escalabilidad y facilitar el mantenimiento de cada componente.

## Arquitectura de Servicios
La infraestructura se basa en una red virtual de Docker que comunica los siguientes componentes:

1. **Frontend**: Interfaz de usuario servida mediante un servidor Nginx, configurada para interactuar con las APIs de backend.
2. **Backend Ventas**: Servicio encargado del procesamiento de transacciones comerciales y logica de negocio de ventas.
3. **Backend Despachos**: Servicio responsable de la gestion logistica y seguimiento de envios.
4. **Base de Datos**: Instancia de MySQL para la persistencia centralizada de la informacion del ecosistema.

## Requisitos del Entorno
Para la ejecucion de este proyecto es necesario contar con:
* Docker Engine / Docker Desktop
* Docker Compose
* Git

## Instrucciones de Despliegue Local

1. Clonar el repositorio:
   git clone https://github.com/MartinIgnaci0/Proyecto-DevOps-Innovatech.git

2. Iniciar la orquestacion de contenedores:
   docker-compose up --build -d

3. Verificacion:
   Acceder a traves del navegador a: http://localhost

## Integracion Continua (CI)
El proyecto implementa un pipeline de automatizacion mediante GitHub Actions, definido en el directorio .github/workflows/. Este flujo se activa ante cada actualizacion en la rama principal (main) y realiza las siguientes tareas:
* Verificacion de integridad del codigo fuente.
* Validacion de construccion (Build) de las imagenes de Docker.
* Reporte de estado de la integracion para asegurar la estabilidad del repositorio.

## Mantenimiento y Troubleshooting
En caso de fallos en la conectividad inicial de los backends, validar que el contenedor de la base de datos haya completado su proceso de inicializacion antes del arranque de los servicios dependientes. Se recomienda el uso de politicas de reinicio (restart policies) en el archivo de orquestacion.

## Autores
* Martin Pizarro
* Lucas Tapia
* Alonzo Vergara
