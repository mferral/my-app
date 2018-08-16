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

### Crear Hook de Github en el Servidor
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
```
### 
