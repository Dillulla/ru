---
title: Sintaxis de escritura y formato básicos
intro: Crear formatos sofisticados para tu prosa y código en GitHub con sintaxis simple.
redirect_from:
  - /articles/basic-writing-and-formatting-syntax
  - /github/writing-on-github/basic-writing-and-formatting-syntax
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
shortTitle: Sintaxis de formato básica
---

## Encabezados

Para crear un encabezado, agrega uno a seis símbolos `#` antes del encabezado del texto. La cantidad de `#`</code> que usas determinará el tamaño del ecanbezado.

```markdown
# El encabezado más largo
## El segundo encabezado más largo
###### El encabezado más pequeño
```

![Encabezados H1, H2 y H6 representados](/assets/images/help/writing/headings-rendered.png)

## Estilo de texto

Puedes indicar énfasis con texto en negritas, itálicas o tachadas en los campos de comentario y archivos `.md`.

| Estilo                       | Sintaxis          | Atajo del teclado   | Ejemplo                                         | Resultado                                     |
| ---------------------------- | ----------------- | ------------------- | ----------------------------------------------- | --------------------------------------------- |
| Negrita                      | `** **` o `__ __` | command/control + b | `**Este texto está en negrita**`                | **Este texto está en negrita**                |
| Cursiva                      | `* *` o `_ _`     | command/control + i | `*Este texto está en cursiva*`                  | *Este texto está en cursiva*                  |
| Tachado                      | `~~ ~~`           |                     | `~~Este texto está equivocado~~`                | ~~Este texto está equivocado~~                |
| Cursiva en negrita y anidada | `** **` y `_ _`   |                     | `**Este texto es _extremadamente_ importante**` | **Este texto es _extremadamente_ importante** |
| Todo en negrita y cursiva    | `*** ***`         |                     | `***Todo este texto es importante***`           | ***Todo este texto es importante***           |

## Cita de texto

Puedes citar texto con un `>`.

```markdown
Tal como dice Abraham Lincoln:

> Con perdón de la expresión
```

![Texto citado representado](/assets/images/help/writing/quoted-text-rendered.png)

{% tip %}

**Sugerencia:** Al revisar una conversación, puedes citar un texto automáticamente en un comentario al resaltar el texto y luego escribir el código `r`. Puedes citar un comentario completo al hacer clic en {% octicon "kebab-horizontal" aria-label="The horizontal kebab icon" %}, y luego en **Quote reply** (Citar respuesta). Para obtener más información sobre atajo del teclado, consulta "[Atajos del teclado](/articles/keyboard-shortcuts/)".

{% endtip %}

## Código de cita

Puedes indicar un código o un comando dentro de un enunciado con comillas simples. El texto entre las comillas simples no se formateará.{% ifversion fpt or ghae-next or ghes > 3.1 %} También puedes presionar el atajo de teclado `command` o `Ctrl` + `e` para insertar las comillas simples para un bloque de código dentro de una línea o texto de marcado.{% endif %}

```markdown
Usa `git status` para enumerar todos los archivos nuevos o modificados que aún no han sido confirmados.
```

![Bloque de código en línea representado](/assets/images/help/writing/inline-code-rendered.png)

Para formatear código o texto en su propio bloque distintivo, usa comillas triples.

<pre>
Algunos de los comandos de Git básicos son:
```
git status
git add
git commit
```
</pre>

![Bloque de código representado](/assets/images/help/writing/code-block-rendered.png)

Para obtener más información, consulta "[Crear y resaltar bloques de código](/articles/creating-and-highlighting-code-blocks)".

## Enlaces

Puedes crear un enlace en línea al encerrar el texto del enlace entre corchetes `[ ]`, y luego encerrar la URL entre paréntesis `( )`. {% ifversion fpt or ghae-next or ghes > 3.1 %}También puedes utilizar el atajo de teclado `command + k` para crear un enlace.{% endif %}

`Este sitio se construyó usando [GitHub Pages](https://pages.github.com/).`

![Enlace representado](/assets/images/help/writing/link-rendered.png)

{% tip %}

**Sugerencias:** {% data variables.product.product_name %} automáticamente crea enlaces cuando las direcciones URL válidas están escritas en un comentario. Para obtener más información, consulta "[Referencias y direcciones URL autovinculadas](/articles/autolinked-references-and-urls)".

{% endtip %}

## Enlaces de sección

{% data reusables.repositories.section-links %}

## Enlaces relativos

{% data reusables.repositories.relative-links %}

## Images

You can display an image by adding `!` and wrapping the alt text in`[ ]`. Then wrap the link for the image in parentheses `()`.

`![This is an image](https://myoctocat.com/assets/images/base-octocat.svg)`

![Rendered Image](/assets/images/help/writing/image-rendered.png)

{% data variables.product.product_name %} supports embedding images into your issues, pull requests{% ifversion fpt %}, discussions{% endif %}, comments  and `.md` files. You can display an image from your repository, add a link to an online image, or upload an image. For more information, see "[Uploading assets](#uploading-assets)."

{% tip %}

**Tip:** When you want to display an image which is in your repository, you should use relative links instead of absolute links.

{% endtip %}

Here are some examples for using relative links to display an image.

| Contexto                                                    | Relative Link                                                          |
| ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| In a `.md` file on the same branch                          | `/assets/images/electrocat.png`                                        |
| In a `.md` file on another branch                           | `/../main/assets/images/electrocat.png`                                |
| In issues, pull requests and comments of the repository     | `../blob/main/assets/images/electrocat.png`                            |
| In a `.md` file in another repository                       | `/../../../../github/docs/blob/main/assets/images/electrocat.png`      |
| In issues, pull requests and comments of another repository | `../../../github/docs/blob/main/assets/images/electrocat.png?raw=true` |

{% note %}

**Note**: The last two relative links in the table above will work for images in a private repository only if the viewer has at least read access to the private repository which contains these images.

{% endnote %}

For more information, see "[Relative Links](#relative-links)."


## Listas

Puedes realizar una lista desordenada al anteceder una o más líneas de texto con `-` o `*`.

```markdown
- George Washington
- John Adams
- Thomas Jefferson
```

![Lista desordenada representada](/assets/images/help/writing/unordered-list-rendered.png)

Para ordenar tu lista, antecede cada línea con un número.

```markdown
1. James Madison
2. James Monroe
3. John Quincy Adams
```

![Lista ordenada representada](/assets/images/help/writing/ordered-list-rendered.png)

### Listas anidadas

Puedes crear una lista anidada al dejar sangría en uno o más elementos de la lista debajo de otro elemento.

Para crear una lista anidada mediante el editor web en {% data variables.product.product_name %} o un editor de texto que usa una fuente monoespaciada, como [Atom](https://atom.io/), puedes alinear tu lista visualmente. Escribe los caracteres con espacio frente a tu elemento de la lista anidada hasta que el carácter del marcador de lista (`-` or `*`) se encuentre directamente debajo del primer carácter del texto en el elemento que se encuentra por debajo.

```markdown
1. Primer elemento de la lista
   - Primer elemento de la lista anidado
     - Segundo elemento de la lista anidado
```

![Lista anidada con alineación resaltada](/assets/images/help/writing/nested-list-alignment.png)

![Lista con dos niveles de elementos anidados](/assets/images/help/writing/nested-list-example-1.png)

Para crear una lista anidada en el editor de comentarios en {% data variables.product.product_name %}, que no usa una fuente monoespaciada, puedes observar el elemento de la lista inmediatamente anterior a la lista anidada y contar el número de caracteres que aparecen antes del contenido del elemento. Luego escribe ese número de caracteres de espacio frente al elemento de la lista anidada.

En este ejemplo, puedes agregar un elemento de la lista anidada debajo del elemento de la lista `100. Primer elemento de la lista` con una sangría mínima de cinco espacios para el elemento de la lista anidada, dado que hay cinco caracteres (`100.`) antes del `Primer elemento de la lista`.

```markdown
100. Primer elemento de la lista
     - Primer elemento de la lista anidada
```

![Lista con un elemento de lista anidado](/assets/images/help/writing/nested-list-example-3.png)

Puedes crear múltiples niveles de listas anidadas mediante el mismo método. Por ejemplo, dado que el primer elemento de la lista tiene siete espacios (`␣␣␣␣␣-␣`) antes del contenido de la lista anidada `Primer elemento de la lista anidada`, deberías colocar sangría en el primer elemento de la lista anidada por siete espacios.

```markdown
100. Primer elemento de la lista
     - Primer elemento de la lista anidada
       - Segundo elemento de la lista anidada
```

![Lista con dos niveles de elementos anidados](/assets/images/help/writing/nested-list-example-2.png)

Para conocer más ejemplos, consulta las [Especificaciones de formato Markdown de GitHub](https://github.github.com/gfm/#example-265).

## Listas de tareas

{% data reusables.repositories.task-list-markdown %}

Si una descripción de los elementos de la lista de tareas comienza con un paréntesis, necesitarás colocar una `\`:

`- [ ] \(Optional) Abre una propuesta de seguimiento`

Para obtener más información, consulta "[Acerca de las listas de tareas](/articles/about-task-lists)".

## Mencionar personas y equipos

Puedes mencionar a una persona o [equipo](/articles/setting-up-teams/) en {% data variables.product.product_name %} al escribir `@` más el nombre de usuario o el nombre del equipo. Esto activará una notificación y llamará su atención hacia la conversación. Las personas también recibirán una notificación si editas un comentario para mencionar su nombre de usuario o el nombre del equipo. Para obtener más información acerca de las notificaciones, consulta la sección {% ifversion fpt or ghes or ghae %}"[Acerca de las notificaciones](/github/managing-subscriptions-and-notifications-on-github/about-notifications){% else %}"[Acerca de las notificaciones](/github/receiving-notifications-about-activity-on-github/about-notifications){% endif %}".

`@github/support ¿Qué piensas sobre estas actualizaciones?`

![@mention representado](/assets/images/help/writing/mention-rendered.png)

Cuando mencionas a un equipo padre, los miembros de los equipos hijo también reciben notificaciones, simplificando la comunicación con múltiples grupos de personas. Para obtener más información, consulta "[Acerca de los equipos](/articles/about-teams)".

Si escribes un símbolo `@` aparecerá una lista de personas o equipos en el proyecto. La lista filtra a medida que escribes, por lo que una vez que escribes el nombre de la persona o del equipo que estás buscando, puedes usar las teclas de flecha para seleccionarlos y presionar cada pestaña para ingresar para completar el nombre. En el caso de los equipos, escribe el nombre de la @organización/equipo y todos los miembros del equipo que se suscribirán a la conversación.

Los resultados autocompletados se restringen a los colaboradores del repositorio y a otros participantes en el hilo.

## Hacer referencia a propuestas y solicitudes de extracción

Puedes mencionar una lista de las propuestas y las solicitudes de extracción sugeridas dentro del repositorio al escribir `#`. Escribe el número o el título de la propuesta o la solicitud de extracción para filtrar la lista, y luego presiona cada pestaña o ingresa para completar el resultado resaltado.

Para obtener más información, consulta "[Referencias y direcciones URL autovinculadas](/articles/autolinked-references-and-urls)".

## Hacer referencia a recursos externos

{% data reusables.repositories.autolink-references %}

## Adjuntos de contenido

Some {% data variables.product.prodname_github_apps %} provide information in {% data variables.product.product_name %} for URLs that link to their registered domains. {% data variables.product.product_name %} presenta la información suministrada por la app debajo de la URL en el cuerpo o comentario de una propuesta o solicitud de extracción.

![Adjunto de contenido](/assets/images/github-apps/content_reference_attachment.png)

Para ver los adjuntos de contenido, debes tener una {% data variables.product.prodname_github_app %} que use la API de los adjuntos de contenido instalada en el repositorio.{% ifversion fpt %} Para obtener más información, consulta las secciones "[Instalar una app en tu cuenta personal](/articles/installing-an-app-in-your-personal-account)" y "[Instalar una app en tu organización](/articles/installing-an-app-in-your-organization)".{% endif %}

Los adjuntos de contenido no se mostrarán para las URL que son parte de un enlace de Markdown.

Para obtener más información sobre el desarrollo de una {% data variables.product.prodname_github_app %} que utilice adjuntos de contenido, consulta la sección "[Utilizar adjuntos de contenido](/apps/using-content-attachments)".

## Cargar activos

Puedes cargar activos como imágenes si las arrastras y sueltas, las seleccionas de un buscador de archivos o si las pegas. Puedes cargar activos a las propuestas, solicitudes de cambios, comentarios y archivos `.md` en tu repositorio.

## Usar emojis

Puedes agregar emojis a tu escritura al escribir `:EMOJICODE:`.

`@octocat :+1: This PR looks great - it's ready to merge! :shipit:`

![Emoji representado](/assets/images/help/writing/emoji-rendered.png)

Si escribes `:` aparecerá una lista con los emojis sugeridos. La lista filtrará a medida que escribes; por lo tanto, una vez que encuentres el emoji que estás buscando, presiona **Tab** (Tabulador) o **Enter** (Intro) para completar el resultado resaltado.

Para encontrar una lista completa de emojis y códigos disponibles, consulta el [listado de emojis](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md).

## Párrafos

Puedes crear un nuevo párrafo al dejar una línea en blanco entre las líneas de texto.

## Importar formato de Markdown

Puedes pedirle a {% data variables.product.product_name %} que ignore (o evada) el formato de Markdown usando `\` antes del carácter de Markdown.

`Cambiemos el nombre de \*our-new-project\* a \*our-old-project\*.`

![Carácter evadido representado](/assets/images/help/writing/escaped-character-rendered.png)

Para obtener más información, consulta "[Sintaxis de Markdown" de Daring Fireball](https://daringfireball.net/projects/markdown/syntax#backslash),

## Hiding content with comments

You can tell {% data variables.product.product_name %} to hide content from the rendered Markdown by placing the content in an HTML comment.

<pre>
&lt;!-- This content will not appear in the rendered Markdown --&gt;
</pre>

## Leer más

- [{% data variables.product.prodname_dotcom %} Especificaciones del formato Markdown](https://github.github.com/gfm/)
- "[Acerca de escritura y formato en GitHub](/articles/about-writing-and-formatting-on-github)"
- "[Trabajar con formato avanzado](/articles/working-with-advanced-formatting)"
- "[Dominar Markdown](https://guides.github.com/features/mastering-markdown/)"
