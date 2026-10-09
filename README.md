# I'm Fine. Or Maybe Not.

Landing de la colaboración **Lancôme × Fundación Manantial**.

Campaña de prevención y visibilización de los problemas de salud mental en
mujeres. El objetivo de la página es una sola conversión: que se complete el
cuestionario. Todos los CTA principales apuntan ahí.

Se alojará en [fundacionmanantial.org](https://www.fundacionmanantial.org/),
enlazada desde un botón de la web principal.

## En revisión

**https://lancome-fundacionmanantial-chi.vercel.app**

Desplegada desde este repositorio: cada push a `main` la actualiza sola.

El repositorio es **público**. No por preferencia, sino porque el plan
Hobby de Vercel no despliega commits de un autor distinto al dueño de la
cuenta cuando el repositorio es privado, y el proyecto vive en una cuenta
distinta a la que firma los commits. Al abrirlo, esa restricción
desaparece.

Conviene tenerlo presente: dentro hay fotografía de Lancôme con la
licencia aún por confirmar, los logos y la campaña sin publicar. Si en
algún momento hay que cerrarlo, basta con volver a ponerlo privado y
mover el proyecto de Vercel a la cuenta de `jubertorello`, que es la que
coincide con el autor de los commits.

No se indexa: lleva `noindex, nofollow` en el `<head>`, porque es material
de campaña sin publicar y con fotografía de Lancôme cuya licencia para este
dominio está por confirmar. **Hay que retirarlo al aprobarla.**

No hay `robots.txt` a propósito. Bloquear el rastreo y pedir `noindex` a la
vez se estorban: si el buscador no puede entrar, nunca lee la etiqueta, y la
URL puede acabar listada igual como enlace pelado. Dejando rastrear, el
`noindex` hace su trabajo.

La URL es pública para quien la tenga. Si hace falta cerrarla del todo
mientras la ven Lancôme y la fundación, en Vercel se activa protección
por contraseña desde los ajustes del proyecto.

## Stack

HTML + CSS + JavaScript, sin dependencias ni build. Un único archivo
(`index.html`) con los estilos y el script en línea. La única carga externa son
las fuentes de Google Fonts.

Todas las rutas de imagen son **relativas** (`img/...`), así que la carpeta
entera se puede subir tal cual a `fundacionmanantial.org/lancome` sin tocar
una sola línea.

## Tipografía

**Mulish**, y solo Mulish. Es la tipografía de Fundación Manantial, y la
landing vive en su dominio, así que la voz de la página es la suya:
titulares, cuerpo, botones, navegación y rótulos.

Hubo dos más y las dos se han ido. **Bodoni Moda** sostenía el wordmark
LANCÔME hasta que llegó el PNG oficial. **Archivo** condensada sostenía el
claim hasta que llegó el logotipo de campaña: era lo más parecido que se
podía componer sin el original. Ahora el claim es el logotipo de verdad en
SVG, así que Archivo sobra y se ha retirado también de la descarga.

## El logotipo de campaña

`img/logo-imfine.svg` — 3 KB, trazado desde el original de Illustrator.

Las tres palabras son **grupos independientes** (`.imf-im`, `.imf-not`,
`.imf-fine`), por eso se pueden animar por separado. «NOT» va primero en el
marcado porque en el original queda **detrás**: «I'M» y «FINE» lo pisan, y
ese solape es el gesto entero de la campaña. El negro va en `currentColor`,
así que hereda el blanco sobre el hero y la tinta sobre el papel.

Está incrustado en el HTML, no enlazado, en el hero y en el cierre: así la
hoja de estilos puede animar sus grupos. En el hero entra con la carga
—«I'M» y «FINE» barren de izquierda a derecha y «NOT» se enfoca después,
saliendo de detrás— y en el cierre lo dispara el observador al llegar.

**No lleva paréntesis.** Durante meses escribimos «I'M (NOT) FINE» porque
el claim se componía con tipografía y los paréntesis separaban las tres
palabras. En la marca no existen: lo que separa a «NOT» es que está en otro
color y en otro plano. Se han quitado del título, de la descripción y de
los textos alternativos.

Para la marquesina, que es una tira de 53 px, el stacked no cabe: ahí va el
lockup horizontal, `img/logo-imfine-h.png` sobre fondo claro y
`img/logo-imfine-h-negativo.png` sobre oscuro.

## Color: cada uno tiene un trabajo

No hay cuotas de color, hay papeles. La regla es que **cuando la página se
pone azul o arena, es que habla Fundación Manantial**.

| Color | Hex | Papel |
|---|---|---|
| Rosa | `#B14860` | El rosa de marca, medido en los PNG oficiales del logotipo. Es la voz de la duda: el «NOT» del lockup, los rótulos de sección, las frases de «lo que no decimos», los desplegables de ansiedad y depresión |
| Granate | `#5C0B1B` / `#8E1230` | El mundo Lancôme: hero, cuestionario, cierre |
| Azul | `#004591` | La voz de Fundación Manantial |
| Arena | `#EAE6E0` | La superficie de los bloques de la fundación |

Azul y arena están tomados directamente de fundacionmanantial.org, no
aproximados a ojo.

Van en azul macizo, con texto en blanco: **la cita de la fundación** y **el
bloque de cifras institucionales**. Son los dos momentos en los que la
fundación habla en primera persona, y por eso son bloques enteros de color
y no detalles.

Van sobre arena, con rótulos azules: «lo comprobamos todo menos cómo
estamos», «cómo entendemos la salud mental desde FM» y el bloque
institucional con sus proyectos.

Y en azul suelto: los datos de los objetivos y su filete superior, los CTA
secundarios, los títulos de columna del pie, los teléfonos de ayuda y la
línea inferior de la cabecera.

El rosa está muy restringido a propósito. Mirando la web de Lancôme, su
sistema es blanco y negro y el color queda para los fondos y para la propia
campaña; si el rosa se reparte por hovers, rótulos y detalles deja de
señalar la duda y pasa a ser decoración.

Todo lo que antes era rosa y no era campaña —el foco del teclado, los
hovers de botones y enlaces, los rótulos de los mensajes, «¿Cómo estoy? ·
Silencio»— es ahora azul de la fundación.

Jerarquía de botones, sin rosa: negro relleno para el CTA principal, blanco
sobre la barra fija, azul con filete para los secundarios de FM. Todos pasan
a azul al posarse encima.

## Reglas de marca

- El claim va **siempre en inglés**: I'M FINE · OR MAYBE NOT. El resto de la
  página está en castellano.
- El logo de **Fundación Manantial va a la izquierda de la navegación**, por
  delante del lockup de campaña: la landing se aloja en su dominio.
- **Firma de la colaboración**: donde aparecen juntos los dos logos —el
  hero y el pie— los acompaña siempre «Juntos en la prevención de los
  problemas de salud mental de las mujeres». No es un pie de crédito
  genérico: es el claim de la alianza.
- El crédito vive **dentro del hero**, como pie de la portada. Sobre oscuro los dos logos van en blanco puro
  (`filter: brightness(0) invert(1)`), que es el negativo estándar de ambas
  marcas. Si alguna tiene versión en negativo propia, sustituirla.
- Los tres bloques oscuros tienen imagen propia, ninguna se repite: la rosa
  en el hero, el sello en el cuestionario y otra vez el sello —con menos
  desenfoque, para que se lea el relieve— firmando el cierre.
- La rosa va **siempre muy desenfocada**, como atmósfera y nunca como
  fotografía legible (`.bgimg--blur`, `.bgimg--soft`). El cierre es la
  excepción deliberada: ahí el sello sí debe reconocerse (`.bgimg--seal`).

## Movimiento

El claim tiene dos registros distintos a propósito:

- **«I'M FINE» se teclea**, rápido y mecánico, con cursor. Es lo que
  mandas por chat: deliberado, automático, la respuesta que damos sin
  pensar.
- **«*or maybe not» no se teclea.** Es el pensamiento de debajo, así que
  aparece entero, desenfocado, y va enfocándose. Nadie teclea lo que
  piensa por dentro.

Entre los dos hay una pausa de 620 ms. El silencio forma parte de la
frase. El asterisco tampoco aparece hasta que la primera está dicha.

Si los dos se escribieran igual quedarían al mismo nivel y el claim
perdería justamente la tensión que lo sostiene.

El resto del movimiento es discreto y siempre al servicio del contenido:
titulares que suben desde debajo de una línea, rejillas escalonadas, fotos
que se posan, la rosa del hero a menor velocidad que la página, y la lista
de «Compruebas» cayendo uno a uno hasta el silencio final.

El movimiento va ocurriendo **a medida que se hace scroll**: cada bloque se
anima cuando entra en pantalla, no antes.

La red de seguridad que evita que algo se quede invisible está acotada a lo
que ya está a la vista o por encima. Antes revelaba la página entera a los
2,5 s y eso disparaba todas las animaciones fuera de pantalla: el
movimiento existía, pero al llegar scrolleando ya estaba todo quieto.

Todo respeta `prefers-reduced-motion`, que deja la página quieta y legible.

**Contrapartida a tener en cuenta:** durante los primeros ~2,5 s el claim se
está escribiendo, así que una captura automática o la miniatura de una
previsualización pueden pillarlo a medias. Si molesta, basta con bajar
`data-speed` en los dos `<span class="tw">` del hero.

Para verlo: abre `index.html` en el navegador, o sirve la carpeta como estático.

```bash
python3 -m http.server 8000
```

## Qué hay que rellenar antes de publicar

| Pendiente | Dónde |
|---|---|
| **Confirmar el texto legal del alta** | El formulario de «Quiero estar informado» envía a Mailchimp (lista `238a2f7b10` de `fundacionmanantial.us18`). Lleva casilla de consentimiento obligatoria enlazando a `/politica-de-privacidad/`. Conviene que lo valide quien lleve protección de datos en la fundación: puede que quieran su propia redacción |
| **Dos versiones del mismo claim** | El pie dice «**Por** la prevención…» y el hero y la sección de la colaboración siguen diciendo «**Juntos** en la prevención…». El documento de cambios solo tocaba el pie; confirmado con la clienta que de momento se queda así. Conviene unificarlo antes de publicar |
| **QUITAR EL `noindex` AL PUBLICAR** | `<meta name="robots">` en el `<head>` de `index.html`. Es lo único que controla la indexación. No hay `robots.txt`: en `fundacionmanantial.org/lancome` sería inerte —los buscadores solo leen el de la raíz del dominio— y en la URL de revisión estorbaba, porque bloquear el rastreo impide que Google llegue a leer el propio `noindex` |
| **El contador del cuestionario es una MAQUETA** | `data-sim-desde` en `index.html` + el bloque «MAQUETA» del `<script>`. Sube solo de 6.457 a 7.000 y esos incrementos **no corresponden a nadie**. Está así para que el cliente vea el efecto en la URL de revisión. **No puede salir a `fundacionmanantial.org/lancome` tal cual:** o se alimenta con el número real que dé la Fundación, o se revierte al contador con dato fijo (commit `e0fe751`). |
| Logo oficial de Fundación Manantial | los `<svg class="fm-mark">` (ahora hay un trazado provisional) |
| Ruta final de alojamiento | prevista `fundacionmanantial.org/lancome` |
| Fotografía | carpeta `img/` — ver nombres abajo |
| Voces, oculta de momento | La sección está comentada en `index.html`, con su carrusel y sus estilos intactos. Para devolverla hay que quitar el comentario **y** sustituir el array `VOCES` del script: las frases que hay son de campaña, no testimonios |
| Artículos, ocultos de momento | También comentados, a petición del cliente: los artículos se leen en la web de Lancôme. Para devolverlos, quitar el comentario y poner títulos y URLs reales |
| **«1 de cada 3 mujeres»** | Sección `.dato`, entre la colaboración y el cuestionario. Ya no es una línea dentro de un desplegable: es **la afirmación más grande de la página**, a todo el ancho y en cuerpo de 78 px. **Necesita fuente citable antes de publicar.** Si no se puede sostener, la banda se quita entera. |
| Export vertical del manifiesto | El spot del modal ya viene en 9:16 y llena el teléfono. El manifiesto del fondo del hero no: es 16:9 contra una pantalla vertical, así que se recorta por los lados. Si el cliente tiene una versión 9:16 de los 57 s, mejor esa |
| Foto `manos.webp` sin usar | Salió de la sección de la colaboración; sigue en `img/` por si se reutiliza |
| Resto de datos de prevalencia | `#colaboracion` y las cifras de `#fundacion` — verificar fuentes antes de publicar |

## Enlaces de salida

Todo lo que sale de la landing va a dos sitios, y los dos abren en pestaña
aparte para no perder a quien está leyendo:

| Desde | A |
|---|---|
| Los 6 CTA del cuestionario | `https://www.imfine.com/es-es/evalua-tu-salud-mental` |
| «Descubre los recursos», en `#recursos` | `https://www.imfine.com/es-es/recursos` |
| «Quiero colaborar» (×2) | `fundacionmanantial.org/colaborar-en-salud-mental/` |
| «Sobre Fundación Manantial», en el pie | `fundacionmanantial.org/salud-mental/` |
| «Proyectos» y las 4 fichas | `fundacionmanantial.org/servicios-*` |
| Las 4 marcas de Lancôme (cabecera, firma del hero, pie ×2) | `https://www.imfine.com/ES-ES` |
| Las 3 marcas de Fundación Manantial | `fundacionmanantial.org` |

Los CTA no llevan la URL escrita en el HTML: la reparte `const FORM_URL`,
al principio del `<script>`. **Para cambiar el destino del cuestionario se
toca esa línea y nada más.** Si algún día el formulario vive en el mismo
dominio que la landing, el código lo detecta y deja de abrir en pestaña
nueva, sin tener que tocar los enlaces uno a uno.

## Vídeo

Son **dos piezas distintas**, no dos tamaños de la misma:

- **El manifiesto**, 57 s. Va de fondo del hero, mudo y en bucle. Es
  atmósfera: nadie lo ve entero ahí.
- **El spot**, 17 s. Es el que se abre al pulsar «Ver el vídeo», con voz y
  con controles. Está montado para verse de una sentada.

De cada pieza hay dos exports y la página elige uno por el ancho:

| Fichero | Medidas | Peso | Cuándo |
|---|---|---|---|
| `video/manifiesto.mp4` | 1920×1080 | 7,1 MB | fondo del hero, >900 px |
| `video/manifiesto-movil.mp4` | 1280×720 | 3,7 MB | fondo del hero, ≤900 px |
| `video/spot-horizontal.mp4` | 1920×1080 | 1,8 MB | modal, >900 px |
| `video/spot-vertical.mp4` | 1080×1920 | 3,1 MB | modal, ≤900 px |
| `video/spot-*-poster.webp` | — | 10 KB | cartel del modal |

En el spot el corte no es solo peso: la versión de móvil está **montada en
vertical, 9:16**, así que llena el teléfono en lugar de quedarse en una
franja. Por eso el modal cambia de forma en móvil —manda la altura y el
ancho se ajusta solo, y la caja se encoge con el vídeo para que el aspa de
cerrar siga pegada a su esquina.

Todo se decide en `const MOVIL` del `<script>`, en los mismos 900 px que
usa la hoja de estilos, para no inventar un segundo punto de ruptura.

**Tienen sonido.** El fondo del hero va silenciado, como exige el
autoarranque; el modal lo abre con voz.

`video/manifiesto-poster.webp` ya no se usa en la página: el modal ahora
pone el cartel del spot. Se queda por si vuelve a hacer falta.

### De dónde salen estos ficheros

Los másteres del cliente son ficheros de emisión, a 8-9 Mbps, y **no están
en el repo**: el del manifiesto pesa 65 MB, diez veces la página entera.
Para rehacer los exports:

```bash
# el manifiesto, fondo del hero
ffmpeg -i MASTER_57S_16X9.mp4 -vf scale=1920:-2 \
  -c:v libx264 -crf 25 -preset slow -profile:v high -pix_fmt yuv420p \
  -movflags +faststart -c:a aac -b:a 128k -ac 2 video/manifiesto.mp4
ffmpeg -i MASTER_57S_16X9.mp4 -vf scale=1280:-2 \
  -c:v libx264 -crf 25 -preset slow -profile:v high -pix_fmt yuv420p \
  -movflags +faststart -c:a aac -b:a 128k -ac 2 video/manifiesto-movil.mp4

# el spot, el del modal. Ya vienen a 1080: no se reescala, solo se comprime
ffmpeg -i MASTER_15S_16X9.mp4 \
  -c:v libx264 -crf 25 -preset slow -profile:v high -pix_fmt yuv420p \
  -movflags +faststart -c:a aac -b:a 128k -ac 2 video/spot-horizontal.mp4
ffmpeg -i MASTER_15S_9X16.mp4 \
  -c:v libx264 -crf 25 -preset slow -profile:v high -pix_fmt yuv420p \
  -movflags +faststart -c:a aac -b:a 128k -ac 2 video/spot-vertical.mp4

# carteles
ffmpeg -i video/spot-horizontal.mp4 -vf "select=eq(n\,40),scale=1280:-2" -frames:v 1 p.png
cwebp -q 72 p.png -o video/spot-horizontal-poster.webp
```

`+faststart` es importante: pone el índice del MP4 al principio para que
empiece a verse mientras se descarga. Sin eso, el navegador se traga el
fichero entero antes de pintar nada.

### Si en un teléfono sale la rosa y no el vídeo

No es un fallo. El export de móvil es H.264 High@3.1, 720p, yuv420p: eso
lo reproduce cualquier teléfono de los últimos diez años. Lo que pasa es
que hay tres puertas, y las tres las ha abierto quien mira:

| Ajuste | Dónde | Qué hace |
|---|---|---|
| Reducir movimiento | Accesibilidad | la página lo consulta y no pide el vídeo |
| Modo de bajos datos / Ahorro de datos | iOS / Android | igual: no se pide el vídeo |
| **Modo de bajo consumo** | iOS, batería | Safari deja de autoarrancar vídeo y ni lo precarga |

El tercero es el más frecuente con diferencia, y el único que no se puede
consultar: no hay bandera que leer, simplemente `play()` no prospera. Si
alguien reporta que «no le carga», lo primero es preguntar si lleva el
teléfono en ahorro de batería.

En los tres casos queda la rosa, que para eso está: es el fondo de verdad
de la sección, no un hueco de carga.

Se puede forzar el vídeo al primer toque de pantalla —en ese momento el
navegador ya lo permite—, pero no se hace a propósito: los tres ajustes
son una petición explícita de quien visita la página.

### Lo que hay que mirar

- **Las piezas son casi todo fondo blanco.** El manifiesto funciona de
  fondo del hero porque las capas oscuras de `.hero::before` y
  `.hero::after` lo asientan. Si alguien las toca, el texto blanco del
  claim deja de leerse.
- **El manifiesto es 16:9 y el hero ocupa la pantalla entera**, así que en
  vertical se recorta por los lados: queda el centro, que es donde están
  las caras. Si llega un export 9:16 del manifiesto —como el que ya hay del
  spot—, ese sería mejor para el fondo en móvil.
- Al llegar al final, el bucle del hero vuelve a empezar desde la cartela
  de Lancôme. Se nota poco porque son 57 s, pero está ahí.

### ¿YouTube o alojado?

Alojado. Un embed de YouTube traería el reproductor completo, su marca, sus
cookies y el consentimiento que eso obliga a pedir en el sitio de una
fundación de salud mental. Unos megas servidos desde el propio dominio no
tienen ninguna de esas contrapartidas.

Si algún día se suben los testimonios de Voces —piezas largas y varias—, ahí
sí conviene YouTube o Vimeo: bitrate adaptativo, subtítulos gestionables y
ancho de banda que no paga la fundación. En ese caso, embeber con fachada
(un cartel que solo carga el iframe al pulsar) y usar `youtube-nocookie.com`.

## Imágenes

Los huecos son progresivos: si el archivo no existe se ve un hueco etiquetado,
y en cuanto aparece, la foto entra sola. Nombres esperados en `img/`:

```
rosa-macro.jpg        fondo del hero y del cierre
sello-rosa.jpg        fondo del bloque de cuestionario
cama.jpg              banda «¿Y si te has acostumbrado a estar así?»
retrato-rosa.jpg      bloque de colaboración
mujer-escribiendo.jpg
cuenco.jpg            los tres artículos
madre-bebe.jpg
retrato-1..4.jpg      sección de voces
retrato-fm.jpg        bloque institucional
```

Comprobar que la licencia del banco de imágenes de Lancôme cubre el alojamiento
en el dominio de Fundación Manantial.

## Contenido y tono

Los copys salen del documento de campaña. El tono no diagnostica ni presupone
que la persona esté mal: parte de algo cotidiano y abre una duda pequeña.
El cuestionario se presenta siempre como herramienta de prevención y
autoobservación, nunca como diagnóstico.

El pie incluye el **024** (atención a la conducta suicida) y el **112**.

## Responsive

Auditado, no solo escrito. Puntos de ruptura en 820, 700, 560, 420 y 400.

### El ancho nunca supera la pantalla

Comprobado a 320, 375, 414, 768, 1024 y 1470 px **desactivando
temporalmente `overflow-x`**, que es la única forma de medirlo de verdad:
con esa propiedad puesta, el desbordamiento no desaparece, solo se
esconde. Desborde real en los seis anchos: 0.

Aparte hay tres redes, por orden de importancia:

1. Que nada sea más ancho que la pantalla. Es la que cuenta.
2. `overflow-x: clip` en `html` y `body`, con `hidden` de respaldo para
   navegadores antiguos. Se prefiere `clip` porque, a diferencia de
   `hidden`, no crea un contenedor de scroll y no interfiere con la
   cabecera pegajosa.
3. `max-width: 100%` en `img`, `svg` y `video`.

Para volver a auditarlo tras cualquier cambio, en la consola del
navegador: poner `document.body.style.overflowX='visible'` y comparar
`document.documentElement.scrollWidth` con `clientWidth`.

Lo que se corrigió al probarlo de verdad:

- **Lancôme desaparecía entero en móvil.** Una regla pensada para despejar
  la cabecera ocultaba `.lan-logo` en toda la página: cabecera, crédito del
  hero y las dos apariciones del pie. Ahora se encoge, nunca se oculta.
- **La cabecera se salía 20 px** y `overflow-x:hidden` lo estaba tapando. A
  375 px necesita 350 y cabe; también en 360.
- **Trece objetivos táctiles por debajo de 44 px**, entre ellos enlaces del
  pie de 22 px de alto. Los logos, que también son enlaces, llevan relleno
  para crecer sin moverse.
- **Veinticinco rótulos a 10 px**, que en la mano no se leen. Suben a 11.
  Se mantiene a 10 solo la etiqueta del botón de cabecera: es el precio de
  que quepan las dos marcas, y en un botón en negrita y versales aguanta.
- **«Lo que decimos / lo que no decimos» deja de ser tarjetas en móvil**
  y pasa a lista desplegable con un chevron por fila. El bloque baja de
  unos 1.900 px a 298. Se probó antes con el asterisco de campaña, que
  encajaba con la marca pero no decía «esto se abre», que es lo único que
  ese elemento tiene que comunicar.
- **La barra fija ocupaba 121 px** de los 812 de pantalla porque el titular
  se partía en tres líneas. En móvil se queda solo el botón, a 68 px.
- **«*or maybe not» se quedaba en 20 px** frente a los 46 del claim. Sube a
  28: es la mitad de la frase, no una nota al pie.
- El rótulo del vídeo se montaba encima del subtítulo quemado del clip.
- Las media queries de cabecera estaban **antes** que el bloque general de
  700 px y la cascada las pisaba. Reordenadas.

## Estructura

1. Banner — claim y vídeo
2. Abrimos la duda — «lo que decimos / lo que no decimos»
3. Lo comprobamos todo menos cómo estamos
4. Cuestionario (bloque protagonista)
5. Colaboración Lancôme + Fundación Manantial
6. Fundación Manantial — mirada, casa y proyectos
7. Artículos Lancôme
8. Voces
9. Cierre → cuestionario

El punto 6 unifica lo que el documento de campaña separaba en dos: «cómo
entendemos la salud mental desde FM» y «quiénes somos». Eran dos bloques
de arena separados por los artículos y las voces que empezaban los dos
diciendo «Fundación Manantial», así que repetían territorio y partían en
dos la única voz institucional de la página.

Unificados, el bloque va de lo que la fundación piensa a lo que hace:
titular y entradilla, tres pilares —prevención, normalización,
conversación—, el dato de quiénes son con sus cifras y sus dos CTA, y los
proyectos al final.
