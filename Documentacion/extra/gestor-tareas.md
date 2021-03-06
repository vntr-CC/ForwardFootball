# Opciones de Gestor de Tareas 馃摀

Las diferentes opciones contempladas haciendo uso del lenguaje de programaci贸n Julia son las siguientes:

## Travis CI

Seg煤n [Wikipedia](https://en.wikipedia.org/wiki/Travis_CI):
> Travis CI es un servicio de integraci贸n continua alojado que se utiliza para crear y probar proyectos de software alojados en GitHub y Bitbucket. Travis CI fue el primer servicio de CI que brind贸 servicios a proyectos de c贸digo abierto de forma gratuita y contin煤a haci茅ndolo.

En un servicio que da soporte de forma general a muchos lenguajes para realizar la funci贸n de gestionar las tareas de manera continua, probando la integridad del proyecto en cada commit realizado y ejecutando las diferentes ordenes establecias en un archivo `.travis.yml` que tiene la siguiente estructura:

```yml
language: julia
julia:
  - nightly
  - 1.0.6
  - 1.5.2
```
Para m谩s informaci贸n acerca de este servicio clique [aqu铆](https://www.travis-ci.com/).

## Appveyor

Seg煤n [Wikipedia](https://en.wikipedia.org/wiki/AppVeyor):
> AppVeyor es un servicio de integraci贸n continua alojado y distribuido que se utiliza para construir y probar proyectos alojados en GitHub y otros servicios de alojamiento de c贸digo fuente en una m谩quina virtual Microsoft Windows, as铆 como m谩quinas virtuales Ubuntu Linux.

Es un servicio similar a Travis CI pero con mayor soporte en la comprobaci贸n de la integridad del proyecto en sistemas Windows. Para ello se ha de crear un archivo `.appveyor.yml` que tiene la siguiente estructura:

```yml
environment:
  matrix:
  - julia_version: 0.7
  - julia_version: 1
  - julia_version: nightly

platform:
  - x86 # 32-bit
  - x64 # 64-bit
```
Para m谩s informaci贸n acerca de este servicio clique [aqu铆](https://www.appveyor.com/).

***
**Aclaraci贸n**

La versi贸n `nightly` hace referencia a la 煤ltima versi贸n de [Julia](https://github.com/JuliaLang/julia).

***
