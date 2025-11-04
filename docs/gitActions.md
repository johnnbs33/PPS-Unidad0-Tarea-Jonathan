# Operaciones con GitHub Actions.
1. [Creación de WorkFlow.](#Conexión-con-GitHub)
2. [Prepara los cambios y subida a GitHub](#Subiendo-los-ficheros-a-GitHub)
---

## Creación de WorkFlow.

- Dentro del directorio `.github/workflows` tendremos el fichero `CreacionDocumentacion.yml`, en el debemos de establecer el workflow que se disparará con cada **push**, para gestionar el despliegue de **MkDocs**.
- Editamos el fichero:
```bash
nano .github/workflows/CreacionDocumentacion.yml
```
- E incluiremos las siguientes líneas.
```yaml
# -----------------------------------------------------------
# Configuración del WorkFlow

name: Deploy MkDocs Tarea 0

on:
  push:
    branches:
      - main 

# Permisos

permissions:
  contents: write 
  pages: write
  id-token: write

# Definición del trabajo

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    
    # Paso 1: Obtencion del código fuente
    - name: Checkout Repo
      uses: actions/checkout@v3

    # Paso 2: Configuración de Python
    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.x'

    # Paso 3: Instalación de dependencias
    - name: Install dependencies
      run: pip install mkdocs

    # Paso 4: Construir y desplegar la documentación
    - name: Deploy docs
      run: mkdocs gh-deploy --force
      env:

        GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}

# -----------------------------------------------------------
```

- Pulsamos `Ctrl + O` para salir del editor nano.

---

## Subiendo los ficheros a GitHub.
- Una vez hemos guardado el fichero, preparamos el fichero, realizaremos un commit y posterior subida a GitHub.
```bash
git add .
git commit -m "Modificación de CreacionDocumentacion.yml"
git push
```

---
