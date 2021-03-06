## Hito 2

Una vez conocido el proyecto a realizar (ver [Hito 0](./Hito-0.md)), y conocido los diferentes roles, los escenarios, las primeras historias de usuario y los primeros milestones (ver [Hito 1](./Hito-1.md)), es momento de definir el gestor de tareas que emplearemos e implementar los diferentes tests que van a cubrir el c贸digo del sistema.


* [Gestor de Tareas](#tareas)
* [Biblioteca de Aserciones](#aserciones)
* [Marco de Pruebas](#pruebas)
* [Metodolog铆a de dise帽o software](#metodologia)

<a name="tareas"></a>
### Gestor de Tareas 馃摀
Un [gestor de tareas o herramienta de construcci贸n](https://jj.github.io/curso-tdd/temas/gestores-tareas.html):

> Permite usar, como subcomandos de un solo programa y especificados en un solo fichero, todas las tareas que se tienen que llevar a cabo con una aplicaci贸n, desde su compilaci贸n hasta la generaci贸n de la documentaci贸n pasando por todo lo necesario para ejecutar todo tipo de tests y desplegarlo.

Para realizar esta cometido en el lenguaje de programaci贸n Julia haremos uso del servicio de Integraci贸n Cont铆nua de **Travis CI**. Donde primeramente comprobar谩 la integraci贸n del proyecto ejecutando los tests y posteriormente inicializar谩 los pasos necesarios para su compilaci贸n y generaci贸n de la documentaci贸n.
Para ver otras opciones haga clic [aqu铆](https://github.com/vntr-CC/Forward-Football/blob/main/Documentacion/extra/gestor-tareas.md).

<a name="aserciones"></a>
### 馃摎 Biblioteca de Aserciones 馃摎

Julia est谩 en r谩pido desarrollo y tiene un extenso conjunto de pruebas para verificar la funcionalidad en m煤ltiples plataformas. En este caso haremos uso del m贸dulo **Test** en conjunto con **SafeTestsets** para la definici贸n de los diferentes tests que cubren los m煤ltiples aspectos de la l贸gica de negocio. Para ver otras opciones haga clic [aqu铆](https://github.com/vntr-CC/Forward-Football/blob/main/Documentacion/extra/biblioteca-aserciones.md)

Comentar que al desarrollar el proyecto puramente en Julia, la necesidad de un archivo `build.jl` desaparece. Gracias al archivo del proyecto `Project.toml` que describe el proyecto a un nivel alto, conteniendo por ejemplo, las dependencias de los diferentes paquetes o las restricciones de compatibilidad. Tambi茅n en 茅l se definen diferentes campos que nos permiten diferenciar los paquetes que necesitamos en las diferentes fases de compilaci贸n. En nuestro caso, al utilizar dos librerr铆as para los tests, definiendo sus dependencias bajo el campo `extras`, nos aseguramos que estas librer铆as solo se instalar谩n en el proceso de testeo del proyecto.

<a name="pruebas"></a>
### 鉁? Marco de Pruebas 鉂?
Para utilizar y lanzar los tests en Julia, solo necesitamos tener Julia instalado y a帽adir el proyecto como paquete a un ecosistema de nuestra elecci贸n. Nosotros lo instalaremos en el que se crea por defecto, pero aconsejamos que si se va a descargar software de terceros se inicialice en un ecosistema diferente en caso de causar fallos de dependencias que podr铆a haber con otros paquetes que tuviera ya instalados. Los pasos son los siguientes:

Una vez abierto el REPL de Julia, presionamos `]`, en el teclado espa帽ol se realiza mediante `AltGr + ]`, para entrar en el REPL del administrador de paquetes (para retornar presionar la tecla `Delete`). Luego indicamos el paquete a a帽adir que en nuestro caso es la direcci贸n de este repositorio:

```julia-repl
(@v1.6) pkg> add https://github.com/vntr-CC/ForwardFootball.git
```
Una vez instalado, somos capaces de testearlo dentro del mismo REPL de la siguiente manera:
```julia-repl
(@v1.6) pkg> test ForwardFooball
```

<a name="metodologia"></a>
### 馃摑 Metodolog铆a de dise帽o software 馃摑

A la hora de implementar los tests, haremos uso de la metodolog铆a TDD para comprobar el funcionamiento general del c贸digo, y haremos uso de la metodolog铆a BDD para comprobar el comportamiento indicado por las historias de usuario.

Para comprobar cu谩ntas funcionalidades de nuestro proyecto est谩n cubiertos por los tests, podemos hacer uso de [Coveralls](https://coveralls.io/) o [Codecov](https://about.codecov.io/).
