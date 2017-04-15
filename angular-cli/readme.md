# Angular CLI
Angular CLI es una aplicación que sirve para el desarrollo de aplicaciones angular.
Más información en: https://cli.angular.io/

Habitualmente para utilizarla hay que instalarla junto `node` utilizando `npm` tal y como se indica
en su pagina oficial. Para evitar tener que realizar estas instalaciones se puede utilizar la imagen
docker disponible en esta misma carpeta hay que realizar los siguientes pasos:

1. Compilar la imagen:

```
docker-compose build
```

2. Utilizar la imagen. La idea de esta imagen es poder utilizar `angular-cli` como si estubiera instalado
en nuestro sistema. Para cada vez que se quiera ejecutar un comando de `angular-cli`hay que ejecutar el
siguiente comando:

```
docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) -p 4200:4200 smartlyway/angular-cli ng <argumentos-angular>
```

Dado que el comando anterior es demasiado largo es recomandable crear un alias. Para ello hay que ir al fichero
`~/.bashrc` y agrear al final la siguiente linea:

```
alias dock-ng-serve='docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) -p 4200:4200 cgardev/angular-cli ng serve --host 0.0.0.0'
alias dock-ng='docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) cgardev/angular-cli ng'
alias dock-node='docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) cgardev/angular-cli node'
alias dock-npm='docker run -it --rm -w /src -v $(pwd):/src --user $(id -u) cgardev/angular-cli npm'
``` 

Gracias a esto ahora podremos usar angular cli desde docker de la siguiente manera:

```
dock-ng <argumentos>  // Para usar el CLI
dock-ng-serve         // Para lanzar el servidor http://0.0.0.0:4200
dock-npm              // Para utilizar NPM
```

### Limitaciones 
El puerto que debe utilizarse para hacer ejecutar la aplicacion angular debe ser el 4200. 
