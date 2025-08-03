# Pseudocódigo para los productos

INICIO Funcion obtenerProductos(filtro)

	1. Definir la URL de STRAPI
	URL_BASE = "http://etc.etc.strapi.com"

	2. Construir la URL completa con el filtro

	URL_FINAL = URL_BASE

	//se usa una desición para añadir al filtro si existe

		SI FILTRO NO es NULO o vacío ENTONCES
			URL_FINAL = URL_FINAL + "?filtro_de_busqueda=" + filtro
		FIN SI	

	3. Usar una estructura try catch para manejar errores
	INTENTAR:
		4.Hacer la llamada a la API
		respuesta = LLAMAR_API_A(URL_FINAL)

		5. Convertir la respuesta a JSON

		datos_productos = convertir-a-json(respuesta)

		6. Si la llamada es exitosa retornar los datos
		RETORNAR datos_productos

	CAPTURAR_ERROR (error):
	7. Si hay un error en la llamada
	MOSTRAR_ERROR("No se pudieron obtener los productos: " + error)
	RETORNAR NULO
	FIN INTENTAR		

FIN Funcion