# El contenido principal de la página

## La etiqueta `<main>`

La etiqueta `<main>` es la etiqueta que se utiliza para el contenido principal de la página. Es importante que solo haya un `<main>` por página y que no contenga contenido que se repita (como navegación, pie de página, cabecera de la página, etc).

```html
<header>La cabecera de la página</header>
<main>Contenido principal de nuestra página...</main>
```

> **Nota sobre accesibilidad:** El elemento `<main>` es un landmark semántico que ayuda a los lectores de pantalla a identificar y navegar directamente al contenido principal de la página. Los usuarios pueden saltar la navegación y otros elementos repetitivos yendo directamente al `<main>`. Por eso es importante que solo haya un `<main>` por página y que contenga el contenido único y principal.

## La etiqueta `<section>`

Dentro de nuestra página, tendremos siempre secciones con la información relacionada. Por ejemplo, en nuestra página de empleos, tendremos una sección con un formulario de búsqueda, otra sección con las características del servicio, etc.

```html
<main>
  <section>
    <h2>Sección de búsqueda</h2>
    Aquí irá el formulario de búsqueda
  </section>
  <section>
    <h2>Sección de características</h2>
    Aquí irán las características del servicio
  </section>
  <section>
    <h2>Sección de contacto</h2>
    Aquí irá el formulario de contacto
  </section>
</main>
```

> **Nota sobre accesibilidad:** Cada `<section>` debe tener un heading (`h2`, `h3`, etc.) que identifique su propósito. Esto ayuda a los lectores de pantalla a navegar por las diferentes secciones de la página. No uses `<section>` solo para estilizar; úsalo cuando el contenido tenga un propósito temático claro y distinto.

Ahora que ya sabemos esto, vamos a empezar a crear la sección más importante de nuestra página principal: la sección hero. El hero normalmente es la primera sección de la página y es la que más destaca visualmente, además que suele tener un título y un botón de llamada a la acción o un formulario para que el usuario haga algo.

# Agregar imágenes a tu página web

## La etiqueta `<img>`

La etiqueta `<img>` es la etiqueta que se utiliza para agregar imágenes a tu página web.

### Atributos de la etiqueta `<img>`

Algunos atributos importantes de la etiqueta `<img>` son:

- `src`: de dónde viene la imagen. Puede ser una ruta local o una URL.
- `alt`: texto alternativo para accesibilidad, SEO y si la imagen no carga.
- `width`/`height`: dimensiones en píxeles para que el navegador reserve espacio.

### Ejemplo de uso

```html
<img src="https://dominio.com/imagen.png" alt="Descripción de la imagen" width="200" height="200" />
```

Como ves, la etiqueta `<img>` es una etiqueta autocerrante. Esto quiere decir que no envuelve contenido interno como los elementos que vimos en la clase anterior.

## Sobre el atributo `alt`

El atributo `alt` es obligatorio y tiene múltiples propósitos importantes:

- **Accesibilidad:** Los lectores de pantalla leen el texto `alt` para describir la imagen a usuarios con discapacidad visual.
- **SEO:** Los motores de búsqueda usan el `alt` para entender el contenido de la imagen.
- **Fallback:** Si la imagen no carga, se muestra el texto `alt` en su lugar.

### Buenas prácticas para escribir textos `alt`

- **Imágenes informativas:** Describe lo que muestra la imagen de forma concisa y específica:

```html
  <img
    src="grafico-ventas.png"
    alt="Gráfico de barras mostrando un aumento del 25% en ventas durante el último trimestre"
  />
```

- **Imágenes decorativas:** Si la imagen es puramente decorativa y no añade información, usa un `alt` vacío:

```html
  <img src="patron-fondo.png" alt="" />
```

- **Evita textos genéricos:** No uses textos como "imagen", "foto" o "gráfico" sin más contexto. Los lectores de pantalla ya anuncian que es una imagen.

- **No repitas información:** Si el texto `alt` repite información que ya está en el texto cercano, puedes usar un `alt` más corto o vacío si es decorativa.

> **Importante:** El atributo `alt` siempre debe estar presente, incluso si está vacío (`alt=""`). Nunca omitas el atributo `alt`.

No es la única etiqueta autocerrante. Hay otras como `<br>`, `<input>`, `<hr>`, etc. Y todas ellas no tienen contenido interno. Las iremos conociendo a lo largo del curso.

# Formularios

## La etiqueta `<form>`

La etiqueta `<form>` es la etiqueta que se utiliza para crear un formulario. Un formulario es un conjunto de campos que el usuario puede rellenar y enviar a la página. Se usan otras etiquetas de forma interna para crear los campos del formulario, normalmente `<input>`.

### Ejemplo de uso

```html
<form>
  <input type="text" name="nombre" placeholder="Nombre" />
  <input type="email" name="email" placeholder="Email" />
  <button type="submit">Enviar</button>
</form>
```

Primero, con `<form>` abrimos el formulario. Dentro de él, usamos `<input>` para crear los campos del formulario. Y finalmente, con `<button>` creamos el botón de envío.

## `<input>`

La etiqueta `<input>` es la etiqueta que se utiliza para crear un campo de formulario.

### Atributos de la etiqueta `<input>`

Algunos atributos importantes de la etiqueta `<input>` son:

- `type`: tipo de input. Puede ser `text`, `email`, `password`, `number`, `date`, etc.
- `name`: nombre del campo. Se usa para identificar el campo cuando se envía el formulario.
- `placeholder`: texto de ayuda que aparece en el campo cuando no se ha rellenado.
- `required`: indica si el campo es obligatorio.

### Ejemplo de uso

```html
<input type="text" name="nombre" placeholder="Nombre" />
```

> `type="text"` es el tipo de input por defecto y, por lo tanto, si no se especifica, se asume que es de tipo texto.

Como ves, la etiqueta `<input>` es una etiqueta autocerrante, como `<img>`. Esto quiere decir que no envuelve contenido interno como los elementos que vimos en la clase anterior.

### Una nota sobre accesibilidad

Por temas de accesibilidad, cada elemento `input` debería tener asociada una etiqueta `<label>` para que los lectores de pantalla y otras tecnologías asistivas puedan identificar correctamente el propósito del campo. En los ejemplos de este curso obviamos las etiquetas `label` para mantener el código más simple y evitar repetición, pero en producción siempre deberías usarlas:

```html
<label for="input-nombre">Nombre</label>
<input type="text" name="nombre" id="input-nombre" placeholder="Nombre" />
```

O también puedes anidar el `input` dentro del `label`:

```html
<label>
  Nombre
  <input type="text" name="nombre" placeholder="Nombre" />
</label>
```

> **Importante:** El atributo `placeholder` no es un sustituto del `label`. El `placeholder` desaparece cuando el usuario empieza a escribir, mientras que el `label` siempre está visible y ayuda a los lectores de pantalla.

## `<button>`

La etiqueta `<button>` es la etiqueta que se utiliza para crear un botón. Los botones son muy comunes en cualquier página web y sirven para que el usuario pueda realizar acciones en ella, como enviar el formulario, aplicar filtros, etc.

> **¡No uses un botón para crear enlaces!** Para eso, usa la etiqueta `<a>` que hemos visto en clases anteriores.

### Atributos de la etiqueta `<button>`

Algunos atributos importantes de la etiqueta `<button>` son:

- `type`: tipo de botón. Puede ser `submit`, `button`, `reset`.
- `disabled`: indica si el botón está deshabilitado.

### Ejemplo de uso

```html
<button type="submit">Enviar</button>
```

> `type="submit"` es el tipo de botón por defecto si es el último o único botón del formulario.

### Accesibilidad en botones

- **Botones con texto:** Siempre usa texto descriptivo en los botones. El texto debe indicar claramente qué acción realizará el botón:

```html
  <button type="submit">Enviar formulario</button>
  <button type="button">Cancelar</button>
```

- **Botones con solo iconos:** Si un botón solo contiene un icono (SVG o imagen) sin texto visible, es esencial añadir un `aria-label` descriptivo:

```html
  <button type="button" aria-label="Cerrar ventana">
    <svg width="24" height="24" aria-hidden="true">
      <!-- icono de X -->
    </svg>
  </button>
```

> **Importante:** El texto del botón (o el `aria-label` si solo tiene icono) debe ser descriptivo. Evita textos genéricos como "Click aquí" o "Botón". Los lectores de pantalla anuncian el texto del botón, así que debe tener sentido por sí solo.

## Sobre los `<svg>`

SVG (Scalable Vector Graphics) es un formato de imagen vectorial que se usa mucho en la web. Una de sus ventajas es que son imágenes que se pueden escalar sin perder calidad, a diferencia de los formatos de imagen tradicionales como JPG o PNG.

Lo mejor de los SVG es que son código, por lo que podemos incluirlos directamente en nuestro HTML.

Por ejemplo, el siguiente icono muestra un check verificado:

El código es el siguiente:

```html
<svg
  width="24"
  height="24"
  viewBox="0 0 24 24"
  stroke="currentColor"
  stroke-width="1"
  stroke-linecap="round"
  stroke-linejoin="round"
  fill="none"
>
  <path stroke="none" d="M0 0h24v24H0z" fill="none" />
  <path
    d="M5 7.2a2.2 2.2 0 0 1 2.2 -2.2h1a2.2 2.2 0 0 0 1.55 -.64l.7 -.7a2.2 2.2 0 0 1 3.12 0l.7 .7c.412 .41 .97 .64 1.55 .64h1a2.2 2.2 0 0 1 2.2 2.2v1c0 .58 .23 1.138 .64 1.55l.7 .7a2.2 2.2 0 0 1 0 3.12l-.7 .7a2.2 2.2 0 0 0 -.64 1.55v1a2.2 2.2 0 0 1 -2.2 2.2h-1a2.2 2.2 0 0 0 -1.55 .64l-.7 .7a2.2 2.2 0 0 1 -3.12 0l-.7 -.7a2.2 2.2 0 0 0 -1.55 -.64h-1a2.2 2.2 0 0 1 -2.2 -2.2v-1a2.2 2.2 0 0 0 -.64 -1.55l-.7 -.7a2.2 2.2 0 0 1 0 -3.12l.7 -.7a2.2 2.2 0 0 0 .64 -1.55v-1"
  />
  <path d="M9 12l2 2l4 -4" />
</svg>
```

Para dar una explicación rápida de los atributos más importantes:

- `width` y `height`: ancho y alto del SVG.
- `viewBox`: define el sistema de coordenadas del SVG.
- `stroke`: color del borde de las formas.
- `stroke-width`: grosor del borde de las formas.
- `stroke-linecap`: define la forma de los extremos de las líneas (puede ser `butt`, `round` o `square`).
- `stroke-linejoin`: define la forma de las uniones entre líneas (puede ser `arcs`, `bevel`, `miter`, `miter-clip` o `round`).
- `fill`: color de relleno de las formas.

Dentro tenemos más elementos HTML, como `<path>`, que define una forma a través de una serie de comandos en su atributo `d`.

Pero podríamos usar otros elementos como `<circle>`, `<rect>`, `<line>`, etc…

¡Podría estar horas hablando de SVG! Así que, si quieres aprender más sobre SVG, puedes echar un vistazo a la [documentación de MDN](https://developer.mozilla.org/es/docs/Web/SVG).

### Accesibilidad en SVG

Cuando uses SVG como iconos o elementos decorativos, es importante considerar la accesibilidad:

- **SVG decorativo:** Si el SVG es puramente decorativo y no añade información, usa `aria-hidden="true"` para ocultarlo de los lectores de pantalla:

```html
  <svg aria-hidden="true" width="24" height="24">
    <!-- contenido del SVG -->
  </svg>
```

- **SVG con significado:** Si el SVG transmite información importante (como un icono de alerta o un botón), añade un `aria-label` descriptivo:

```html
  <button aria-label="Cerrar ventana">
    <svg width="24" height="24">
      <!-- icono de X -->
    </svg>
  </button>
```

O si el SVG está directamente en la página y tiene significado:

```html
<svg aria-label="Gráfico de ventas del mes" role="img" width="400" height="300">
  <!-- contenido del gráfico -->
</svg>
```
# La última sección de nuestra página

La última sección de nuestra página es la sección de características donde mostramos características del servicio o producto que ofrecemos.

```html
<section>
  <header>
    <h2>¿Por qué DevJobs?</h2>
    <p>
      DevJobs es la principal bolsa de trabajo para desarrolladores. Conectamos a los
      desarrolladores con las mejores empresas del mundo.
    </p>
  </header>
  <footer>...</footer>
</section>
```

¡Eh! ¿Qué es esto? ¿Por qué tenemos un `<header>` y un `<footer>` dentro de una `<section>`?

Sí, como ves, podemos usar `<header>` y `<footer>` dentro de `<section>`. Esto es útil para estructurar mejor el contenido de nuestra página, ya que las secciones pueden tener un encabezado y un pie. A diferencia de `<main>`, que sólo puede existir un elemento en la página, las etiquetas `<header>` y `<footer>` pueden usarse dentro de otras etiquetas cuando tenga sentido.

## La etiqueta `<article>`

La etiqueta `<article>` es la etiqueta que se utiliza para crear un… ¿artículo? Bueno, no exactamente. En HTML un artículo se entiende como un contenido independiente y autónomo que puede ser reutilizado en otro sitio. Por ejemplo, un artículo de blog, un comentario, una tarjeta de producto, un tuit… NO significa siempre exactamente que tenga que ser literalmente un artículo de un periódico.

```html
<article>
  <h3>Característica 1</h3>
  <p>Descripción de la característica 1</p>
</article>
<article>
  <h3>Característica 2</h3>
  <p>Descripción de la característica 2</p>
</article>
<article>
  <h3>Característica 3</h3>
  <p>Descripción de la característica 3</p>
</article>
```

¡Sí! La etiqueta `<article>` también podría tener un `<header>` y un `<footer>` dentro.

## El pie de página

Finalmente, queremos que nuestra página web tenga un pie de página donde podamos poner información de contacto, enlaces a redes sociales, etc. En este caso vamos a poner simplemente un copyright.

```html
<footer>
  <small>© 2025 DevJobs. Todos los derechos reservados.</small>
</footer>
```

También tenemos la etiqueta `<small>` que se utiliza para poner texto de menor importancia que el contenido principal como anotaciones, comentarios legales, copyright, etc.

¡Sí! La etiqueta `<small>` suena a pequeño y es verdad que se renderiza por defecto con un tamaño de fuente más pequeño que el contenido principal. Pero siempre ten en cuenta que la idea de HTML es describir el contenido de la página, no su apariencia.