# Ejercicio global Bookmarks (Módulo 2 - Javascript)

1. [x] [Recopilatorio de Bookmarks](#recopilatorio-de-bookmarks-día-1)
2. [x] [Agregar contenido](#bookmark-agregar-contenido-día-2)
3. [x] [Usar variables](#bookmark-usar-variables-día-3)
4. [x] [Condicionales](#bookmark-condicionales-día-4)
5. [x] [Eventos](#bookmark-eventos-día-5)
6. [x] [Objetos](#bookmark-objetos-día-6)
7. [x] [Arrays](#bookmark-arrays-día-7)
8. [x] [Arrays II](#bookmark-arrays-ii-día-8)
9. [x] [Peticiones al servidor I](#bookmark-peticiones-al-servidor-i-día-9)
10. [x] [Peticiones al servidor II](#bookmark-peticiones-al-servidor-ii-día-10)
11. [x] [DOM Avanzado](#bookmark-dom-avanzado-día-11)
12. [x] [Métodos funcionales de arrays](#bookmark-métodos-funcionales-de-arrays-día-12)

---

# Recopilatorio de Bookmarks (día 1)

Vamos a hacer una aplicación web para ir anotando los enlaces y páginas web que nos parezcan interesantes.

![Screenshot de la aplicación web](./images/README_screenshot_main.png)

La sección principal de la aplicación consta de un listado en forma de tabla (que también puede transformarse en una cuadrícula de tarjetas) donde se muestran los enlaces ya guardados por al usuaria y junto con una breve descripción, el origen y etiquetas para categorizarlos.

La aplicación tiene un menú hamburguesa (en la parte superior derecha) que al pulsar sobre él se muestran las opciones de filtrado y de visualización del listado.

![Screenshot del menú desplegado](./images/README_screenshot_menu.png)

Al pulsar sobre el botón de "Vista tarjetas", la lista de enlaces se convertirá en un panel de tarjetas, donde cada una contendrá la información de un enlace:

![Screenshot con el listado en forma de tarjetas](./images/README_screenshot_tarjetas.png)

Por último, la usuaria puede añadir nuevos enlaces pulsando sobre el botón "Nueva" que mostrará un formulario para rellenar los datos del nuevo enlace a guardar.

![Screenshot del formulario para crear un nuevo enlace](./images/README_screenshot_nueva.png)

---

# Bookmark: Agregar contenido (día 2)

## Ejercicios

### 1. Crear un proyecto nuevo

Empezaremos lógicamente por crear un proyecto nuevo, para lo cual:

1. Cread un repositorio en GitHub llamado `promo-X-module-3-pair-Y-sprint-1-hangman-game`.
   - Cambiad la `X` por tu promo y la `Y` por tu número de pareja.
   - Cread el repo en **la organización de Adalab**.
   - Clónadlo en vuestros equipos.
2. Cread un nuevo proyecto de React dentro del repo clonado.
   - Si queréis podéis hacerlo con `create-react-app` o con un `react-starter-kit`.
3. Arráncadlo y poneos a programar.

### 2. Muestra el formulario de nuevo bookmarks

La usuaria puede añadir nuevos enlaces pulsando sobre el botón "Nueva" que mostrará un formulario para rellenar los datos del nuevo enlace a guardar. Prueba a mostrar el formulario asociado al botón de nuevo bookmark.

> **Pista**: Busca la sección que contiene este formualrio y utiliza la propiedad classList.remove("hidden");

![Screenshot del formulario para crear un nuevo enlace](./images/README_screenshot_nueva.png)

### 3. Muestra el desplegable del menú hamburguesa

La aplicación tiene un menú hamburguesa (en la parte superior derecha) que al pulsar sobre él se muestran las opciones de filtrado y de visualización del listado. Prueba a mostrar este menú.

> **Pista**: Busca la sección que contiene este menú y utiliza la propiedad classList.remove("collapsed");
> P
> ![Screenshot del menú desplegado](./images/README_screenshot_menu.png)

### 4. Agregar los enlaces dinámicamente

Ahora vamos a dar nuestros primeros pasos para que nuestra página sea dinámica, vamos a añadir la información estática de los enlaces que está en html desde Javascript. Para ello podemos seguir los siguientes pasos:

1.  Buscad el elemento utilizando el `document.queryselector(".js-datails")`. Recuerda primero añadir esta clase de js a la sección de listas.
2.  Copiad cada `li` dentro de una variable.
3.  Añadir esa variable utilizando propiedad `innerHTML` para agregar los enlaces.

---

# Bookmark: Usar variables (día 3)

## Ejercicio 1

Vamos a usar variables que luego interpolaremos en el string con el HTML de cada bookmark.
Os proponemos usar 6 variables por cada enlace:

1. Una variable para la URL (dirección del enlace).
1. Una variable para la descripción
1. Una variable para indicar si es del módulo actual o no.
1. Otras dos variables que indiquen las etiquetas de ese enlace.
1. Una última variable con el HTML del enlace en la que interpolaremos las anteriores.

Por ejemplo:

```js
const bmk_1_url =
  'https://books.adalab.es/materiales-del-curso-n/-MdR6Gp68BX20m1pi0z2/modulo-2-programando-la-web/javascript/2_1_intro_a_la_programacion';
const bmk_1_desc = 'JS en los materiales de Adalab';
const bmk_1_seen = 'checked';
const bmk_1_tags_1 = 'javascript';
const bmk_1_tags_2 = 'html';
```

> **Nota** : Usamos \_ en los nombres de las variables, pero por una razón académica.
> En JS se suele usar la notación [camelCase](https://es.wikipedia.org/wiki/Camel_case) para los nombres de variable.

## Ejercicio 2: Bonus

¿Serías capaz de buscar métodos de String para pasar a minúsculas el nombre de las etiquetas?

## Ejercicio 3: Bonus

¿Serías capaz de quitar el 'https://' del principio de la dirección en el contenido del enlace usando otro método de String? (en el href no se lo quites)

---

P.D.- Comenta el código de ayer en el que se mostraban el menú y el formulario.

---

# Bookmark: Condicionales (día 4)

## Ejercicio 1

Prueba a mostrar a cambiar la vista del panel de los enlaces en diferentes formatos: lista o tabla. La sección con la clase `data` añadimos las clases `tableview` para que la vista de los enlaces sea en tabla y `listview` para que se muestre en una lista, en dependencia del cual queremos activar. Para ello podemos ver cambiar la clase en el html ver si funciona correctamente:

```html
<section class="data tableview"></section>
```

> **Pista**: Utiliza condicionales y el `classList.contains`

## Ejercicio 2.

Vamos a comenzar a implementar el filtro de búsqueda por descripción. Para ello puedes:

1. Mostrar el menú hamburguesa y dejarlo siempre visible.
2. Seleccionamos el `input` con el `document.querySelector`

```js
const input_search_desc = document.querySelector('.js_in_search_desc');
```

3. Simulamos que escribe la usuaria en el `input` de búsqueda.

```js
input_search_desc.value = 'materiales';
```

4. Recoger el valor del `input` en una variable.

```js
const descrSearchText = input_search_desc.value;
```

5. Utilizar un condicional con la función `includes` antes de añadir cada enlace para solo mostrar aquellos enlaces que contengan la palabra introducida por la usuaria:

```js
if( bmk_2_desc.includes(descrSearchText) ) {
    ....
```

## Ejericio 3. BONUS

Vamos a validar la columna de las categorías de los enlaces: Si el enlace no tiene categoría mostraremos el mensaje **No tiene categorías**.

![Screenshot de la aplicación web](./images/list_without_categories.png)

Para ello podemos verificar si las categorías tienen algún valor, y en dependencia del resultado del condicional mostrar un resultado u utro.

```js
if ((bmk_1_tags_1 === "") & (bmk_1_tags_2 === "")) {
  html += `<p class='item__tags'>No tiene</p>`;
} else {
  ...
}
```

## Ejercicio 4. BONUS

Cambia el valor de la variable `bmk_1_seen` a `true` o `false`. En dependencia de este valor muestra seleccionado o no el `input` de tipo `checkbox`.

---

# Bookmark: Eventos (día 5)

## Ejercicio 1

Haz una función (podemos llamarla `handleClickLinkDropdown`) que muestra u oculta el menú colapsable dependiendo de su estado actual. Agrega un evento para cuando damos `click` en el botón hamburguesa.

> **Nota**:
> Recuerda utilizar el `event.preventDefault()`.
> La clase `collapsed` es la que muestra y/u oculta el menú colapsable.

## Ejercicio 2

Haz las funciones necesarias para cambiar la vista de los bookmarks a tarjetas.

- Agrega un evento `click` al botón "Vista Tarjetas" del menú que cambie la vista a tarjetas de los bookmarks.
- Además agrega y/o elimina la clase `selected` de los botones para resaltarlo.

```js
...
  buttonShowTable.classList.remove('selected');
  buttonShowCardview.classList.add('selected');
...
```

## Ejercicio 3

Haz las funciones necesarias para cambiar la vista de los bookmarks a tabla.

- Agrega un evento `click` al botón "Vista Tabla" del menú que cambie la vista a tabla de los bookmarks.
- Además agrega y/o elimina la clase `selected` de los botones para resaltarlo.

```js
...
buttonShowCardview.classList.remove('selected');
buttonShowTable.classList.add('selected');
...
```

## Ejercicio 4

Crea las funciones necesarias para mostrar el formulario de añadir una nueva tarjeta cuando damos `click` en el botón nueva. Para ello puedes hacer uso de la función `showAddForm()`

```js
//función que muestra el formulario para agregar un nuevo enlace

function showAddForm() {
  sectionAdd.classList.remove('hidden');
}
```

---

# Bookmark: Objetos (día 6)

## Ejercicio 1

Crea un objeto `bmkData` para cada uno de los enlaces que contenga toda la información de las variables: `bmk_1_url`, `bmk_1_desc`, `bmk_1_seen`, `bmk_1_tags_1`, `bmk_1_tags_2`. Por ejemplo:

```js
//objeto con la información del primer enlace
const bmkData_1 = {
  url: 'https://books.adalab.es/materiales-del-curso-n/-MdR6Gp68BX20m1pi0z2/modulo-2-programando-la-web/javascript/2_1_intro_a_la_programacion',
  desc: 'JS en los materiales de Adalab',
  seen: true,
  tags_1: 'javascript',
  tags_2: '',
};
```

Luego modifica la función `renderBookmark` para que reciba un objeto como parámetro.

```js
...
function renderBookmark(bmkData) {
...
```

---

# Bookmark: Arrays (día 7)

## Ejercicio 1

Hoy vamos a crear una única variable `bmkData` que almacenará los datos de todos los enlaces como un array. Podemos usar las variables con objetos del ejercicio de ayer para crear este array:

```js
// Objeto con la información del primer enlace
const bmkData_1 = {
  url: 'https://books.adalab.es/materiales-del-curso-n/-MdR6Gp68BX20m1pi0z2/modulo-2-programando-la-web/javascript/2_1_intro_a_la_programacion',
  desc: 'JS en los materiales de Adalab',
  seen: true,
  tags_1: 'javascript',
  tags_2: '',
};

// Objeto con la información del segundo enlace
const bmkData_2 = {
  /* ... */
};

// Objeto con la información del tercer enlace
const bmkData_3 = {
  /* ... */
};

// Lista con la información de todos los enlaces
const bmkData = [bmkData_1, bmkData_2, bmkData_3];
```

## Ejercicio 2 (BONUS)

Vamos a hacer un array también con las etiquetas de cada bookmark. Será un array dentro de un objeto dentro del array de todos los bookmark (ufff).

Debemos quitar las propiedades `tags_1` y `tags_2` de cada objeto con datos de cada Bookmark y agruparlos en una única propiedad `tags` que sea un array con los dos valores de las etiquetas. Puedes retirar los valores que sean cadenas vacías (así tendremos arrays de 0, 1 ó 2 elementos).

También deberemos modificar la función `renderTags()` para que reciba como parámetro una única variable que sea el array de tags, pero su valor de retorno deberá ser el mismo. Recuerda cambiar el argumento que le pasas a esta función dentro de la función `renderBookmark()`.

---

# Bookmark: Arrays II (día 8)

## Ejercicio 1: Agregar nuevo enlace

Vamos a añadir un nuevo bookmark al listado de enlaces desde el formulario. Haz una nueva función manejadora del evento click del botón **Guardar** del formulario, podemos llamarla `saveNewBookmark(ev)`.

Esta función obtiene los valores de cada uno de los inputs, crea un nuevo objeto `newBookmarkDataObject` que agregaremos al listado de enlaces con la siguiente línea de código:

```js
bmkData.push(newBookmarkDataObject);
```

Recuerda limpiar los valores de los `inputs` y volver a ocultar la sección del formulario.

## Ejericio 2: Cancelar formulario

Haz el código necesario para ocultar la sección del fomulario de añadir un nuevo enlace. Recuerda tambien limpiar los valores de los `inputs`.

---

# Bookmark: Peticiones al servidor I (día 9)

## Ejercicio 1

Vamos a obtener la lista de bookmarks de un servidor. Para realizar este ejercicios tenemos creado un servidor que devuelve un listado con la información de los enlaces de un usuario en formato `json`:

```js
...

    {
    "id": "16396904232462016",
    "owner": "adalabdigital",
    "url": "https://books.adalab.es/materiales-del-curso-o/XwqEzZ1o5Xgza96sxhld/modulo-2-programando-la-web/javascript/2_1_intro_a_la_programacion",
    "description": "JS en los materiales de Adalab",
    "module": false,
    "tags": [ "javascript"]
    },

...
```

Prueba la siguiente petición en en tu navegador con tu usuario de GitHub:
https://adalab-bookmarks-api.herokuapp.com/api/bookmarks/tuusuariodegithub

Haz un `fetch` para obtener el lisatdo los enlaces y mostrar en la página de los bookmarks.

---

# Bookmark: Peticiones al servidor II (día 10)

## Ejercicio 1

Guarda los datos de los bookmarks en el local storage, asi cada vez que se inicie la aplicación primero busque si los datos están almacenados en el local storage y en caso de que no estén, entonces se hace la petición de los datos al servidor.

## Ejercicio 2 (BONUS)

Guarda un nuevo bookmarks en el servidor, haz una petición `post` para guardar los datos a la siguiente dirección: https://adalab-bookmarks-api.herokuapp.com/api/bookmark/tuusuariodegithub.

## Ejercicio 3 (BONUS)

Haz fetch al servidor al cambiar el campo de Leído de un bookmark.
Usar el servidor https://adalab-bookmarks-api.herokuapp.com/api/bookmark/tuusuariodegithub/iddelbookmark con el método PUT.

---

# Bookmark: DOM Avanzado (día 11)

## Ejercicio 1

Cambia los innerHTML de las funciones `renderTags()`, `renderSeen()` y `renderBookmark()` por sentencias de creación de elementos.
Probablemente la función `renderSeen()` ya es útil como está y nos conviene hacer funciones para cada campo: `renderURL()`, `renderSeen()`, `renderDescription()` y `renderTags()`.

---

# Bookmark: Métodos funcionales de arrays (día 12)

## Ejercicio 1

El menú lateral de la aplicación tiene un `input` para realizar búsquedas. Haz el código necesario para filtrar según la descripción de los bookmarks. Utiliza el método de arrays `filter`.

## Ejercicio 2 (BONUS)

Agrega el código necesario para filtrar si el enlace está leido o no, además de la descripción.

## Ejercicio 3 (BONUS)

Agrega una nueva funcionalidad que permita filtrar por las etiquetas, además de filtrar si el enlace está leido o no y por la descripción.
