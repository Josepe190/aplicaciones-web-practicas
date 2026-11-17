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
``Escritorio/
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
            ``

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
````

index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
<nav>
    <ul>
        <li>
    <a href="interiores/introduccion.html">Introduccion</a>
	<a href="interiores/trailer.html">Trailer</a>
	<a href="interiores/estreno.html">Fecha de estreno</a>
	<a href="interiores/estreno.html">Reparto</a>
	<a href="interiores/argumento.html">Argumento</a>
        </li>
    </ul>
</nav>
<a href="../strangerthings.html">
    ← Volver a Stranger Things
</a>
</body>
</html>
````

trailer.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
   <h1>Netflix lanzó su último avance teaser en mayo de este año. En el clip, nos llevan al laboratorio donde el Dr. Brenner realizó sus experimentos con niños, vistos por última vez en flashbacks en las temporadas uno y dos. Un reloj siniestro hace tic tac de fondo; los niños persiguen carros de juguete alrededor de una pista de arcoíris (¿recuerdan la habitación del arco iris de la segunda temporada?); alguien está jugando al ajedrez; una bola cae a través de alfileres en un tablero de clavijas; se dice "las señales apuntan a sí"; hay una risa infantil espeluznante; ladrillos de juguete; todo tiene mucho eco y está iluminado en el gris verdoso institucional que hemos llegado a esperar de las malas agencias gubernamentales experimentales.

Todos los niños tienen la cabeza rapada y batas de hospital como solía hacer Once en la primera temporada. Es evidente que hemos retrocedido en el tiempo porque vemos al Dr. Martin Brenner (desde atrás, pero se le reconoce en cualquier lugar) acechando los pasillos, y mientras la voz de Matthew Modine les dice a los niños: "Tenemos algo muy especial planeado para vosotros hoy", la cámara hace un zoom inquietante en una puerta marcada como '11'. El tráiler termina con la voz en off que dice: "¿Once? ¿Estás escuchando?". y los ojos de la joven Once se abren de repente por la sorpresa.</h1> 
<a href="../index.html">← Volver al inicio</a>
</body>
</html>
````

reparto.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>La serie no sería la serie que es sin su reparto, así que volverán a sus pantallas una vez más: Once (Millie Bobby Brown), Mike (Finn Wolfhard), Lucas (Caleb McLaughlin) , Dustin (Gaten Matarazzo), Will (Noah Schnapp), Max (Sadie Sink), Steve (Joe Keery), Nancy (Natalia Dyer), Jonathan (Charlie Heaton), Robin (Maya Hawke) y Joyce (Winona Ryder), entre otros.

Todos sabemos ahora que David Harbour regresará como Hopper, a pesar de ese final aparentemente trágico de la tercera temporada. En una charla con Total Film, Harbour explicó que su personaje "tenía que cambiar" y "resucitar de alguna manera", y agregó: "Así que veremos a un tipo muy diferente avanzando. El mismo tipo pero en una vena diferente. Es muy algo genial para poder jugar". Si bien aún no está claro cómo sobrevivió su personaje, Harbour ha revelado que la cuarta temporada revelará más de su historia en una llamada a la segunda temporada, donde Once encontró cajas en el ático de Hopper etiquetadas como "papá", "Vietnam" y "Nueva York".

Myles Truitt interpretará el papel del jugador de baloncesto de Hawkins, Patrick, cuya vida terminará "saliéndose de control" después de algunos "eventos impactantes", mientras que Amybeth McNulty interpretará a Vickie, descrita como "una banda nerd genial y de habla rápida que llama la atención de uno de nuestros queridos héroes ". "Fui una de las primeras personas de mi grupo de amigos en ver la primera temporada de Stranger Things", le dijo a The Times. "Cuando me seleccionaron, grité, lloré y me emocioné mucho".
</h1>
<a href="../index.html">← Volver al inicio</a>
</body>
</html>
````

introduccion.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>La temporada 4 de Stranger Things tiene algunas preguntas importantes que responder después del explosivo final de 77 minutos de la temporada 3, 'La batalla de Starcourt'. Pero no desesperen, amigos. La serie de ciencia ficción de Netflix regresará para la cuarta temporada, lo que significa que todos esos cabos sueltos por los que has estado perdiendo el sueño se resolverán. Sigue leyendo mientras nos ponemos nuestra ropa más brillante con un tema de los 80, enciende el electropop y sumérgete en todo lo relacionado con Hawkins, Indiana. Aquí está todo lo que necesitas saber sobre la cuarta temporada de Stranger Things.</h1>
    <a href="../index.html">← Volver al inicio</a>
</body>
</html>
````

estreno.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>Actualmente no hay una fecha de estreno oficial sobre la mesa, aunque ahora sabemos que la cuarta temporada no llegará hasta 2022. Un teaser reciente solo confirmó que regresará el próximo año, lo que es significativamente más tarde de lo que esperábamos. El productor Shawn Levy aprecia que la cuarta temporada esté tardando más de lo esperado, incluido él, pero promete que "vale la pena esperar". "Sólo diré que estamos muy retrasados, y los Duffers y yo queremos compartir la cuarta temporada con el mundo tanto como el mundo lo desee", dijo a The Hollywood Reporter. "Parte de lo que está tomando tiempo es mucho antes de que existieran COVID y la pandemia, la cuarta temporada se construyó para ser, con mucho, la temporada más ambiciosa, cinematográfica, extensa y épica que hayamos hecho".</h1>
   <a href="../index.html">← Volver al inicio</a>
</body>
</html>
````


argumento.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>"Honestamente, los guiones son geniales", dijo Natalia Dyer a The Independent cuando se le preguntó sobre los próximos episodios. "Cada vez que terminamos una temporada, todos pensamos, '¿A dónde va a ir esto? ¿A dónde puede ir esto?' Luego obtenemos los guiones para la próxima temporada y pensamos, '¡Dios mío, wow, como, wow!'. Ella agregó: "Va a ser realmente grande. ¡Va a ser grande!".

Hablando con MTV, Sink sonó igualmente emocionado: "Es una temporada increíble. Y la escala es tan enorme este año. Creo que la gente realmente la va a disfrutar". Matarazzo también habló sobre cómo ha cambiado la serie en la cuarta temporada con Entertainment Tonight. "Cuando se trata del tono de la temporada, definitivamente, creo que el tono definitivamente ha madurado, y creo que ellos [los creadores Matt y Ross Duffer] lo hacen a propósito porque creo que quieren que su serie madure con su niños", explicó. "A medida que envejecemos como personas, tenemos que envejecer como personajes. Se enfrentan a este problema, pero lo abrazan y lo usan para su ventaja. Y no se asustan cuando nos hacemos más altos o cuando nuestras voces bajan o algo por el estilo. Lo usan y lo usan como munición para su escritura. Es increíble lo que pueden hacer. Trabajar con ellos, es simplemente excepcional. Siempre lo ha sido".

La tercera temporada concluyó con una nota extremadamente emocional. Joyce, Will y Jonathan empacaron su casa en Hawkins y se subieron a una camioneta de mudanzas con Once a cuestas después de la muerte de Hopper (que en realidad no fue una muerte)."No todo son buenas noticias para nuestro 'estadounidense'; está encarcelado lejos de casa en el páramo nevado de Kamchatka, donde enfrentará peligros tanto humanos ... como de otro tipo", se lee en la sinopsis oficial de Netflix. "Mientras tanto, de vuelta en los Estados Unidos, un nuevo horror está comenzando a aflorar, algo enterrado hace mucho tiempo, algo que conecta todo ...".</h1>
<a href="../index.html">← Volver al inicio</a>
</body>
</html>
````
