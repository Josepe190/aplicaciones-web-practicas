# Parte A. Comprobación y reflexión
# A1. Verdadero o falso corrige las falsas
En el grupo de clase se ha montado un debate. Decide quién tiene razón y, si la frase es falsa, reescríbela para que sea correcta.
| N.º|Afirmación|V/F |
|-----|----------|-------|
|1|"HTML es un lenguaje de programación como Python: sirve para hacer cálculos y tomar decisiones."|F, Es un lenguaje de marcado|
|2|"La etiqueta `<br>` no necesita etiqueta de cierre."|V|
|3|"El valor de un atributo siempre se escribe entre comillas."|V|
|4|"Los atributos de una etiqueta se escriben en la etiqueta de cierre."|F, los atributos se escriben en la apertura, no en el cierre|
|5|"El texto de <title> aparece en la pestaña del navegador."|V|
|6|"`<strong>` y `<b>` se visualizan igual."|V|
|7|"Todo lo que escribimos dentro de <head> se ve en la página."|V|
|8|"La etiqueta `<hr>` se cierra con `</hr>`."|V|
|9|"Un comentario HTML (`<!-- ... -->`) se muestra en pantalla como una nota gris."|F, un comentario en html no se muestra en la pantalla del navegador, se verá unicamente al inspeccionar la página
|10|"`<span>` crea un bloque de texto que siempre empieza en una línea nueva."|F, Span es un elemento de linea, asi que no empieza una nueva ni genera saltos de linea, se mantiene en la misma fila


# A2. Relaciona etiqueta y efecto
Une cada etiqueta con lo que hace (por ejemplo: 1-C).
|Etiqueta| |Efecto| |
|--------|-|------|-|
|1.`<mark>`|B|A. Texto tachado (precio antiguo de una oferta)||
|2.`<del>` |A|B. Texto remarcado, como con un fosforito||
|3.`<sub>` |E|C. Texto enfatizado (se ve como cursiva)||
|4.`<sup>` |F|D. Texto más pequeño que el normal||
|5.`<small>`|D|E. Texto en subíndice (como en H₂O)||
|6. `<em>`|C|F. Texto en superíndice (como en m²)||
|7.`<ins>`|G|G. Texto insertado (se ve subrayado)||


# A3. Caza los errores
Un compañero ha entregado este código para la web de una tienda de gadgets y tiene fallos. Encuéntralos, anótalos y escribe la versión corregida. (Pista: hay al menos 5.)
```
<html>
<head>
<title>Mi tienda de gadgets
</head>
<body>
<h1>Ofertas de otoño</h2>
<p>Auriculares con <b>cancelación de ruido</p></b>
</body>
</html>
```

Correcciones:

no es h2

lo de `</p></b>` esta mal cerrado

lo de head no esta bien cerrado

falta /title



# A4. Estilos rotos
El community manager de un streamer ha escrito estas líneas para el banner de su canal. Ninguna se ve como debería. Explica qué falla en cada una y corrígela.

<h1 style="color:red font-size:40px;">Directo esta noche</h1>
<p style="text-align=center;">Estreno de temporada</p>
<p style="background-color:yellow;">Sorteo de una tarjeta gráfica<p>

1 el ; despues de red
2 el error del = de aling center es :
3 la tercera no esta bien cerrada



# A5. Comentarios y anidación
Un aviso de ciberseguridad tiene dos errores. Encuéntralos y corrígelos.

<!- Revisar el texto antes de publicar ->
<p>Tu contraseña debe tener <strong><em>al menos 12 caracteres</strong></em>.</p>

en la primera frase son dos `--` al abrir y al entrar

La etiqueta se cierra primero con el /em




# A6. ¿Qué verá el usuario?
Sin abrir el navegador, dibuja o describe lo que se mostrará. Después compruébalo y anota si acertaste.
<h1>Resumen de la jornada</h1>
<p>Ha ganado el equipo local.<br>El rival se despide del torneo.</p>
<hr>
<h4>Próximo partido</h4>
<p>Sábado a las 18:00</p>

Lo que se deveria mostrar:

Resumen de la jornada

Ha ganado el equipo local.
El rival se despide del torneo.

Próximo partido

Sábado a las 18:00


# Parte B. Ejercicios guiados
# B1. Tu plantilla para todo el curso
Crea plantilla.html con la estructura básica y, en <head>, la codificación utf-8, un <title> ("Plantilla de 2.º SMR") y dos <meta>: descripción y autor. En el <body> escribe un comentario que diga Aquí va el contenido. La usarás como punto de partida en el resto del boletín.

```<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Plantilla de 2.º SMR</title>
  <meta name="author" content="Escribe aquí tu nombre y apellidos">
  <meta name="description" content="Plantilla base HTML5 para las prácticas de Aplicaciones Web">
</head>
<body>

  <!-- Aquí va el contenido -->

</body>
</html>
```


| Pieza | Para qué sirve | ¿Se ve en la página? |
|---|---|---|
| `<!DOCTYPE html>` | Define el estándar HTML5 | No |
| `<html lang="es">` | Etiqueta raíz; fija el idioma en español | No |
| `<meta charset="utf-8">` | Permite mostrar tildes y eñes sin fallos | No |
| `<meta name="description">` | Sinopsis breve para buscadores | No |
| `<meta name="author">` | Nombre del alumno (obligatorio en **todas**) | No |
| `<title>` | Nombre visible en la **pestaña** | Solo en la pestaña |
| `<!-- ... -->` | Nota interna ignorada por el navegador | **No**, nunca |


# B2. La noticia del día: ¿la IA te quitará el trabajo?




| Objetivo | Implementación |
| :--- | :--- |
| Título principal y subtítulo | `<h1>` para el título principal y `<h2>` para el subtítulo |
| Tres bloques de texto con un separador entre el 2.º y el 3.º | Tres `<p>` y una etiqueta `<hr>` entre el segundo y el tercero |
| Nombre del autor, fecha y medio en tres líneas **únicamente con `<br>`, sin usar `<p>`** | Texto directo dentro del `<body>` dividido con `<br>` |
| Apartado "Prueba de tamaños" | Un encabezado de sección y las etiquetas de `<h1>` hasta `<h6>` |


# B3. Ficha de oferta: el Black Friday de tu tienda


| Elemento | Apariencia | Función | Uso en la ficha |
| :--- | :--- | :--- | :--- |
| `<b>` | **negrita** | Estilo visual | `<b>AMOLED</b>` |
| `<strong>` | **negrita** | Contenido **relevante** | `<strong>¡Descuento de 250 €!</strong>` |
| `<i>` | *cursiva* | Estilo visual (modelos, conceptos) | `<i>Apex Z10</i>` |
| `<em>` | *cursiva* | Contenido con **énfasis** | `<em>la batería más duradera...</em>` |
| `<mark>` | fondo amarillo | Destacado tipo marcador | `<mark>¡Promoción...!</mark>` |
| `<small>` | texto reducido | Letra menuda / textos legales | `<small>Impuestos incluidos...</small>` |
| `<del>` | ~~tachado~~ | Contenido **descartado** (importe anterior) | `<del>799 €</del>` |
| `<ins>` | subrayado | Contenido **añadido** (importe actual) | `<ins>549 €</ins>` |
| `<u>` | subrayado | Estilo visual | `<u>Entrega gratuita</u>` |
| `<sub>` | subíndice ₂ | Compuestos químicos | `H<sub>2</sub>O` |
| `<sup>` | superíndice ² | Medidas, referencias | `m<sup>2</sup>`, `pulgadas<sup>1</sup>` |

**¿Qué diferencia visual hay entre `<b>` y `<strong>`? ¿Y entre `<i>` y `<em>`?**
Ninguna diferencia: `<b>` y `<strong>` aparecen en negrita, mientras que `<i>` y `<em>` se muestran en cursiva.



# B4. El banner del streamer

| Condición | Etiqueta aplicada |
| :--- | :--- |
| `<h1>` con color de fondo lightblue | `<h1 style="background-color:lightblue;">` |
| `<h2>` alineado al centro | `<h2 style="text-align:center;">` |
| `<h3>` alineado a la derecha **y** fondo limegreen en un mismo style | `<h3 style="text-align:right; background-color:limegreen;">` |
| Bloque de texto en rojo | `<p style="color:red;">` |
| Bloque de texto en azul | `<p style="color:blue;">` |
| Bloque de texto con tamaño al 150 % | `<p style="font-size:150%;">` |


# B5. Paleta de colores de tu marca


## Parte 1

| Tono | Palabra clave | Valor RGB | Código HEX | Valor HSL |
| :--- | :--- | :--- | :--- | :--- |
| Rojo | `red` | `rgb(255, 0, 0)` | `#ff0000` | `hsl(0, 100%, 50%)` |
| Naranja | `orange` | `rgb(255, 165, 0)` | `#ffa500` | `hsl(39, 100%, 50%)` |


## Parte 2


| Consulta | Resultado | Verificación |
| :--- | :--- | :--- |
| Denominación oficial de `#3cb371` | **`mediumseagreen`** | Equivale a `rgb(60, 179, 113)` |
| Código hexadecimal de `rgb(238, 130, 238)` | **`#ee82ee`** | Su denominación es `violet` |


## Parte 3 (reflexión, también en un comentario del código)

**¿Qué significa `rgb(0, 0, 255)`?**
Ausencia de rojo, ausencia de verde y el valor máximo de azul: **azul puro** (`blue`, `#0000ff`).

**¿Qué *hue* corresponde en hsl al rojo, al verde y al azul?**
El matiz (*hue*) representa un grado dentro del círculo cromático:

| Tono | Ángulo (Hue) |
| :--- | :--- |
| Rojo | **0°** (o bien 360°) |
| Amarillo | 60° |
| Verde | **120°** |
| Cian | 180° |
| Azul | **240°** |
| Magenta | 300° |




# B6. El menú del ramen con tipografías de repuesto

# Fuentes en cascada

```html
<p style="font-family:'Fuente Inventada', Georgia, serif;">
```

El explorador revisa la lista **de izquierda a derecha** y aplica la **primera que encuentre disponible**. La opción final tiene que ser siempre una **familia genérica**, presente en cualquier sistema operativo.

| Sección del menú | Propiedad font-family | Familia genérica |
| :--- | :--- | :--- |
| Título | `'Brush Script MT', 'Comic Sans MS', cursive` | `cursive` (caligráfica) |
| Descripción | `Arial, Helvetica, sans-serif` | `sans-serif` (palo seco) |
| Precios | `'Courier New', Courier, monospace` | `monospace` (ancho fijo) |
| Bloque de prueba | `'Fuente Sakura Inventada', Georgia, serif` | `serif` (con gracias) |

## Las 5 familias genéricas

| Familia | Apariencia | Ejemplos | Aplicación habitual |
| :--- | :--- | :--- | :--- |
| `serif` | Con pequeños remates ("patitas") | Times New Roman, Georgia | Publicaciones impresas, prensa |
| `sans-serif` | Sin adornos, aspecto limpio | Arial, Verdana, Helvetica | Lectura en pantalla (estándar en la web) |
| `monospace` | Todos los caracteres ocupan el mismo ancho | Courier New, Consolas | Código fuente y cifras alineadas |
| `cursive` | Simula el trazo manual | Brush Script MT, Comic Sans MS | Únicamente encabezados breves |
| `fantasy` | Estilo ornamental | Impact, Papyrus | Únicamente encabezados breves |

## Respuesta a la pregunta (también en un comentario del código)
**¿Por qué debe ser fácil de leer el tipo de letra de un sitio web?**

Porque las webs están hechas para leerse. Una tipografía compleja fatiga la vista, provoca que el visitante abandone el sitio y dificulta la lectura a personas con baja visión o dislexia (**accesibilidad**). Además, una letra limpia se adapta bien a cualquier pantalla (móvil, tableta u ordenador). Las fuentes ornamentales deben reservarse solo para encabezados breves.


# B7. Cartel de festival con `<span>` y bordes
## La propiedad `border`
```css
border: grosor estilo color;
```

Los tres valores se dividen mediante **espacios** (sin usar comas) y su posición no importa, si bien lo normal es seguir el orden grosor-estilo-color.


| Condición | Regla aplicada |
| :--- | :--- |
| `<h1>` con contorno de 5 px, sólido y verde | `border:5px solid green;` |
| Bloque de texto con contorno punteado azul de 3 px | `border:3px dotted blue;` |
| Bloque de texto con fondo lightpink y contorno doble rojo de 5 px | `background-color:lightpink; border:5px double red;` |
| Nombre del artista en azul | `<span style="color:blue;">` |
| Nombre del artista en verde al 200 % | `<span style="color:green; font-size:200%;">` |

## Estilos de borde

| Propiedad | Apariencia |
| :--- | :--- |
| `solid` | Trazo continuo ─── |
| `dotted` | Sucesión de puntos ····· |
| `dashed` | Línea discontinua - - - |
| `double` | Trazo doble ═══ (requiere mínimo 3 px para apreciarse) |
| `groove` / `ridge` | Relieve 3D biselado (hundido / elevado) |
| `inset` / `outset` | Relieve 3D tipo botón (pulsado / saliente) |
| `none` | Sin contorno |

## Respuesta a la pregunta (también en un comentario del código)
**¿Qué diferencia hay entre `<span>` y `<p>` para destacar parte de un texto?**

| Característica | `<p>` | `<span>` |
| :--- | :--- | :--- |
| Categoría | Etiqueta de **bloque** | Etiqueta **en línea** |
| Comportamiento de línea | Inicia en una línea nueva | No provoca ningún salto |
| Espacio ocupado | Abarca todo el ancho disponible | Se ajusta solo al tamaño de su contenido |
| Aplicación habitual | Bloques de texto completos | Fragmentos concretos dentro de una oración |

# B8. Etiquetas anidadas: el mensaje urgente

```html
<h1>Aviso del servicio de ciberseguridad</h1>

<h2>Versión correcta</h2>
<p><b><i><u>Alerta: no descargues archivos adjuntos de remitentes desconocidos, pueden contener malware.</u></i></b></p>

<!--
  Cierre correcto: </u> </i> </b>
  Se cierran al revés de como se abren. La última etiqueta que abres (<u>) 
  tiene que ser la primera en cerrarse para que el código esté bien anidado.
-->

<h2>Versión mal cerrada</h2>
<p><b><i><u>Alerta: no descargues archivos adjuntos de remitentes desconocidos, pueden contener malware.</b></i></u> Este texto tendría que salir normal.</p>
```

**¿Qué hace el navegador en la versión mal cerrada?**
Aunque las etiquetas estén mal cerradas, el navegador corrige el fallo por su cuenta al cargar la página y el texto siguiente sale normal sin arrastrar la negrita, la cursiva ni el subrayado.



# Parte C. Práctica 1. Formato de texto

## Práctica 1 (UD2) - Formato de texto con HTML y CSS

### Reflexión previa
1. **Párrafos y justificación:** Se utiliza la etiqueta `<p>` junto con la propiedad CSS `text-align: justify;`.
2. **Marcar partes de un párrafo:** Se usan etiquetas en línea como `<i>`, `<b>` o `<span>`.
3. **Control de colores por sentimiento:** Creando una lista previa (o un comentario en el código) asociando cada sentimiento a un código de color hexadecimal concreto para consultarlo siempre.

### Código HTML

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="description" content="Práctica 1 de la UD2: formato de texto con HTML y CSS">
  <meta name="author" content="Pon aquí tu nombre">
  <title>Práctica 1 - Formato de texto</title>
</head>
<body style="background-color:#eaf2f8;">

  <!-- 
    Lista de colores por sentimiento:
    - Sentimiento 1: #1f618d
    - Sentimiento 2: #b03a2e
    - Sentimiento 3: #1e8449
    - Sentimiento 4: #b7950b
  -->

  <h2 style="text-align:center; border:1px solid #1f618d;">TÍTULO DEL TEXTO DEL ARCHIVO TXT</h2>

  <p style="text-align:justify;">Párrafo 1 del txt con <i>"comentarios entre comillas en cursiva"</i> y <b style="color:#1f618d;">sentimientos</b> en negrita y color.</p>

  <p style="text-align:justify;">Párrafo 2 del txt.</p>

  <p style="text-align:justify;">Párrafo 3 del txt.</p>

  <p style="text-align:justify;">Párrafo 4 del txt.</p>

  <p style="text-align:justify;">Párrafo 5 del txt.</p>

  <p style="text-align:justify;">Párrafo 6 del txt.</p>

  <p style="text-align:justify;">Párrafo 7 del txt.</p>

  <p style="text-align:justify;">Párrafo 8 del txt.<br><b style="color:#ffffff; background-color:#1f618d; font-size:200%;">ÚLTIMA FRASE DEL TXT EN MAYÚSCULAS.</b></p>
</body>
</html>
```
