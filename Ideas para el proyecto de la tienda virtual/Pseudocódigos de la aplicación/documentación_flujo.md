# Documentación general de la vista del cliente en el ecommerce

Como bien se especifica en el diagrama de flujo, se va a mantener una lógica simple pero bien implementada para que
no haya fallos a nivel de usuario. 

Vamos a estructurar el documento por cada función que aparece en el diagrama

## Presionar el logo

Esto es simple, solo se debe de hacer que retorno a la pagina principal para que sea fácil de acceder en caso de que el usuario se quede atascado en algún lago. Igualmente en el navbar si se permite, se puede poner un botón de inicio, si el espacio en el navbar es limitado, se puede implementar de forma principal lo de retornar a la home desde el logo, la verdad es una lógica simple que se puede usar con un href en HTML

## Seleccionar categorías

Se debe de colocar todas las categorías que planea el cliente para hacer la aplicación, igualmente al hacerse con los href para redireccionar, se debe de poder consultar estos datos a la API de strapi para saber cuáles son las categorías y poder filtrarlas mejor

## Acerca de

La sección acerca de es una sección institucional dandole un breve recorrido al usuario de cuál es el sitio web, su finalidad y el equipo de trabajo. Cosas simples que se complementan con la información institucional del footer

## Al revisar el carrito

Esto es algo sencillo que puede verse en la UI del usuario  a través de un efecto hover o con un menú active para que despliegue un menú en el que se van a ver los productos listados del cliente en esa sesión. Como no se va a hacer una tabla de usuarios en el sitio, porque sería insostenible para el tipo de tecnologías que se están usando, en el sentido de que es de bajo presupuesto o en su defecto nulo, como vendrían siendo el plan de alojamiento gratuito de vercel y el plan de alojamiento de la BDD como Render, tener muchas conexiones concurrentes sería problemático incluso si se estuviera usando node, el problema sería donde está alojada la BDD que es Render y las limitaciones del servicio y la transferencia de archivos, pero como render solo se va a usar para que el administrador del sitio cargue, revise y haga operaciones CRUD en la aplicación, al final esto no afectaría la UX del usuario.

Entonces cómo se hará en este caso, sencillo se usa la API de Strapi, para que a través del JSON se detecte cuáles son los productos disponibles en la BDD y que concuerden con el front de la pagina, ahora cómo se van a almacenar los productos a nivel de usuario sin tener una tabla en la BDD en la aplicación? sencillo, cada usuario podrá guardar sus productos a través del estado de la aplicación, es decir en el local storage del navegador, y esto será como una sesión de invitado que le permite que mientras esté en la aplicación estos productos aparezcan. Obviamente debería de haber una notificación que le explique esto al usuario. Pero así se podría guardar productos en el carrito a nivel de usuario.

Una vez se vean los productos del carrito, el usuario decidirá si entrar directamente a la publicación del producto, o si no tiene un producto cargado en el carrito, no le aparecerá ningún resultado


## Al hacer una búsqueda

Para hacer la búsqueda se utiliza la misma lógica que anteriormente, se encierra en una variable el valor del input de búsqueda y luego se hace un script que tome las palabras clave para ser buscados en la API de Strapi para que se haga la consulta en la BDD y el usuario obtenga sus resultados o no los tenga

## Sección del producto

Esto es muy sencillo a nivel del front simplemente se tiene una vista para el usuario con el producto deseado, o cualquier producto que se recomiende, va a seguir la misma lógica de usar strapi para hacer las consultas de los productos que están cargados en la BDD. Se puede aplicar un pequeño algoritmo de recomendación a partir de las búsquedas del usuario en esa sesión, y de los datos del usuario almacenados en una tabla del lado del administrador que indica las ventas más importantes del día, las ofertas y productos que estén relacionados con otros productos. 

Para esto podría ser de la siguiente forma, en la sección del producto se muestran recomendaciones de los productos relacionados a los que el cliente está viendo junto con los mejores precios y ofertas 