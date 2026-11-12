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



| Requisito | Solución |
|---|---|
| Titular y entradilla | `<h1>` para el titular y `<h2>` para la entradilla |
| Tres párrafos con una línea entre el 2.º y el 3.º | Tres `<p>` y un `<hr>` entre el segundo y el tercero |
| Autor, fecha y fuente en tres líneas **solo con `<br>`, sin `<p>`** | Texto suelto en el `<body>` separado con `<br>` |
| Sección "Prueba de tamaños" | Un título y los encabezados `<h1>` a `<h6>` |
