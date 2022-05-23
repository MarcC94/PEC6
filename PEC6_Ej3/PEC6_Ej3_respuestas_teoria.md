> ### PEC6_Ej3
>
> #### a) ¿Qué son los interceptores?
>
> Los interceptores de Angular son un tipo especial de servicio de cliente HTTP que tiene el único propósito de interceptar todas las solicitudes HTTP realizadas. Esto es cierto tanto para las solicitudes HTTP entrantes como salientes.
>
> Los interceptores HTTP siempre estan en medio de cualquier solicitud HTTP única. Estos servicios interceptarán todas las solicitudes realizadas por la aplicación, lo que nos permitirá realizar muchas operaciones sobre ellas antes de que se envíen al servidor. Las funciones incluyen agregar un encabezado HTTP personalizado a la solicitud saliente final (por ejemplo, agregar un encabezado de autorización y pasar un token de autorización en todos los puntos finales que requieren un conjunto de permisos, etc.), almacenamiento en caché, registro para recopilar métricas, manejo de errores, etc.
>
> Un proceso similar ocurre cuando el servidor responde. Ahora tenemos la respuesta interceptada por el interceptor HTTP, lo que nos permite realizar una serie de operaciones antes de que la aplicación consuma la respuesta final. Un escenario de caso de uso cotidiano podría ser transformar el objeto de respuesta en un formato más significativo para el producto. Por ejemplo, limpiar el objeto de respuesta y extraer solo las partes requeridas en lugar de tratar con eso en cada componente que usaría los datos.
>
> #### b) Analiza la siguiente cadena de operadores de RxJS, explica cada uno de los pasos que se están desarrollando y explica en qué caso usarías este código:
>
> El código ejecuta una busqueda de un vino con la función searchSubject(). El primer método utilizado para esta búsqueda es startsWith(), el cual indica si una cadena de texto comienza con los caracteres de una cadena de texto concreta, en este caso "searchTerm", devolviendo true o false según corresponda.
>
> debounceTime() emite valores solo después de que haya transcurrido una cierta cantidad de tiempo desde el último valor. Emite solo el último valor y descarta cualquier valor intermedio.
>
> distinctUntilChanged() hace que solo emita valor cuando el valor actual es diferente al último.
>
> .merge() aplana múltiples observables al combinar sus valores en un observable. En el ejemplo tiene como argumento la función reloadProductsList() por lo que devolvera un listado de productos que cumplan la condición de que comienzen por los caracteres de la cadena de texto indicada en el método startsWith().
>
> .switchMap() cancela observables anteriores y solo emite valores del último observable. Esto permite modificar el searchTerm sin recibir cada vez una cantidad mayor de valores procedentes de diferentes observables que se irian ejecutando y irian aumentando cada vez que modificaramos nuestro texto de búsqueda.
>
> Este código lo utilizaría para buscar el nombre de un vino en base a un término de búsqueda.