> ### PEC6_Ej1
>
> #### a) ¿Cuál es la función de los componentes y servicios? (i.e. cuándo se debe utilizar cada uno de ellos)
>
> Un componente en Angular es un elemento que está compuesto por:
>
> Un archivo que será nuestro Template (app.component.html), el cual es nuestro HTML, que es el que se va a visualizar en la interfaz de usuario o la vista.
>
> Un archivo de lógica, la cual es la que pondremos en un archivo .ts (como por ejemplo app.component.ts), ese archivo debe incluir una clase y esta es la que va a contener las propiedades que se van a usar en la vista (HTML) y los métodos que será las acciones que se ejecutarán en la vista. En este archivo de lógica también se incluye una metadata, que es definida con un decorador,  que identifica a Angular como un componente.
>
> Un archivo para el CSS (podemos usar un preprocesador como SASS o LESS), donde incluiremos los estilos, lo que nos ayuda a hacer bonita nuestra aplicación.
>
> Los servicios son clases que se encargan de acceder a los datos para entregarlos a los componentes. Lo bueno de esto es que podemos reaprovechar servicios para distintos componentes.
>
> #### b) ¿Qué es la <<inyección de dependencias>>? ¿Para qué sirve el decorador @Injectable?
>
> La inyección de dependencias (en inglés Dependency Injection, DI) es un patrón de diseño orientado a objetos, en el que se suministran objetos a una clase en lugar de ser la propia clase la que cree dichos objetos. Esos objetos cumplen contratos que necesitan nuestras clases para poder funcionar (de ahí el concepto de dependencia). Nuestras clases no crean los objetos que necesitan, sino que se los suministra otra clase 'contenedora' que inyectará la implementación deseada a nuestro contrato.1​
>
> En otras palabras, se trata de un patrón de diseño que se encarga de extraer la responsabilidad de la creación de instancias de un componente para delegarla en otro.
> 
> El decorador @injectable sirve para marcar una clase como disponible para ser proporcionada e inyectada como dependencia.
>
> #### c) Explica los siguientes conceptos de la programación reactiva que se usan en RxJS:
>
> • Observable: Son colecciones Push de múltiples valores.
>
> • Subscription: Es un objeto que representa un recurso desechable, normalmente la ejecución de un Observable. Una suscripción tiene un método importante, darse de baja, que no admite argumentos y simplemente desecha el recurso que tiene la suscripción.
>
> • Operators: Son las piezas esenciales que permiten que el código asincrónico complejo se componga fácilmente de manera declarativa.
>
> • Subject: Es un tipo especial de Observable que permite la multidifusión de valores a muchos Observadores. Mientras que los Observables simples son de unidifusión (cada Observador suscrito posee una ejecución independiente del Observable), los Subjects son de multidifusión.
>
> • Schedulers: Controla cuándo comienza una suscripción y cuándo se entregan las notificaciones.
>
> #### d) ¿Cuál es la diferencia entre promesas y observables?
>
> Algunas diferencias entre observables y promesas son las siguientes:
>
> Los observables son declarativos; La ejecución no comienza hasta la suscripción. Las promesas se ejecutan inmediatamente después de la creación. Esto hace que los observables sean útiles para definir recetas que se pueden ejecutar cuando necesites el resultado.
>
> Los observables proporcionan muchos valores. Las promesas proporcionan un valor. Esto hace que los observables sean útiles para obtener múltiples valores a lo largo del tiempo.
>
> Los observables diferencian entre encadenamiento y suscripción. Las promesas solo tienen cláusulas .then (). Esto hace que los observables sean útiles para crear recetas de transformación complejas para ser utilizadas por otra parte del sistema, sin que el trabajo se ejecute.
>
> Observables subscribe() es responsable de manejar los errores. Las promesas empujan los errores a promesas hijas. Esto hace que los observables sean útiles para el manejo centralizado y predecible de errores.
>
> #### e) ¿Cuál es la función de la tubería (pipe) async?
>
> La tubería asíncrona se suscribe a un Observable o Promise y devuelve el último valor que ha emitido. Cuando se emite un nuevo valor, la canalización asíncrona marca el componente para verificar los cambios. Cuando el componente se destruye, la canalización asíncrona cancela la suscripción automáticamente para evitar posibles fugas de memoria. Cuando la referencia de la expresión cambia, la canalización asíncrona cancela automáticamente la suscripción del antiguo Observable o Promise y se suscribe al nuevo.