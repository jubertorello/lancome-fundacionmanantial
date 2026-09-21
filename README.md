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

No se indexa. Lleva `noindex, nofollow` y un `robots.txt` cerrado porque
es material de campaña sin publicar y con fotografía de Lancôme cuya
licencia para este dominio está por confirmar. **Las dos cosas hay que
retirarlas al aprobarla.**

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
| **El contador del cuestionario es una MAQUETA** | `data-sim-desde` en `index.html` + el bloque «MAQUETA» del `<script>`. Sube solo de 6.457 a 7.000 y esos incrementos **no corresponden a nadie**. Está así para que el cliente vea el efecto en la URL de revisión. **No puede salir a `fundacionmanantial.org/lancome` tal cual:** o se alimenta con el número real que dé la Fundación, o se revierte al contador con dato fijo (commit `e0fe751`). |
| URL del cuestionario | `const FORM_URL` al final de `index.html` — alimenta los 6 CTA. **Ahora apunta provisionalmente a lancome.es** |
| Logo oficial de Fundación Manantial | los `<svg class="fm-mark">` (ahora hay un trazado provisional) |
| Ruta final de alojamiento | prevista `fundacionmanantial.org/lancome` |
| Fotografía | carpeta `img/` — ver nombres abajo |
| Vídeo de embajadoras | bloque `.hero` y sección `#voces` |
| Historias reales de Voces | array `VOCES` en el script: imagen y frase de cada una. **Las frases actuales son de campaña, no testimonios**: hay que sustituirlas por lo que digan de verdad las mujeres que aparezcan, y con sus caras |
| Artículos de Lancôme | títulos y URLs reales en `#articulos` |
| **«1 de cada 3 mujeres»** | Sección `.dato`, entre la colaboración y el cuestionario. Ya no es una línea dentro de un desplegable: es **la afirmación más grande de la página**, a todo el ancho y en cuerpo de 78 px. **Necesita fuente citable antes de publicar.** Si no se puede sostener, la banda se quita entera. |
| Foto `manos.webp` sin usar | Salió de la sección de la colaboración; sigue en `img/` por si se reutiliza |
| Resto de datos de prevalencia | `#colaboracion` y las cifras de `#fundacion` — verificar fuentes antes de publicar |

## Vídeo

`video/manifiesto.mp4` — 8 s, 720p, con subtítulos quemados en inglés.

No se autocarga. La página muestra el póster (105 KB) y solo pide el mp4
cuando alguien pulsa play. Es lo correcto mientras el archivo pese lo que
pesa.

### Pendiente: comprimir

El máster viene a 15,5 Mbps, que es bitrate de edición, no de web. Lo he
bajado a 720p con `avconvert` (la herramienta del sistema, sin control de
bitrate) y se queda en 6,7 MB. Con ffmpeg baja a ~1 MB sin pérdida visible:

```bash
ffmpeg -i video/manifiesto-master.mp4 -vf scale=1280:-2 \
  -c:v libx264 -crf 26 -preset slow -profile:v high \
  -movflags +faststart -c:a aac -b:a 96k video/manifiesto.mp4
```

Conserva el audio. El máster actual no lo tiene —ver abajo— pero el día que
llegue un export con voz, este comando no lo tira.

### El archivo actual no tiene sonido

Comprobado de dos formas: leyendo los átomos del MP4, que solo declaran una
pista `vide`, y reproduciéndolo en el navegador, donde
`webkitAudioDecodedByteCount` se queda en 0 con el volumen al máximo y sin
silenciar.

No se perdió al comprimir: el máster ya venía mudo del programa de edición.
El reproductor de la página pide sonido —sin `muted`, con controles y
lanzado por un clic, que es lo que los navegadores exigen para permitir
audio—, así que **en cuanto se sustituya el archivo por un export con voz,
sonará sin tocar una línea de código**.

Una vez por debajo de ~1,5 MB se puede pasar a autoplay silenciado en
bucle, que como hook funciona mucho mejor que un play manual.

### ¿YouTube o alojado?

Para este clip, **alojado**. Son 8 segundos sin audio imprescindible: un
embed de YouTube traería el reproductor completo, su marca, sus cookies y
el consentimiento que eso obliga a pedir en el sitio de una fundación de
salud mental. Un mp4 de 1 MB no tiene ninguna de esas contrapartidas.

Para piezas largas —el manifiesto completo, los testimonios— sí conviene
YouTube o Vimeo: bitrate adaptativo, subtítulos gestionables y ancho de
banda que no paga la fundación. En ese caso, embeber con fachada (póster
que solo carga el iframe al pulsar) y usar `youtube-nocookie.com`.

`video/manifiesto-master.mp4` se conserva como original para reencodear.

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
