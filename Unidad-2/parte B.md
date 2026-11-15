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


## A5. Caza los errores de la galería

### Código original

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Mi galería</title>
</head>
<body>
<h1>Mi viaje de fin de curso</h1>
<img>src="playa.jpg" alt="Playa al atardecer"</img>
<img src="monte.jpg" style="width=300px; height=200px;">
<a href=https://www.wikipedia.org target="_blank">Más información sobre el destino
</body>
</html>
```

### Errores encontrados


| N.º | Error | Explicación | Corrección |
|---|---|---|---|
| 1 | `<img>src="playa.jpg" ...` | La etiqueta `<img>` se cierra antes de tiempo y los atributos quedan sueltos fuera de ella como texto normal. | `<img src="playa.jpg" alt="Playa al atardecer">` |
| 2 | `</img>` | La etiqueta `<img>` es un elemento vacío y no utiliza etiqueta de cierre. | Quitar `</img>`. |
| 3 | `width=300px; height=200px;` | Dentro de CSS se deben usar dos puntos (`:`) para asignar valores a las propiedades, en lugar del signo igual (`=`). | `width:300px; height:200px;` |
| 4 | Segunda imagen sin `alt` | Es obligatorio incluir el atributo `alt` en todas las imágenes para describir su contenido. | `alt="Vista del monte"` |
| 5 | Enlace sin cerrar | Falta la etiqueta de cierre `</a>`, por lo que el enlace queda abierto. | Añadir `</a>`. |
| 6 | `href=https://...` sin comillas | Según las pautas del curso, todos los valores de los atributos deben ir entre comillas. | `href="https://www.wikipedia.org"` |
| 7 | Falta `lang` y `meta author` | Requisito de estructura y buenas prácticas indicadas en el boletín. | `<html lang="es">` y `<meta name="author">` |



### Versión corregida

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Mi galería</title>
</head>
<body>
  <h1>Mi viaje de fin de curso</h1>
  <img src="playa.jpg" alt="Playa al atardecer">
  <img src="monte.jpg" alt="Vista del monte" style="width:300px; height:200px;">
  <a href="https://www.wikipedia.org" target="_blank">Más información sobre el destino</a>
</body>
</html>
```


## A6. Rutas que no funcionan

El código está en `index.html`, en la carpeta `proyecto/`.

| Código | ¿Funciona? | Motivo | Corrección |
|---|---|---|---|
| `<img src="logo.png" alt="Logo">` | No | El archivo `logo.png` se encuentra dentro de la subcarpeta `imagenes/`. | `src="imagenes/logo.png"` |
| `<img src="imagenes/equipo.jpg" alt="Equipo">` | Sí | | |
| `<a href="Contacto.html">Contacto</a>` | No | El nombre real es `contacto.html` todo en minúsculas, y los servidores diferencian mayúsculas de minúsculas. | `href="contacto.html"` |
| `<a href="apuntes.pdf">Apuntes</a>` | Sí | | |
| `<a href="imagenes/apuntes.pdf">Apuntes</a>` | No | El PDF no está guardado en `imagenes/`, sino en la misma carpeta que `index.html`. | `href="apuntes.pdf"` |
| `<img src="imagenes/equipo.png" alt="Equipo">` | No | La extensión correcta de la imagen es `.jpg` y no `.png`. | `src="imagenes/equipo.jpg"` |


## A7. ¿Qué verá el usuario?

```html
<h2>Mi mascota</h2>
<img src="gato.jpg" alt="Gato durmiendo" style="float: right;">
<p>Se llama Miau y duerme catorce horas al día. Cuando está despierto, intenta apagar el router.</p>
<a href="https://www.w3.org/" target="_blank"><img src="logo.png" alt="W3C"></a>
```

(a) La foto del gato se alinea en el margen derecho junto al párrafo, mientras que el texto se adapta a su lado izquierdo.

(b) En caso de que no se encuentre el archivo `gato.jpg`, el navegador mostrará el icono de error de carga acompañado de la descripción "Gato durmiendo" (definida en `alt`), manteniendo su posición a la derecha.

(c) Pulsar sobre el logotipo cargará la página https://www.w3.org/ en una pestaña distinta del navegador, ya que la imagen actúa como enlace y tiene asignado el atributo `target="_blank"`.
