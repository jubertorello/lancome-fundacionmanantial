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

- **Mulish** — la tipografía de Fundación Manantial. Es la de toda la
  página: titulares, cuerpo, botones, navegación y la cita.
- **Archivo** (ancho condensado, peso 800) — exclusivamente para el lockup
  del claim, que funciona como logo. Desaparece en cuanto llegue el logo de
  campaña en SVG, y entonces la landing se queda con una sola familia.

Había una tercera, Bodoni Moda, para el wordmark LANCÔME y la cita. El
wordmark pasó a ser el PNG oficial y la cita a Mulish, así que ya no la
usaba nadie y se ha retirado también de la descarga.

## Color: cada uno tiene un trabajo

No hay cuotas de color, hay papeles. La regla es que **cuando la página se
pone azul o arena, es que habla Fundación Manantial**.

| Color | Hex | Papel |
|---|---|---|
| Rosa | `#EE4B98` | **Solo** el claim «or maybe not», los asteriscos, el cursor del claim y las frases de «lo que no decimos» |
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
| URL del cuestionario | `const FORM_URL` al final de `index.html` — alimenta los 6 CTA. **Ahora apunta provisionalmente a lancome.es** |
| Logo oficial de Fundación Manantial | los `<svg class="fm-mark">` (ahora hay un trazado provisional) |
| Ruta final de alojamiento | prevista `fundacionmanantial.org/lancome` |
| Fotografía | carpeta `img/` — ver nombres abajo |
| Vídeo de embajadoras | bloque `.hero` y sección `#voces` |
| Historias reales de Voces | array `VOCES` en el script: imagen y frase de cada una. **Las frases actuales son de campaña, no testimonios**: hay que sustituirlas por lo que digan de verdad las mujeres que aparezcan, y con sus caras |
| Artículos de Lancôme | títulos y URLs reales en `#articulos` |
| **«1 de cada 3 mujeres»** | Sección `.dato`, entre la colaboración y el cuestionario. Ya no es una línea dentro de un desplegable: es **la afirmación más grande de la página**, a todo el ancho y en cuerpo de 78 px. **Necesita fuente citable antes de publicar.** Si no se puede sostener, la banda se quita entera. |
| Export vertical del spot | Resuelto a medias: ya hay un export ligero de 720p para móvil (3,7 MB). Pero el spot es 16:9 y el hero ocupa toda la pantalla, así que en vertical se recorta por los lados. Si el cliente tiene una versión 9:16, mejor esa |
| Foto `manos.webp` sin usar | Salió de la sección de la colaboración; sigue en `img/` por si se reutiliza |
| Resto de datos de prevalencia | `#colaboracion` y las cifras de `#fundacion` — verificar fuentes antes de publicar |

## Vídeo

El spot de campaña, 57 s, con las embajadoras y locución en español. Hay
dos exports del mismo máster y la página elige uno:

| Fichero | Medidas | Peso | Cuándo |
|---|---|---|---|
| `video/manifiesto.mp4` | 1920×1080 | 7,1 MB | pantallas de más de 900 px |
| `video/manifiesto-movil.mp4` | 1280×720 | 3,7 MB | pantallas de 900 px o menos |
| `video/manifiesto-poster.webp` | 1280×720 | 10 KB | cartel del modal |

La decisión se toma una sola vez, en `const VIDEO_SRC` del `<script>`, y la
comparten el fondo del hero y el modal: lo que se descarga sirve para los
dos y no se pide nada dos veces. El corte está en los mismos 900 px que usa
la hoja de estilos, para no inventar un segundo punto de ruptura.

**Ya tiene sonido.** Durante meses el máster venía mudo; este no. El fondo
del hero va silenciado y en bucle, como debe ser para autoarrancar, y el
modal de «Ver el vídeo» lo abre con controles y con voz.

### De dónde salen estos ficheros

El máster del cliente —`DG133869_SP_LANCOME_LACAUSA_MEDIA_TRADUCCION_TAG_57S_16X9.mp4`,
65 MB a 9,3 Mbps— es un fichero de emisión, no de web. No está en el repo:
pesa diez veces lo que la página entera. Para rehacer los exports:

```bash
# escritorio
ffmpeg -i MASTER.mp4 -vf scale=1920:-2 \
  -c:v libx264 -crf 25 -preset slow -profile:v high -pix_fmt yuv420p \
  -movflags +faststart -c:a aac -b:a 128k -ac 2 video/manifiesto.mp4

# móvil
ffmpeg -i MASTER.mp4 -vf scale=1280:-2 \
  -c:v libx264 -crf 25 -preset slow -profile:v high -pix_fmt yuv420p \
  -movflags +faststart -c:a aac -b:a 128k -ac 2 video/manifiesto-movil.mp4

# cartel (fotograma 180: Christy Turlington abriendo la pieza)
ffmpeg -i MASTER.mp4 -vf "select=eq(n\,180),scale=1280:-2" -frames:v 1 p.png
cwebp -q 72 p.png -o video/manifiesto-poster.webp
```

`+faststart` es importante: pone el índice del MP4 al principio para que
empiece a verse mientras se descarga. Sin eso, el navegador se traga el
fichero entero antes de pintar nada.

### Lo que hay que mirar

- **El spot es casi todo fondo blanco.** De fondo del hero funciona porque
  las capas oscuras de `.hero::before` y `.hero::after` lo asientan. Si
  alguien las toca, el texto blanco del claim deja de leerse.
- **Es 16:9 y el hero ocupa la pantalla entera.** En vertical se recorta
  mucho por los lados: queda el centro, que es donde están las caras, pero
  si el cliente manda un export vertical, mejor ese para móvil.
- Al llegar al final, el bucle vuelve a empezar desde la cartela de
  Lancôme. Se nota poco porque son 57 s, pero está ahí.

### ¿YouTube o alojado?

Alojado. Un embed de YouTube traería el reproductor completo, su marca, sus
cookies y el consentimiento que eso obliga a pedir en el sitio de una
fundación de salud mental. 7 MB servidos desde el propio dominio no tienen
ninguna de esas contrapartidas.

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
