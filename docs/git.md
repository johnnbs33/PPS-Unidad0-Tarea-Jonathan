# Operaciones con Git
1. [Conexión con GitHub.](#Conexión-con-GitHub)
2. [Preparacion del proyecto y creación del repositorio local.](#Preparación-del-proyecto)
3. [Fichero mkdocs.yml.](#Fichero-mkdocs)
4. [Subiendo el repositorio a GitHub.](#Subiendo-el-repositorio-a-GitHub)

---

## Conexión con GitHub.
>Todas las operaciones de creación del repositorio en GitHub se realizarán a través de la terminal.  

- En primer lugar, realizaremos una instalacion de las dependencias necesarias para trabajar con **git** y **GitHub**.
```bash
sudo apt update && sudo apt install git gh
```
- Realizamos una autenticación en **GitHub**.
```bash
gh auth login
```

---

## Preparación del proyecto.
- Crearemos un directorio de trabajo e incluimos el contenido inicial.
```bash
mkdir PPS-Unidad0-Tarea-Jonathan
```
- Inicializamos el repositorio y configuramos la rama principal en `main`.
```bash
git config --global init.defaultBranch main
git init
```

---

## Fichero mkdocs.
- Creamos un fichero llamado **mkdocs.yml**.
```bash
nano mkdocs.yml
```
- En el cual, incluiremos la siguientes líneas.
```yaml
# mkdocs.yml

# Inicializando fichero mkdocs.yml
site_name: Tarea Unidad 0 - RA5

# Estructura de navegación
nav:
  - Home: index.md
  - Git: guia_uso.md
  - GitHub Actions: gitActions.md
  - GitPages: gitPages.md
  - Docker: docker.md
  - Conclusiones: conclusiones.md

# Directorios
doc_dir: docs

# Fin del fichero makdocs.yml
```

- Pulsamos `Ctrl + O` para salir del editor nano.

---

## Subiendo el repositorio a GitHub.
- Creamos el primer **comit** con toda la estructura.
```bash
git add .
git commit -am "Inicializando repositorio"
git branch -M main
```
- A continuación, crearemos el repositorio en GitHub.
 

```bash 
gh repo create johnnbs33/PPS-Unidad0-Tarea-Jonathan --public --source=. --remote=origin --push
```


---
