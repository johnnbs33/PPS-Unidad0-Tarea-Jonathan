# Conclusiones.
* En la puesta en marcha de los repositorios, hay que tener claro cuándo se trabaja en **local** o en **remoto**, así como la rama en la que se está trabajando en el momento.
* Al realizar un **push** de los cambios, es necesario haber hecho previamente un **commit** de los mismos.
* “La documentación generada mediante **Markdown** nos facilita visualizarla de manera **rápida** y **limpia**.
* Con **GitHUb Actions**, realizaremos **flujos de trabajo**, en respuesta a los **eventos** del repositorio.
* Con **MkDocs**, documentaremos de forma automática los ficheros .md a través de **GitHub Pages** de forma fácil, sin intervención manual.
* Con **Docker**, podremos levantar un servicio de forma **rápida** y **sencilla**, con multitud de opciones.

---

## Tareas realizadas en orden.
* Creación del **repositorio**.
  * Repositorio **local**.
  * Conexión con **GitHub**.
  * Repositorio **remoto** en GitHub.
* Creación del fichero **MkDocs**.
* Creación del **Workflow**.
  * Fichero `CreacionDocumentacion.yml` 
* Creación de todos los ficheros **Markdown** (`.md`).
  * Push al repositorio en GitHub.
* Configuración de **GitHub Pages**.
* Despliegue de **Docker**.
  * Fichero `docker-compose.yml`
* Ultimas modificaciones y ajustes de los ficheros Markdown.   

---

## Resumen rápido de los principales ficheros.


| Fichero                     | Cometido                            |
| --------------------------- | ----------------------------------- |
| `CreacionDocumentacion.yml` | Establecer el workflow              |
| `mkdocs.yml`                | Configuración  de MkDocs            |
| `docker-compose.yml`        | Orquestación de contenedores Docker |

---
