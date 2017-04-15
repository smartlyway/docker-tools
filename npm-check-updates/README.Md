## NPM Check Updates
Aplicación que actualiza las dependencias de un proyecto javascript.

Modo de uso:

1. Compilar la imagen:

```
docker-compose build
```

2. Utilizar la imagen. 

```
docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) smartlyway/npm-check-updates npm-check-updates
```

Dado que el comando anterior es demasiado largo es recomandable crear un alias. Para ello hay que ir al fichero
`~/.bashrc` y agrear al final la siguiente linea:

```
alias dock-npm-check='docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) smartlyway/npm-check-updates npm-check-updates'
alias dock-npm='docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) smartlyway/npm-check-updates npm'
``` 

Gracias a esto ahora podremos usar el paquete así:

```
dock-npm-check <argumentos>  // Para actualizar dependencias
dock-npm <argumentos>        // Para utilizar NPM
```
