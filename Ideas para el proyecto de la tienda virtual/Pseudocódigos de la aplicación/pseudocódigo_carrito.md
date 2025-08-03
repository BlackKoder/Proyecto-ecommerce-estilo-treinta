# Pseudocódigo del carrito de compra

INICIO Función agregarProductoAlCarrito(producto, cantidad)

	// 1. Obtener los productos del carrito
	carrito_actual = OBTENER_DATOS("carrito_id")

	// 2. Variable para saber si encontramos el producto
	productoEncontrado = FALSO

	// 3. Recorrer el carrito para buscar el producto
	PARA CADA item en carrito_actual:
		SI item.id es IGUAL a producto.id ENTONCES
			item.cantidad = item.cantidad + cantidad
			producto_encontrado = VERDADERO
			SALIR DEL PARA CADA
		FIN SI	
	FIN PARA	

	//4. Si el producto no aparece lo agregamos
	SI producto_encontrado es FALSO ENTONCES
		AGREGAR el producto al carrito actual
	FIN SI	

	// 5. Guardar el carrito en el almacenamiento local
	GUARDAR_DATOS("carrito_key", carrito_actual)


FIN Funcion  