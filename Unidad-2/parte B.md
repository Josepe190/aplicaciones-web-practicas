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



## B1. Galería de tu setup



```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>B1. Galería de tu setup</title>
</head>
<body>
  <h1>Galería de mi mascota</h1>
  <h2>Tamaño original</h2>
  <img src="imagenes/gato_patio.jpeg" alt="Mi gato calicó en el patio junto a su cuenco verde">
  <h2>200 × 150 con el atributo style</h2>
  <img src="imagenes/gato_patio.jpeg" alt="Mi gato calicó en el patio junto a su cuenco verde" style="width:200px; height:150px;">
  <h2>200 × 150 con los atributos width y height</h2>
  <img src="imagenes/gato_patio.jpeg" alt="Mi gato calicó en el patio junto a su cuenco verde" width="200" height="150">
  <h2>Imagen rota a propósito</h2>
  <img src="imagenes/gato_patio_error.jpeg" alt="Mi gato calicó en el patio junto a su cuenco verde">
  <!--
    Pregunta: ¿por qué se recomienda style frente a width y height?
    Respuesta: al utilizar style aplicamos el tamaño directamente como código CSS, separando el diseño de la estructura HTML.
    De esta manera se evita que una hoja de estilos externa modifique las medidas por accidente y se mantiene todo el estilo unificado.
  -->
</body>
</html>
```

### Qué se ve con la imagen rota

El atributo `src` apunta a `gato_patio_error.jpeg`, un archivo que no existe en la carpeta. Al no encontrarlo, el navegador muestra el icono de imagen rota acompañado del texto descriptivo definido en `alt`. Por ese motivo es tan importante redactar un `alt` claro que explique qué había en la foto.

### Respuesta a la pregunta

Al utilizar `style` aplicamos el tamaño directamente como código CSS, separando el diseño de la estructura HTML. De esta manera se evita que una hoja de estilos externa modifique las medidas por accidente y se mantiene todo el estilo unificado. Los atributos clásicos `width` y `height` siguen siendo válidos, pero tienen menor prioridad frente a las reglas CSS.



## B2. Perfil de una red social

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>B2. Perfil de una red social</title>
</head>
<body>
  <h1>Josep Tech</h1>
  <img src="imagenes/gato_sofa.jpeg" alt="Foto de perfil de mi gato acurrucado en el sofá" style="width:180px; border:5px solid green; float:right;">
  <p>Josep es un apasionado de la informática y el desarrollo web que comparte trucos prácticos sobre sistemas y diseño de páginas desde cero. Empezó montando sus propios proyectos locales y hoy ayuda a otros estudiantes a entender las bases del código limpio.</p>
  <p>En su perfil publica guías sencillas sobre cómo estructurar documentos HTML, organizar carpetas sin errores de rutas y aplicar estilos CSS paso a paso. Sus publicaciones favoritas son las de resolución de problemas reales en el navegador.</p>
  <p>Cuando no está programando o configurando equipos, pasa el rato con su mascota y disfruta probando nuevas herramientas digitales. Su objetivo es demostrar que cualquiera puede crear su propia web con un poco de práctica.</p>
  <img src="imagenes/gato_limpiandose.png" alt="Mi gato limpiándose tranquilamente en el suelo" style="width:160px; border:3px dotted blue; float:left;">
  <p>Este es el verdadero protagonista de la cuenta descansando y limpiándose después de comer. Al aplicar flotación hacia el margen izquierdo con un borde azul punteado, el navegador acomoda automáticamente todo este bloque de texto a su lado derecho. De esta forma se aprovecha mucho mejor el ancho de la pantalla sin dejar huecos en blanco.</p>
  <p><img src="imagenes/gato_perfil.jpeg" alt="Mi gato posando de perfil encima de la mesa" style="width:120px; float:none;"> Esta última foto no flota hacia ningún lado: se mantiene integrada dentro de la propia línea del párrafo, comportándose exactamente igual que un carácter más del texto.</p>
</body>
</html>
```

### Respuesta a la pregunta

- `float: left`: coloca la imagen pegada al borde izquierdo y hace que el texto fluya por su lado derecho.
- `float: right`: desplaza la imagen hacia el borde derecho y permite que el texto la rodee por su lado izquierdo.
- `float: none` (es el comportamiento por defecto): la imagen no flota hacia los lados, se queda en su posición normal dentro de la línea y el texto no la envuelve.


```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>B2. Perfil de una red social</title>
</head>
<body>
  <h1>Josep Tech</h1>
  <img src="imagenes/gato_sofa.jpeg" alt="Foto de perfil de mi gato acurrucado en el sofá" style="width:180px; border:5px solid green; float:right;">
  <p>Josep es un apasionado de la informática y el desarrollo web que comparte trucos prácticos sobre sistemas y diseño de páginas desde cero. Empezó montando sus propios proyectos locales y hoy ayuda a otros estudiantes a entender las bases del código limpio.</p>
  <p>En su perfil publica guías sencillas sobre cómo estructurar documentos HTML, organizar carpetas sin errores de rutas y aplicar estilos CSS paso a paso. Sus publicaciones favoritas son las de resolución de problemas reales en el navegador.</p>
  <p>Cuando no está programando o configurando equipos, pasa el rato con su mascota y disfruta probando nuevas herramientas digitales. Su objetivo es demostrar que cualquiera puede crear su propia web con un poco de práctica.</p>
  <img src="imagenes/gato_limpiandose.png" alt="Mi gato limpiándose tranquilamente en el suelo" style="width:160px; border:3px dotted blue; float:left;">
  <p>Este es el verdadero protagonista de la cuenta descansando y limpiándose después de comer. Al aplicar flotación hacia el margen izquierdo con un borde azul punteado, el navegador acomoda automáticamente todo este bloque de texto a su lado derecho. De esta forma se aprovecha mucho mejor el ancho de la pantalla sin dejar huecos en blanco.</p>
  <p><img src="imagenes/gato_perfil.jpeg" alt="Mi gato posando de perfil encima de la mesa" style="width:120px; float:none;"> Esta última foto no flota hacia ningún lado: se mantiene integrada dentro de la propia línea del párrafo, comportándose exactamente igual que un carácter más del texto.</p>
</body>
</html>
```

### Respuesta a la pregunta

- `float: left`: coloca la imagen pegada al borde izquierdo y hace que el texto fluya por su lado derecho.
- `float: right`: desplaza la imagen hacia el borde derecho y permite que el texto la rodee por su lado izquierdo.
- `float: none` (es el comportamiento por defecto): la imagen no flota hacia los lados, se queda en su posición normal dentro de la línea y el texto no la envuelve.




## B3. ¿Qué formato elijo?

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>B3. ¿Qué formato elijo?</title>
</head>
<body>
  <h1>Elección del formato de imagen adecuado</h1>
  <p>Si necesito guardar una foto de vacaciones con muchos colores, elijo <strong>JPEG (.jpg / .jpeg)</strong>, ya que reduce bastante el peso del archivo manteniendo una buena calidad visual en fotografías.</p>
  <p>Si se trata de un logo con fondo transparente, utilizo <strong>PNG (.png)</strong>, porque soporta canales de transparencia y conserva los bordes definidos sin perder nitidez.</p>
  <p>Para un icono que deba verse nítido a cualquier tamaño, opto por <strong>SVG (.svg)</strong>, al ser un formato vectorial que se escala sin pixelarse.</p>
  <p>Cuando quiero insertar una animación corta tipo meme, recurro a <strong>GIF (.gif)</strong>, puesto que permite secuencias animadas y es compatible con todos los navegadores web.</p>
  <p>Para el icono que aparece en la pestaña del navegador, uso <strong>ICO (.ico)</strong>, que es el formato estándar para los favicon.</p>
  <h2>Ejemplos con mis archivos</h2>
  <img src="imagenes/gato_patio.jpeg" alt="Ejemplo de fotografía en formato JPEG" style="width:240px;">
  <img src="imagenes/gato_limpiandose.png" alt="Ejemplo de imagen en formato PNG" style="width:160px;">
  <img src="imagenes/gato_mesa.gif" alt="Ejemplo de archivo en formato GIF" style="width:160px;">
</body>
</html>
```
### recuerda

| Necesidad | Formato |
|---|---|
| Fotografía con gran variedad de colores | JPEG (`.jpg`, `.jpeg`) |
| Gráficos con fondo transparente | PNG (`.png`) |
| Iconos escalables sin pérdida de nitidez | SVG (`.svg`) |
| Imágenes animadas cortas | GIF (`.gif`) o APNG (`.apng`) |
| Icono de pestaña del navegador (favicon) | ICO (`.ico`) |





## B4. Mis enlaces favoritos

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>B4. Mis enlaces favoritos</title>
</head>
<body>
  <h1>Mis páginas web favoritas</h1>
  <p><a href="https://w3.org">Consorcio W3C, entidad encargada de los estándares web</a></p>
  <p><a href="https://google.com" target="_blank">Buscador de Google (abre en pestaña nueva)</a></p>
  <p><a href="https://wikipedia.org" target="_blank" style="color:teal;">Wikipedia, la enciclopedia libre (abre en pestaña nueva)</a></p>
</body>
</html>
```

### Respuesta a la pregunta

Sin aplicar estilos personalizados, los navegadores muestran un enlace pendiente de visitar en color azul y subrayado, mientras que un enlace ya visitado aparece en color morado. Si se mantiene pulsado (estado activo), cambia momentáneamente a rojo.







## B5. Enlaces con imagen

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>B5. Enlaces con imagen</title>
</head>
<body>
  <h1>Enlaces utilizando imágenes</h1>
  <p><a href="https://wikipedia.org" target="_blank"><img src="imagenes/gato_patio.jpeg" alt="Acceder a Wikipedia en una pestaña nueva" style="width:150px;"></a></p>
  <p><a href="https://google.com"><img src="imagenes/gato_limpiandose.png" alt="Miniatura para ir al buscador" style="width:40px;"> Buscar información en Google</a></p>
  <!--
    Enlace 1: su destino es https://wikipedia.org, el rótulo está formado únicamente por la imagen gato_patio.jpeg y su objetivo es _blank para abrirse en una pestaña nueva.
    Enlace 2: su destino es https://google.com, el rótulo combina la imagen gato_limpiandose.png junto con el texto "Buscar información en Google", y su objetivo es abrirse en la misma pestaña al no tener atributo target.
  -->
</body>
</html>
```







## B6. Mini web de tres páginas

### `index.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Inicio</title>
</head>
<body>
  <h1>Página principal de Josep</h1>
  <p><a href="sobre-mi.html">Sobre mí</a> | <a href="contacto.html">Contacto</a></p>
  <img src="imagenes/gato_sofa.jpeg" alt="Foto de mi gato descansando en el sofá" style="width:200px;">
  <p>Bienvenido a mi sitio web de tres páginas conectadas mediante enlaces relativos.</p>
</body>
</html>
```

### `sobre-mi.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Sobre mí</title>
</head>
<body>
  <h1>Conoce un poco sobre mí</h1>
  <p><a href="index.html">Inicio</a> | <a href="contacto.html">Contacto</a></p>
  <p>Soy Josep, estudiante de Aplicaciones Web en 2.º de SMR, y estoy practicando la creación de sitios en HTML y CSS.</p>
</body>
</html>
```

### `contacto.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Contacto</title>
</head>
<body>
  <h1>Formas de contacto</h1>
  <p><a href="index.html">Inicio</a> | <a href="sobre-mi.html">Sobre mí</a></p>
  <p>Puedes consultar más información y recursos de desarrollo web en <a href="https://w3.org" target="_blank">W3C</a>.</p>
</body>
</html>
```

### Respuesta a la pregunta

Si trasladamos `contacto.html` a otra carpeta diferente (por ejemplo, a una subcarpeta `paginas/`), fallarían todos los enlaces relativos relacionados con ese archivo:

- Los enlaces situados en `index.html` y `sobre-mi.html` que apuntan a `contacto.html` darían error al no encontrarlo en el mismo directorio (habría que cambiarlos a `paginas/contacto.html`).
- Los enlaces del menú dentro de `contacto.html` hacia `index.html` y `sobre-mi.html` también dejarían de funcionar, ya que necesitarían retroceder un nivel de carpeta usando `../index.html` y `../sobre-mi.html`.

Por el contrario, el enlace absoluto hacia la web externa seguiría funcionando sin problemas porque incluye la URL completa con protocolo y dominio.







## B7. Tu propia chuleta

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>B7. Tu propia chuleta</title>
</head>
<body>
  <h1>Chuleta de etiquetas HTML y CSS</h1>
  <p><a href="chuleta.pdf">Ver chuleta en la misma ventana</a></p>
  <p><a href="chuleta.pdf" target="_blank">Abrir chuleta en una pestaña nueva</a></p>
  <p><a href="https://w3schools.com" target="_blank">Tutorial de referencia HTML en W3Schools</a></p>
</body>
</html>
```

### Respuesta a la pregunta

Si eliminamos el archivo `chuleta.pdf` de la carpeta, ambos enlaces relativos se romperán y, al hacer clic sobre ellos, el navegador mostrará un mensaje indicando que no encuentra el archivo (en un servidor web devolvería un error 404). En cambio, el enlace externo seguirá funcionando correctamente porque apunta a una dirección de internet independiente de nuestros archivos locales.








## Parte C. Práctica 2. Las estaciones (enlaces e imágenes)

### Reflexión previa

1. ¿Qué ruta relativa usará `estaciones.html` para cargar `primavera.jpg`?

`imagenes/primavera.jpg`: como `estaciones.html` está en la carpeta raíz del proyecto, solo tiene que entrar en el subdirectorio `imagenes` para localizar el archivo.

2. ¿Qué pasaría si movieras las páginas de cada estación a una carpeta `paginas/`?

Todas las rutas relativas dejarían de funcionar. Desde dentro de `paginas/` habría que subir un nivel usando `../imagenes/primavera.jpg` para mostrar las fotos y `../estaciones.html` para el enlace de regreso, mientras que en `estaciones.html` habría que cambiar los enlaces a `paginas/primavera.html`.

3. Si las fotos miden 600 × 600 y deben verse a 300 × 300, ¿las recortas o cambias el tamaño con HTML/CSS?

Cambio sus dimensiones con CSS (`width:300px; height:300px;`). De este modo reutilizo exactamente el mismo archivo en ambas páginas sin recortar ninguna zona y, al mantener la proporción cuadrada, la imagen no se deforma.

### Estructura de ficheros

```text
estaciones/
├── imagenes/
│   ├── primavera.jpg
│   ├── verano.jpg
│   ├── otono.jpg
│   └── invierno.jpg
├── estaciones.html
├── primavera.html
├── verano.html
├── otono.html
└── invierno.html
```

### `estaciones.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Estaciones</title>
</head>
<body>
  <h1>ESTACIONES</h1>
  <h2>Primavera</h2>
  <a href="primavera.html"><img src="imagenes/primavera.jpg" alt="Paisaje florido de primavera" style="width:300px; height:300px; border:5px solid forestgreen;"></a>
  <h2>Verano</h2>
  <a href="verano.html"><img src="imagenes/verano.jpg" alt="Playa soleada de verano" style="width:300px; height:300px; border:5px solid darkorange;"></a>
  <h2>Otoño</h2>
  <a href="otono.html"><img src="imagenes/otono.jpg" alt="Bosque con hojas secas de otoño" style="width:300px; height:300px; border:5px solid peru;"></a>
  <h2>Invierno</h2>
  <a href="invierno.html"><img src="imagenes/invierno.jpg" alt="Montañas nevadas de invierno" style="width:300px; height:300px; border:5px solid royalblue;"></a>
</body>
</html>
```

### `primavera.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Primavera</title>
</head>
<body>
  <h1>Primavera</h1>
  <img src="imagenes/primavera.jpg" alt="Paisaje florido de primavera" style="width:600px; height:600px; border:5px solid forestgreen;">
  <p><a href="estaciones.html">Volver a la página principal</a></p>
</body>
</html>
```

### `verano.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Verano</title>
</head>
<body>
  <h1>Verano</h1>
  <img src="imagenes/verano.jpg" alt="Playa soleada de verano" style="width:600px; height:600px; border:5px solid darkorange;">
  <p><a href="estaciones.html">Volver a la página principal</a></p>
</body>
</html>
```

### `otono.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Otoño</title>
</head>
<body>
  <h1>Otoño</h1>
  <img src="imagenes/otono.jpg" alt="Bosque con hojas secas de otoño" style="width:600px; height:600px; border:5px solid peru;">
  <p><a href="estaciones.html">Volver a la página principal</a></p>
</body>
</html>
```

### `invierno.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Invierno</title>
</head>
<body>
  <h1>Invierno</h1>
  <img src="imagenes/invierno.jpg" alt="Montañas nevadas de invierno" style="width:600px; height:600px; border:5px solid royalblue;">
  <p><a href="estaciones.html">Volver a la página principal</a></p>
</body>
</html>
```



# Nivel 3 · Parte A. Comprobación y reflexión

## A1. Verdadero o falso

| N.º | Afirmación | V / F | Respuesta y corrección |
|---|---|---|---|
| 1 | "Para crear un bookmark se añade el atributo `id` a una etiqueta de la página." | V | Por ejemplo, colocando `<h2 id="contacto">` en un encabezado. |
| 2 | "`<a href="#S4">` salta al elemento con `id="S4"` de la misma página." | V | El símbolo `#` le indica al navegador que busque ese identificador dentro del documento actual. |
| 3 | "Dos elementos de la misma página pueden tener el mismo `id`." | F | Cada atributo `id` debe ser único dentro de un mismo documento HTML. |
| 4 | "`<a href="guia.html#wifi">` abre `guia.html` directamente en la sección con ese `id`." | V | Carga el archivo `guia.html` y desplaza la vista hasta el elemento marcado con `id="wifi"`. |
| 5 | "Los identificadores `Precios` y `precios` son el mismo." | F | Los valores de `id` son sensibles a mayúsculas y minúsculas, por lo que se consideran dos identificadores diferentes. |

## A2. ¿Qué pasa al hacer clic?

```html
<!-- Caso A -->
<a href="#precios">Ver precios</a>
<h2 id="precios">Precios</h2>

<!-- Caso B -->
<a href="#Precios">Ver precios</a>
<h2 id="precios">Precios</h2>

<!-- Caso C -->
<a href="guia.html#instalacion">Ir a la instalación</a>
```

| Caso | Qué pasa |
|---|---|
| A | El navegador desplaza la pantalla directamente hasta el subtítulo "Precios", ya que `#precios` coincide exactamente con `id="precios"`. |
| B | No ocurre ningún desplazamiento. Como `#Precios` empieza por mayúscula y el atributo está en minúscula (`id="precios"`), el navegador no encuentra coincidencia y se queda en el mismo sitio. |
| C | Se abre el archivo `guia.html` en la pestaña actual y se posiciona automáticamente en la parte que tenga `id="instalacion"`. Si ese identificador no existe, muestra la página desde el inicio. |

## A3. Reflexiona

1. ¿En qué tipo de páginas resulta más útil un índice con bookmarks?

Resulta especialmente práctico en documentos extensos divididos en varios apartados, como manuales de usuario, apuntes largos, páginas de preguntas frecuentes (FAQ) o artículos técnicos. Permite al visitante saltar de inmediato al tema que le interesa sin tener que hacer scroll por todo el texto.

2. Al final de cada sección habrá un enlace de vuelta al índice. ¿A qué `id` debe apuntar y dónde tienes que ponerlo?

Debe apuntar a un `id` situado en la zona superior de la página, justo donde comienza el documento o el índice (por ejemplo, `<h1 id="arriba">`), mediante el enlace `<a href="#arriba">Volver arriba</a>`. Ese identificador solo se define una vez arriba, mientras que el enlace de regreso se incluye al cierre de cada apartado.

3. ¿Qué pasaría si dos secciones tuvieran el mismo `id`?

El código HTML dejaría de ser válido según el estándar (daría error en cualquier validador) y, al pulsar el enlace, el navegador se detendría siempre en la primera aparición de ese `id`, haciendo imposible acceder a la segunda sección desde el índice.





## B1. Guía exprés de ciberseguridad en casa

### `guia.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Guía exprés de ciberseguridad</title>
</head>
<body>
  <h1 id="inicio">Guía exprés de ciberseguridad en casa</h1>
  <h2>Índice de contenidos</h2>
  <p>
    <a href="#contrasenas">Contraseñas</a><br>
    <a href="#wifi">Wi-Fi</a><br>
    <a href="#actualizaciones">Actualizaciones</a><br>
    <a href="#copias">Copias de seguridad</a>
  </p>

  <h2 id="contrasenas">Contraseñas</h2>
  <p>Para proteger cualquier cuenta es fundamental crear claves largas que mezclen letras, números y símbolos. Cuantos más caracteres tenga una contraseña, mucho más tiempo necesitaría un programa automático para descifrarla.</p>
  <p>Nunca utilices la misma clave en diferentes servicios de internet. Si una página sufre un robo de datos, los atacantes probarán esa misma combinación en tu correo electrónico o redes sociales; lo ideal es apoyarse en un gestor de contraseñas.</p>
  <p>Activa siempre la verificación en dos pasos en tus perfiles principales. De este modo, aunque alguien descubra tu clave, necesitará un código temporal de tu teléfono para poder iniciar sesión.</p>
  <p>Desconfía de correos o mensajes sospechosos que pidan tus credenciales con urgencia, ya que suelen ser intentos de suplantación de identidad o phishing.</p>
  <p><a href="#inicio">Volver arriba</a></p>

  <h2 id="wifi">Wi-Fi</h2>
  <p>Nada más configurar un router en casa conviene cambiar la contraseña de acceso al panel de administración que viene por defecto, puesto que muchos modelos comparten claves genéricas conocidas.</p>
  <p>Asegúrate de que tu red inalámbrica utilice el protocolo de cifrado WPA2 o WPA3 con una clave robusta y desactiva la función WPS para evitar conexiones no autorizadas mediante PIN.</p>
  <p>Si sueles recibir visitas en casa, habilita una red de invitados independiente. Así tus amigos tendrán acceso a internet sin poder ver los ordenadores o archivos compartidos de tu red local.</p>
  <p>Revisa periódicamente la lista de equipos conectados desde el panel del router para comprobar que no haya ningún dispositivo extraño usando tu conexión.</p>
  <p><a href="#inicio">Volver arriba</a></p>

  <h2 id="actualizaciones">Actualizaciones</h2>
  <p>Mantener el software al día es una de las barreras más eficaces contra los virus, ya que cada actualización suele corregir vulnerabilidades graves descubiertas recientemente.</p>
  <p>Configura las actualizaciones automáticas tanto en tu sistema operativo como en el navegador web y las aplicaciones del móvil para no dejar parches pendientes durante semanas.</p>
  <p>Descarga los programas únicamente desde sus páginas oficiales o tiendas verificadas, evitando instaladores modificados de dudosa procedencia que suelen incluir código malicioso.</p>
  <p>Cuando un dispositivo antiguo deja de recibir soporte oficial del fabricante, es recomendable dejar de utilizarlo para gestiones bancarias o compras online.</p>
  <p><a href="#inicio">Volver arriba</a></p>

  <h2 id="copias">Copias de seguridad</h2>
  <p>Realizar copias de seguridad periódicas te garantiza no perder tus documentos, fotos o trabajos de clase ante un fallo del disco duro, un robo o el ataque de un virus ransomware.</p>
  <p>Una buena práctica es seguir la regla 3-2-1: conservar tres copias de tus archivos importantes, almacenadas en dos soportes distintos y manteniendo al menos una de ellas fuera de casa o en la nube.</p>
  <p>Comprueba de vez en cuando que puedes abrir los archivos respaldados para asegurarte de que la copia se está guardando correctamente y sin errores.</p>
  <p>Automatiza el proceso de respaldo una vez a la semana para no depender de la memoria y tener siempre tus datos a salvo.</p>
  <p><a href="#inicio">Volver arriba</a></p>
</body>
</html>
```

### `indice.html`

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="author" content="Josep">
  <title>Índice general</title>
</head>
<body>
  <h1>Recursos y guías de clase</h1>
  <p><a href="guia.html#wifi">Consultar directamente el apartado Wi-Fi en la guía de ciberseguridad</a></p>
</body>
</html>
```



# STRANGER THINKS
Escritorio/
└── Stranger Thinks/
    ├── stranger thinks.html
    └── mis paginas/
        ├── index.html
        └── interiores/
            ├── introduccion.html
            ├── trailer.html
            ├── estreno.html
            ├── reparto.html
            └── argumento.html
            

stranger thinks.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<title>Stranger Things 4</title>
<h1 style="color: red; background-color: black;">
    Stranger Things 4
</h1>
<body>
   <a href="mis paginas/index.html">Indice</a>
</body>
</html>

