# Criterios de aceptación de maquetas de terceros

**CONTENIDO**  
[Generales](#generales)  
[HTML](#html)  
[CSS](#css)  
[Javascript](#javascript)

## Generales

### Asegurarse de que el código es legible y fácil de seguir:
Escribir código conciso y legible es obligatorio, nos ahorrará dolores de cabeza en el futuro. Las posibilidades de escribir código que nunca se cambiará o nunca se volverá a ver son escasas, y el tiempo que se pierde en el código antiguo es un lujo que no podemos costear.

*Una muy buena guía de código es [Codeguide.Co](https://codeguide.co/), te recomendamos revisarla y aplicarla cuando sea posible*

### Usar indentación:
Usa la sangría como una representación visual de elementos anidados, añadiendo un espacio grande (tabulador o 4 espacios) a cada elemento hijo.

**Ejemplos:**
```html
<body>
    <div class="bloque1">
        <h1>Título Principal</h1>
        <img src="imagen1.jpg" alt="imagen1">
        <p>Elemento 1</p>
    </div>
</body>
```

```css
.bloque1 {
    background-color: transparent;
    border: 1px solid #333333;
}
```

```javascript
function cambiarContenido(mensaje){
    var elemento = document.getElementById('bloque1');

    if(mensaje!==''){
        elemento.innerHTML = mensaje;
    }
}
cambiarContenido('Hola Mundo');
```

### Comentar código:
Sea HTML, CSS, o Javascript, es importante que el código se comente para facilitar una revisión posterior. Tus comentarios deben explicar por qué funciona de la manera en que funciona y cuál es el objetivo general del código.

**Ejemplos:**
```html
<!-- El siguiente listado será llenado dinámicamente -->
<ul id="ultimasnoticias" class="ultimasnoticias"></ul>
```

```css
html, body {
    height: 100%;
    -ms-overflow-x: hidden; /* Quita scroll horizontal en IE8 */
}

/*
    Fix para quitar scroll horizontal
    en Internet Explorer/Edge ≤ 6
    http://browserhacks.com/#hack-f0ed28ec60d48b6b0b6e4e8dc9fc8d06
*/
* html, body { overflow-x: hidden; }
```

```javascript
// La siguiente función cambia el contenido HTML del bloque
function cambiarContenido(mensaje){
    var elemento = document.getElementById('bloque1');

    if(mensaje!==''){
        elemento.innerHTML = mensaje;
    }
}
cambiarContenido('Hola Mundo'); // Llamamos a la función y proporcionamos el mensaje
```


### Elementos obsoletos:
No utilizar Flash, ni etiquetas HTML, ni propiedades CSS ni métodos o características javascript considerados obsoletos.

### Elementos experimentales:
Siempre se debe cuidar que los elementos, estilos y funcionalidades experimentales son compatibles con todos los navegadores.

*Para verificar la compatibilidad de tu código puedes consultar el sitio [Caniuse.Com](https://caniuse.com/)*

### Compatibilidad en todos los navegadores:
De la mano del desarrollo para todos los dispositivos, es importante que el sitio web sea compatible con al menos los principales navegadores en el mercado (Chrome, Firefox, Safari, Edge), tanto en teléfonos como en tablets y en sistemas operativos como MacOs, iOs, iPadOs, Android y Windows.

Por ello es importante no utilizar propiedades ni etiquetas experimentales, tanto en css como html y javascript, que pudieran tener funcionamientos inesperados o nulos en algunos navegadores y tratar de que el código que utilizamos sea compatible con al menos 2 versiones anteriores.

*Para verificar la compatibilidad de tu código puedes consultar el sitio [Caniuse.Com](https://caniuse.com/)*

### No depender de librerías y frameworks:
Si bien no hay nada de malo en convertirse en un maestro en una librería o framework específico, es importante no confiar exclusivamente en esos métodos. Todas las librerías y frameworks están construidos con los propios lenguajes nativos y se actualizan y eliminan constantemente, además de que no se tiene control alguno sobre los bugs y fallas de seguridad que puedan tener. Para no complicar el mantenimiento posterior y tener un mejor control sobre el diseño y funcionalidad, es preferible utilizar los lenguajes nativos, a menos que se tenga un desarrollo que dependa de frameworks específicos como *React* o *Angular*.

Es importante tomar en cuenta de que en el caso de que por requerimiento tuvieras que utilizar alguna librería, **nunca debes modificarla**.

### Texto en imagen:
Evita usar imágenes para mostrar texto siempre que sea posible. Esto permite hacer la carga de la página más rápida, además de que hará más fácil cambiar el texto si se requiere.

### Optimizar el código CSS y JS:
Optimizar el código tanto como sea posible, reutilizando funciones y agrupando estilos similares. La página debe funcionar además, **con una versión minificada del js y css** y contar lon los archivos originales sin minimizar, para poder editarlos. Si lo necesitas, puedes utilizar servicios como *[Minifier.Org](https://www.minifier.org/)*

### Optimizar imágenes:
Utiliza imágenes optimizadas para web, recortadas al tamaño que necesitas, en formato jpeg preferentemente (80% de calidad aprox) y png solo si se requiere transparencia.

## HTML
### Cuidar el cierre de etiquetas:
Se debe revisar que todas las etiquetas que lo requieran tengan su etiqueta de cierre.

### Uso de HTML Semántico:
Para mejorar la accesibilidad, el mantenimiento y el posicionamiento SEO, se deben utilizar las etiquetas creadas a partir de HTML5 (`article`, `section`, `nav`, `aside`, `header`, `footer`, etc) en la estructura de la página. De la misma manera, se deben cuidar detalles como la posición de los títulos *por orden de importancia* (`h1`, `h2`, `h3`, `h4`, `h5` y `h6`), poner la descripción de las imágenes en el atributo alt y usar clases y id cuyos nombres se relacionen más con la función y/o naturaleza del elemento que modifican.

Se aconseja además solo utilizar el atributo id para facilitar la funcionalidad, **nunca para dar estilo al elemento**.

Se aconseja también **nunca estructurar con el elemento `<table>`** a menos que sean datos estadísticos o listados.

Referencias:  
https://desarrolloweb.com/articulos/etiquetas-semanticas-html5.html  
http://www.manualweb.net/html5/semantica-html5/  
https://www.arkaitzgarro.com/html5/capitulo-2.html  

## CSS
### Uso de CSS Reset:
Muchos navegadores web agregan su estilo por defecto, y cada navegador web puede aplicar estilos en su propia forma única (muchos navegadores hacen que los enlaces sean azules o le dan a los botones y tablas una cierta cantidad de borde y relleno). La utilización de un Reset CSS es una gran práctica para restablecer todos los elementos, tener un mayor control de su presentación y diseñarlos desde cero.

Existen varias formas de resetear los elementos, e incluso hay librerías que se encargan de ello (como normalize o sanitize). Nosotros recomendamos que utilices un reset simple, de pocas líneas, que sea eficiente y permita modificaciones. Ejemplo de ello son el reset de [Eric Meyer](http://meyerweb.com/eric/tools/css/reset/) y el de [html5doctor](http://html5doctor.com/html-5-reset-stylesheet/)

### Evitar usar estilos en línea:
Los estilos en línea se refieren principalmente a utilizar estilos dentro de las etiquetas (`<h1 style="color:#ff0000">Título Principal</h1>`). Esto debe evitarse excepto en casos donde la etiqueta está siendo editada directamente por javascript.

De la misma manera, debe tratar de evitarse el incluir la hoja de estilos en el mismo archivo html que se está trabajando. **HTML y CSS Siempre deben trabajarse en archivos separados.**

### Evitar dar estilo directamente a las etiquetas:
Con excepción del reset o estilos ***muy generales***, las reglas deben ser aplicadas a las clases de los elementos. Esto evita que se alteren los estilos de otros elementos o se haga un *reset involuntario* que no teníamos previsto.

**Ejemplo:**
```html
<h1 clase="titulo">Título</h1>

<style>
    h1 { color: #333333; } /* MAL: esto afectará a todos los elementos H1 */
    .titulo { color: #333333; } /* BIEN: Esto sólo afecta al elemento .titulo */
</style>
```

### Evitar el uso de !important:
Los !important en CSS tienen la capacidad de anular cualquier propiedad de un elemento, dificultando cualquier edición posterior. Por ello **no se debe usar !important en ninguno de tus estilos**.

### Agrupar los estilos por componente:
Para facilitar el mantenimiento y la claridad del código, los estilos deben estar estructurados por grupos de componentes, así es más fácil saber, por ejemplo que `.menu .menu-boton {}` se refiere a los botones del menú. Además esto facilita el encapsulamiento de css.

### Encapsular CSS:
Para dar estructura y hacer que tus reglas no afecten a otras partes del dom, **es importante que encapsules tu código**, utilizando selectores descendentes.

***Ejemplo:***
```css
.titulo {
    /*
        MAL: TODOS los elementos con clase .titulo
        en el <BODY> serán afectados
    */
}

.bloque .titulo {
    /*
        BIEN: Solo los elementos con clase .titulo
        dentro del elemento .bloque serán afectados
    */
}
```

Existen varias formas de hacerlo. Puedes usar la [Metodología Object Oriented CSS](https://blog.interactius.com/metodolog%C3%ADa-css-object-oriented-css-oocss-b58118935d3e) o la [Metodología BEM](http://getbem.com/) o basar tu nomenclatura en los dos, lo importante es que además de ser práctico, *pueda ser lo suficientemente claro como para que otra persona lo modifique*. 

### Combinación de Desarrollo Mobile First y Diseño Responsivo:
Con el fin de mejorar la experiencia de usuario se recomienda preparar el contenido del sitio web para los diferentes dispositivos y plataformas y asegurarse de que es accesible de manera eficaz independientemente de la resolución o terminal con la que acceda el usuario.

Dado que actualmente el número de usuarios que acceden a los sitios web mediante un teléfono o tablet va en aumento, recomendamos que al diseñar y maquetar se tengan en cuenta, en primera instancia, los dispositivos móviles y a través del diseño responsivo ir adaptando el diseño hacia los dispositivos y pantallas más grandes del mercado, tratando de que el contenido no se deforme ni descuadre en ninguna de las medidas, ya que no podemos controlar los tamaños de pantalla que salen a la venta.

**Referencias Mobile First:**  
https://www.initcoms.com/que-es-mobile-first-posicionamiento/  
https://www.appandweb.es/blog/importancia-mobile-first/  
https://www.mediaclick.es/blog/diseno-web-responsive-design-y-la-importancia-del-mobile-first/  
https://www.idento.es/blog/desarrollo-web/que-es-mobile-first-una-buena-decision/

**Referencias Responsive Design:**  
https://devcode.la/blog/que-es-responsive-web-design/  
https://desarrolloweb.com/articulos/que-es-responsive-web-design.html  
https://www.initcoms.com/por-que-necesitas-un-sitio-web-con-responsive-design/

## Javascript
### Orden de carga de los scripts:
Para permitir la carga rápida del DOM, se recomienda añadir los elementos `<script>` al final del cuerpo (justo antes de la etiqueta `<body>`), así evitaremos que la página se quede colgada si un error en el js detiene la carga.

### Nombres de Variables y Funciones:
Cuando uses JavaScript, trata de usar nombres de variables y funciones que tengan sentido. Por ejemplo, describiendo el funcionamiento (`enviarFormulario()`,`abrirMenu()`) o el objeto al que se refiere (`contenedor`, `botonAbrir`). Para separar palabras es común usar camelCase, que consiste en escribir la primera letra de cada palabra en mayúscula, a partir de la segunda palabra.

### Uso de Patrones y encapsulamiento:
Para evitar modificar variables desde cualquier parte del código o que  existan colisiones entre funciones con el mismo nombre es importante que utilices patrones modulares o hagas tu código javascript *orientado a objetos*.

También es importante que **agrupes tus funciones por componente**, ya que esto facilitará el mantenimiento y les da independencia, pues permite que las puedas añadir o retirar sin romper el resto del código.

**Referencias:**  
https://frontendlabs.io/2643--patron-modular-en-javascript  
https://www.wextensible.com/temas/javascript-closure/encapsulamiento.html  
http://www.adequatelygood.com/JavaScript-Module-Pattern-In-Depth.html  
https://developer.mozilla.org/es/docs/Web/JavaScript/Introducci%C3%B3n_a_JavaScript_orientado_a_objetos


