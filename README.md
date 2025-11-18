# Guía Completa de Comandos Git y GitHub

## 📋 Configuración Inicial (Solo una vez)

```bash
# Configura tu nombre
git config --global user.name "Tu Nombre"


# Configura tu email
git config --global user.email "tuemail@ejemplo.com"


# Verifica la configuración
git config --list
```


---


## 🚀 Crear un Nuevo Repositorio Local


```bash
# Inicializa un repositorio en la carpeta actual
git init


# Agrega archivos al staging area
git add .


# Realiza tu primer commit
git commit -m "Primer commit"
```


---


## 🔗 Conectar con GitHub


```bash
# Conecta tu repositorio local con GitHub
git remote add origin https://github.com/tu-usuario/tu-repositorio.git


# Verifica la conexión
git remote -v


# Sube tus cambios a GitHub
git push -u origin main
```


**Nota:** Si tu rama principal se llama "master", usa `git push -u origin master`


---



## 📥 Clonar un Repositorio Existente


```bash
# Clona un repositorio de GitHub a tu computadora o entrar a un repositorio 
git clone https://github.com/usuario/repositorio.git
```


---


## 💼 Comandos Básicos Diarios


```bash
# Ver el estado de tus archivos
git status


# Agregar cambios
git add nombre-archivo.txt  # Un archivo específico
git add .                    # Todos los archivos


# Guardar cambios
git commit -m "Descripción del cambio"


# Subir cambios a GitHub
git push


# Descargar cambios de GitHub
git pull
```


---



## 🌿 Trabajar con Ramas


### Crear y Cambiar entre Ramas


```bash
# Ver todas las ramas
git branch


# Crear una nueva rama
git branch nombre-rama


# Cambiar a una rama
git checkout nombre-rama


# Crear y cambiar a una rama (en un solo comando)
git checkout -b nombre-rama


# Comando moderno para cambiar de rama
git switch nombre-rama


# Crear y cambiar con git switch
git switch -c nombre-rama
```


### Flujo de Trabajo Completo en tu Rama


```bash
# 1. Crear y cambiar a tu rama de trabajo
git checkout -b feature/mi-nueva-funcionalidad


# 2. Trabajar en tus archivos...


# 3. Ver qué archivos cambiaron
git status


# 4. Agregar los cambios
git add .


# 5. Hacer commit de los cambios
git commit -m "Descripción de lo que hiciste"


# 6. Subir tu rama a GitHub
git push -u origin feature/mi-nueva-funcionalidad


# 7. Commits adicionales en la misma rama
git add .
git commit -m "Más cambios"
git push  # Ya no necesitas -u origin nombre-rama
```


---



## 🔀 Fusionar Ramas


### Fusionar tu Rama con main/master


```bash
# 1. Cambiar a la rama principal
git checkout main


# 2. Actualizar la rama principal
git pull origin main


# 3. Fusionar tu rama de trabajo
git merge feature/mi-nueva-funcionalidad


# 4. Subir los cambios fusionados
git push origin main
```


### Mantener tu Rama Actualizada con main


```bash
# Estando en tu rama de trabajo
git checkout feature/mi-nueva-funcionalidad


# Traer los últimos cambios de main a tu rama
git merge main


# O usar rebase (reorganiza los commits)
git rebase main
```


---



## 🗑️ Eliminar Ramas


```bash
# Eliminar rama local
git branch -d nombre-rama


# Forzar eliminación si no está fusionada
git branch -D nombre-rama


# Eliminar rama remota en GitHub
git push origin --delete nombre-rama
```


---




## 🔧 Comandos Útiles Adicionales


```bash
# Ver todas las ramas (locales y remotas)
git branch -a


# Ver la rama actual
git branch --show-current


# Renombrar una rama
git branch -m nuevo-nombre


# Ver el historial de commits
git log --oneline --graph --all


# Ver cambios no guardados
git diff


# Ver cambios en staging
git diff --staged


# Deshacer cambios en un archivo
git checkout -- nombre-archivo.txt


# Quitar archivo del staging area
git reset nombre-archivo.txt


# Volver al commit anterior (mantiene cambios)
git reset --soft HEAD~1


# Ver información remota
git remote show origin
```


---





## 📝 Ejemplo de Flujo Completo


```bash
# 1. Actualizar main
git checkout main
git pull


# 2. Crear rama para nueva funcionalidad
git checkout -b feature/agregar-login


# 3. Hacer cambios y commits
git add .
git commit -m "Agregado formulario de login"


# 4. Subir la rama a GitHub
git push -u origin feature/agregar-login


# 5. Cuando termines, volver a main y fusionar
git checkout main
git pull
git merge feature/agregar-login
git push


# 6. Eliminar la rama ya fusionada
git branch -d feature/agregar-login
git push origin --delete feature/agregar-login
```


---



## 🆘 Comandos de Emergencia


```bash
# Descartar TODOS los cambios locales
git reset --hard HEAD


# Guardar cambios temporalmente (sin commit)
git stash


# Recuperar cambios guardados
git stash p
# Ver lista de stashes
git stash list


# Deshacer el último commit (pero mantener cambios)
git reset --soft HEAD~1


# Deshacer el último commit (y descartar cambios)
git reset --hard HEAD~1


# Ver quién modificó cada línea de un archivo
git blame nombre-archivo.txt
```


### Antes de Hacer Push
```bash
# Siempre verifica qué vas a subir
git status
git log --oneline -5
```
---




### Nombres de Ramas Recomendados
- `feature/nombre` - Para nuevas funcionalidades
- `bugfix/nombre` - Para corrección de errores
- `hotfix/nombre` - Para correcciones urgentes
- `docs/nombre` - Para documentación
- `test/nombre` - Para pruebas


### Mensajes de Commit
- Usa presente: "Agrega función" en lugar de "Agregada función"
- Sé descriptivo pero conciso
- Primera letra mayúscula
- Ejemplos:
  - "Agrega validación de formulario"
  - "Corrige error en el login"
  - "Actualiza documentación de API"


---



