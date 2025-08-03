# Acciones que va a poder realizar el usuario por parte del cliente

**Las únicas acciones que va a ejecutar el usuario en el ecommerce, es Create y Read**

Hay que hacer que el alcance del scope por parte del cliente, tenga una abstracción que no le permita hacer todas las funciones CRUD directamente a la base de datos, en cambio. Acciones como la del carrito de compras, se puede almacenar en el local storage, y se puede eliminar del local storage, para que los usuarios tengan una experiencia personalizada pero se mantenga en una sesión de invitados, para que no haya una conexión por parte del usuario a la base de datos al mismo nivel que el administrador

**El Update y Delete solo serán vistos a nivel del localStorage**

## Parte de los pedidos por parte del cliente

Esta parte es sencilla, solo usaremos un formulario para que el cliente rellene los datos y mandé esos datos a la vista del administrador para que se puedan gestionar los pedidos