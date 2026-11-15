# Nivel 2. Imágenes y enlaces
## A1. Verdadero o falso

| N.º | Afirmación | V / F | Respuesta y corrección |
|---|---|---|---|
| 1 | "La etiqueta `<img>` se cierra con `</img>`." | F | Se trata de un elemento vacío (sin contenido interno), por lo que no lleva etiqueta de cierre. |
| 2 | "El atributo `alt` muestra un texto si la imagen no se puede cargar." | V | También sirve para describir la imagen a usuarios con lectores de pantalla y ayudar a los motores de búsqueda. |
| 3 | "Para dar ancho y alto a una imagen se recomienda usar `style` en lugar de `width` y `height`." | V | Al aplicarlo mediante estilos en línea (CSS), evitas que una hoja de estilos externa sobrescriba las dimensiones por accidente. |
| 4 | "La propiedad `float` permite que una imagen flote a la izquierda o a la derecha del texto, o que no flote." | V | Se controla usando los valores `left`, `right` o `none`. |
| 5 | "El rótulo de un enlace solo puede ser un texto." | F | Dentro de un enlace se puede incluir texto, una imagen o una combinación de ambos. |
| 6 | "`target="_blank"` hace que el enlace se abra en una ventana (pestaña) nueva." | V | Si se omite este atributo, el destino se carga por defecto en la misma pestaña. |
| 7 | "Por defecto, un enlace ya visitado se ve azul y uno por visitar, morado." | F | Ocurre justo lo contrario: sin visitar se muestra azul (y subrayado), mientras que el visitado pasa a ser morado. |
| 8 | "Un enlace relativo escribe la URL completa, incluido el dominio." | F | Esa definición corresponde a una ruta absoluta. Una ruta relativa parte de la ubicación del archivo actual (por ejemplo, `docs/info.html`). |


## A2. Relaciona atributo y función

| Elemento | Descripción | Respuesta |
|---|---|---|
| 1. `src` | D. Ruta del archivo de imagen | 1-D |
| 2. `alt` | G. Texto que se muestra si la imagen no carga | 2-G |
| 3. `href` | B. Indica el destino del enlace | 3-B |
| 4. `target` | F. Indica dónde se abrirá el destino del enlace | 4-F |
| 5. `id` | A. Crea un marcador (bookmark) dentro de la página | 5-A |
| 6. `float` | E. Propiedad CSS para que la imagen flote junto al texto | 6-E |
| 7. `_blank` | C. Valor de `target` que abre una pestaña nueva | 7-C |


## A3. ¿Absoluto o relativo?


| N.º | Dirección | Tipo | Por qué |
|---|---|---|---|
| 1 | `https://w3.org` | Absoluto | Tiene protocolo y dominio. |
| 2 | `paginas/contacto.html` | Relativo | Parte de la carpeta actual. |
| 3 | `/css/default.asp` | Relativo (a la raíz) | Empieza por `/` y va desde la raíz. |
| 4 | `https://google.com` | Absoluto | Es una URL completa con dominio. |
| 5 | `./apuntes.pdf` | Relativo | `./` indica el directorio actual. |
| 6 | `imagenes/logo.png` | Relativo | Entra en la carpeta `imagenes`. |


## A4. Formatos de imagen

| Abreviatura | Nombre completo | Extensión |
|---|---|---|
| GIF | Graphics Interchange Format | `.gif` |
| JPEG | Joint Photographic Experts Group | `.jpg`, `.jpeg` |
| PNG | Portable Network Graphics | `.png` |
| SVG | Scalable Vector Graphics | `.svg` |
| ICO | Microsoft Icon | `.ico` |
| APNG | Animated Portable Network Graphics | `.apng` |
