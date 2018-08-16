# my-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```
## Git Config

### Crear Hook en el Servidor
```
$ cd /var/repos/
$ mkdir my-app.git
$ cd my-app.git
$ git init --bare
$ cd hooks
$ touch post-receive
$ chmod +x post-receive
```
### Editar el archivo post-recive
```
#!/bin/bash
git --work-tree=/ruta/a/donde/quieres/que/tu/codigo/se/copie --git-dir=/var/repos/my-app.git checkout -f
cd /ruta/a/donde/quieres/que/tu/codigo/se/copie
# Borrar la imagen
docker rmi my-app
# Crear nueva imagen
docker build -t my-app:latest .
# Parar contenedor
docker stop my-app
# Borrar contenedor
docker rm my-app
# Arrancar contenedor
docker run --name my-app -p "3100:80" -d my-app:latest
# Limpiar fuente
rm -Rf /ruta/a/donde/quieres/que/tu/codigo/se/copie
```
### En Localhost
```
git remote add dev ssh://usuario@servidor/var/repos/my-app.git
```
### Cambio de branch en servidor
```
$ cd /var/repos/proyecto.git/
$ git symbolic-ref HEAD refs/heads/develop
```
### Subir cambios
$ git push dev develop