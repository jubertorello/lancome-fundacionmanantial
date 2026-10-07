# Antes de publicar

Landing de **Lancôme × Fundación Manantial**, prevista para
`fundacionmanantial.org/lancome`.

Es HTML plano: no hay compilación, ni dependencias, ni servidor. Se sube la
carpeta tal cual y funciona. Para verla en local basta con un servidor
estático —si se abre el `index.html` con doble clic, el vídeo no carga:

```bash
python3 -m http.server 8000
```

El detalle de todo está en `README.md`. Esta nota solo recoge **las tres
cosas que no pueden publicarse tal como están**.

---

## 1 · Quitar el `noindex`

En el `<head>` de `index.html`, línea 17:

```html
<meta name="robots" content="noindex, nofollow">
```

Mientras esa línea esté, **Google no indexa la página**. Está puesta porque
hasta ahora era material sin publicar. Hay que borrarla al publicar.

No hay `robots.txt` y no hace falta: en una subcarpeta sería inerte, porque
los buscadores solo leen el de la raíz del dominio.

## 2 · El contador de mujeres es una MAQUETA

En `index.html`, el bloque marcado `MAQUETA, NO PUBLICAR`:

```html
<div class="num" data-sim-desde="6457" data-sim-hasta="7000">6.457</div>
```

Sube solo, de 6.457 a 7.000, y **esos incrementos no corresponden a nadie**.
Se montó así para que el cliente viera el efecto en la URL de revisión.

En una campaña de salud mental, bajo el logo de una fundación, un contador
que finge participación real no puede salir a producción. Hay dos salidas:

- **Dato real.** Que la Fundación dé la cifra y se escriba fija, o que dé un
  endpoint y el contador lea de ahí.
- **Revertir.** El commit `e0fe751` tiene la versión honesta, con la cifra
  fija y sin animación.

## 3 · «1 de cada 3 mujeres» necesita fuente

Es **la afirmación más grande de la página**: ocupa una sección entera, en
cuerpo de más de 100 px, sobre prevalencia de ansiedad y depresión.

No tiene fuente citada. Antes de publicar hace falta una referencia que se
pueda sostener públicamente —OMS, Ministerio de Sanidad, estudio con
nombre—. Si no aparece, la banda se quita entera: es preferible a publicar
un dato que nadie puede respaldar.

---

## Lo que ya está resuelto

- **Enlaces.** Los 6 CTA van a `imfine.com/es-es/evalua-tu-salud-mental` y
  «Descubre los recursos» a `imfine.com/es-es/recursos`. Los CTA no llevan
  la URL en el HTML: la reparte `const FORM_URL`, al principio del
  `<script>`. Para cambiarla se toca esa línea y nada más.
- **Vídeo.** Cuatro ficheros en `video/`: el manifiesto de 57 s para el
  fondo del hero y el spot de 17 s para el modal, cada uno con su export de
  escritorio y de móvil. El de móvil del spot está montado en vertical.
- **Formulario de alta.** «Quiero estar informado» envía a Mailchimp. Falta
  que lo valide quien lleve protección de datos en la fundación.
- **Marquesina.** `marquesina.html` es una pieza aparte: la tira que iría
  encima de la cabecera de fundacionmanantial.org, en claro y en oscuro.
  No forma parte de la landing. Su botón apunta todavía a la URL de
  revisión; hay que cambiarlo por la definitiva.

## Dos secciones ocultas

**Voces** y **Artículos** están comentadas en el HTML, no borradas, con sus
estilos y su guion intactos. Se devuelven quitando el comentario. Dentro de
cada una hay una nota explicando cómo.
