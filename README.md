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
- La rosa de Lancôme aparece **siempre desenfocada**, como atmósfera y nunca
  como fotografía legible (clases `.bgimg--blur` y `.bgimg--soft`).

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
