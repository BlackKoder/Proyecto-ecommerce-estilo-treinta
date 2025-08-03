# Elementos que se van a ver en la sección del cliente

Se sabe que se va a seguir la lógica vista para la vista del cliente ya mostrada en los wireframes. Pero, hay algunos pequeños detalles que podríam mejorar la UX. Por ejemplo está lo del carrito de compras, el cuál puede hacerse con el local Storage, o en su defecto se puede hacer con Zustand

El buscador se debería de emparejar mediante la API que busque los productos creados en el backend, teniendo en cuenta que se va a utilizar Postgre, anteriormente se pudo haber implementado esta idea mediante metadatos en las etiquetas del producto y que estás sean generadas con Next al administrador gestionar y cargar productos.

Se tiene que tener en cuenta que la carga de la pagina debería de ser on page, considerando que no va a tener artículos masivos, y que eso le dará un toque visual más fresco. Esto se podría hacer con React para que no se tengan que usar botones de paginación, y se cargue de forma asíncrona