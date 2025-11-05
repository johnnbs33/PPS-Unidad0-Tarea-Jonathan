# Operaciones con GitHub Actions.
1. [Creación de WorkFlow.](#conexion-con-github)
2. [Prepara los cambios y subida a GitHub](#subiendo-los-ficheros-a-github)
---

## Creación de Workflow.

- Dentro del directorio `.github/workflows` tendremos el fichero `CreacionDocumentacion.yml`, en él debemos de establecer el workflow que se disparará con cada **push**, para gestionar el despliegue de **MkDocs**.
- Editamos el fichero:
```bash
nano .github/workflows/CreacionDocumentacion.yml
```
- E incluiremos las siguientes líneas.
```yaml
# CreacionDocumentacion.yml

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
    
    # Paso 1: Obtención del código fuente
    - name: Checkout Repo
      uses: actions/checkout@v3

    # Paso 2: Configuración de Python
    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.x'

    # Paso 3: Instalar dependencias
    - name: Install dependencies
      run: pip install mkdocs

    # Paso 4: Construir y desplegar la documentación
    - name: Deploy docs
      run: mkdocs gh-deploy --force
      env:

        GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}

# Fin del fichero CreacionDocumentacion.yml
```

- Pulsamos `Ctrl + O` para guardar los cambios y `Ctrl + X` para salir del editor **nano**.

---

## Subiendo los ficheros a GitHub.
- Una vez guardado el fichero, preparamos los cambios, realizamos un **commit** y lo subimos a **GitHub**.
```bash
git add .
git commit -m "Modificación de CreacionDocumentacion.yml"
git push
```

---
