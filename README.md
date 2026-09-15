# I'm Fine. Or Maybe Not.

Landing de la colaboración **Lancôme × Fundación Manantial**.

Campaña de prevención y visibilización de los problemas de salud mental en
mujeres. El objetivo de la página es una sola conversión: que se complete el
cuestionario. Todos los CTA principales apuntan ahí.

Se alojará en [fundacionmanantial.org](https://www.fundacionmanantial.org/),
enlazada desde un botón de la web principal.

## Stack

HTML + CSS + JavaScript, sin dependencias ni build. Un único archivo
(`index.html`) con los estilos y el script en línea. La única carga externa son
las fuentes de Google Fonts.

Todas las rutas de imagen son **relativas** (`img/...`), así que la carpeta
entera se puede subir tal cual a `fundacionmanantial.org/lancome` sin tocar
una sola línea.

## Tipografía

- **Mulish** — la tipografía de Fundación Manantial. Es la principal de toda
  la página: titulares, cuerpo, botones y navegación.
- **Bodoni Moda** — solo para el wordmark LANCÔME y la cita. Es el guiño
  didone de Lancôme, usado con cuentagotas.
- **Archivo** (ancho condensado, peso 800) — exclusivamente para el lockup
  del claim, que funciona como logo.

## Reglas de marca

- El claim va **siempre en inglés**: I'M FINE · OR MAYBE NOT. El resto de la
  página está en castellano.
- El logo de **Fundación Manantial va a la izquierda de la navegación**, por
  delante del lockup de campaña: la landing se aloja en su dominio.
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
| URL del cuestionario | `const FORM_URL` al final de `index.html` — alimenta los 5 CTA |
| Logo oficial de Fundación Manantial | los `<svg class="fm-mark">` (ahora hay un trazado provisional) |
| Ruta final de alojamiento | prevista `fundacionmanantial.org/lancome` |
| Fotografía | carpeta `img/` — ver nombres abajo |
| Vídeo de embajadoras | bloque `.hero` y sección `#voces` |
| Artículos de Lancôme | títulos y URLs reales en `#articulos` |
| Datos de prevalencia | `#colaboracion` y `.stats` — verificar fuentes antes de publicar |

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
  -movflags +faststart -an video/manifiesto.mp4
```

`-an` quita el audio: el vídeo lleva los subtítulos quemados, así que se
entiende en silencio. Si hace falta conservar la voz, cambia `-an` por
`-c:a aac -b:a 96k`.

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

## Estructura

1. Banner — claim y vídeo
2. Abrimos la duda — «lo que decimos / lo que no decimos»
3. Lo comprobamos todo menos cómo estamos
4. Cuestionario (bloque protagonista)
5. Colaboración Lancôme + Fundación Manantial
6. Cómo entendemos la salud mental desde FM
7. Artículos Lancôme
8. Voces
9. Quiénes somos y proyectos de FM
10. Cierre → cuestionario
