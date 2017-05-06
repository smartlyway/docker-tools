# Angular-CLI WorkSpace

Este espacio de trabajo esta pensado para ejecutar los comandos de node-js y angular-cli dentro de docker y que los ficheros generados sean visibles desde el exterior.

## ¿Cómo se utiliza?
La estructura del proyecto es la siguiente:

- Carptea de del proyecto angular. [workspace]
  - Docker/
  - README.md

Para iniciar un proyecto de angular:

1. Situarse dentro de la carpeta Docker y ejecuutar:
```
docker-compose build
```

2. Levantar la máquina de docker
```
docker-compose up -d
```

3. Entrar en la máquina de docker
```
docker-compose exec workspace bash
```

4. Dentro de la máquina de docker ejecutar:
```
ng new <nombre del proyecto>
```
Los ficheros del proyecto apareceran en la carpeta root/[nombre del proyecto]

5. Para lanzar el servidor dentro de la máquina ejecutar
```
ng serve --host 0.0.0.0
```
