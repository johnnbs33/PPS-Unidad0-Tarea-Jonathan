# Docker.
1. [Preparación del del repositorio.](#Preparación-del-repositorio)
2. [Creación del entorno Docker.](#Creación-del-entorno-Docker)
3. [Iniciando el entorno](#Inicializando-el-entorno)
---

## Preparación del repositorio.
- Cambiaremos a la rama **gh-pages** en local, a partir de la remota de **GitHub**.
```bash
git checkout gh-pages
```
> Una vez terminado todo el ejercicio de Docker, si quisieramos volver a la rama **main**, ejeecutariamos el comando siguiente:
```bash
git checkout main
```
- Si realizamos algun cambio en alguna de las páginas **MarkDown**, tendremos que traer los ultimos cambios de la rama **gh-pages**, que habran sido generados por `MkDocs`.
```bash
git pull
```

---

## Creación del entorno Docker.
- Orquestaremos un servicio web con un único archivo **docker-compose.yml**.
- Nos situaremos fuera del directorio del repositorio, crearemos un directorio llamado **PPS-Unidad0-Tarea-Jonathan-Docker**.
```bash
mkdir PPS-Unidad0-Tarea-Jonathan-Docker
```
- Situados dentro de él, crearemos el fichero **docker-compose.yml**.
```bash
nano docker-compose.yml
```
- Añadimos el siguiente contenido.
```yaml
services:
  web:
    image: nginx:stable
    container_name: PPSUnidad0-Tarea_Jonathan
    ports:
      - "8085:80"
    volumes:
      - /home/ppsjonathan/Documentos/PPS/PPS-Unidad0-Tarea-Jonathan:/usr/share/nginx/html
```

- Pulsamos `Ctrl + O` para guardar los cambios y `Ctrl + X` para salir del editor **nano**.

- Resumen de las operaciones del fichero Compose:
  - El servicio se llamara **web**.
  - Se creará a partir de la imagen de **nginx estable**.
  - El nombre del contenedor será **PPSUnidad0-Tarea_Jonathan**.
  - Mapearemos el puerto **8085** del host al **80** del servidor web nginx.
  - Definimos **bind mount** del directorio que aloja los ficheros estáticos del repositorio, hacia el directorio donde nginx busca los archivos web.
 
---

## Inicializando el entorno.
- A contiunación, **crearemos** y **levantaremos** los servicios definidos en el archivo **docker-compose.yml** en modo *detached* (segundo plano).
```bash
docker compose up -d
```
*En la terminal, observaremos como se levantan los servicios, haciendo **pull** de las imagenes si no estuvieran ya.*
- Comprobamos que todo esta funcionando, mediante el siguiente comando:
```bash
docker compose ps
```
*La salida nos mostrará los servicios en ejecución, en este caso es solamente uno, y podremos observar el nombre, estado, puertos, entre otros datos.*
- También podemos realizar un inspect del contenedor para visualizar toda la información del mismo.
```bash
docker inspect PPSUnidad0-Tarea_Jonathan
```

---
