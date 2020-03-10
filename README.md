 # Bootstrap 4 Maquetacion

Para instalar BootStrap 4 podemos optar por dos opciones:

Usar el los enlaces que nos proporcionan en la documentación:
El primero de ellos es el CSS de la librería


<!-- Bootstrap CSS -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/css/bootstrap.min.css" integrity="sha384-PsH8R72JQ3SOdhVi3uxftmaW6Vc51MKb0q5P2rRUpPvrszuE4W1povHYgTpBfshb" crossorigin="anonymous">
Y posteriormente si vamos a usar componentes, muchos de los cuáles no son elementos estáticos y van a requerir scripts para definir su comportamiento


<!-- Optional JavaScript -->
<!-- jQuery first, then Popper.js, then Bootstrap JS -->

<script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.3/umd/popper.min.js" integrity="sha384-vFJXuSJphROIrBnz7yo7oB41mKfc8JzQZiCq4NCceLEaO4IHwicKwpJf9c9IpFgh" crossorigin="anonymous"></script>

<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/js/bootstrap.min.js" integrity="sha384-alpBpkh1PFOepccYVYDB4do5UnbKysX5WZXm3XxPqe5iKTfUKjNkCk9SaVuEZflJ" crossorigin="anonymous"></script>
Los dos primeros scripts son para referenciar las librerías jQuery y Popper de las que depende BootStrap.

Descargar los ficheros necesarios para no tener que pedirlos cada vez que se muestre nuestra página.
Esos ficheros podemos descargarlos de aquí y en vez de usar URLs podremos referenciar los ficheros localmente.

En cualquier caso para este curso se proporciona un fichero base HTML (template.html) con todo lo necesario para poder practicar.

IMPORTANTE: Para la realización de este curso se ha usado la versión beta de BootStrap 4. Conforme los desarrolladores vayan publicando nuevas versiones habría que actualizar los enlaces.



¿Qué es un contenedor?
Un contenedor es el “padre” de todos los elementos de nuestra página web. Es una etiqueta que. como regla general, va a contener todas las otras etiquetas del contenido de nuestra página.

¿Qué tipos de contenedores nos ofrece BootStrap?
BootStrap 4 nos ofrece dos tipos de contenedores:

container : Ocupará diferentes anchos dependiendo del tamaño de la pantalla. Puede ocupar todas la pantalla o dejar unos márgenes a izquierda a derecha aunque, en este caso, siempre estará centrado.
<body>

<div class="container">

</div>

</body>
container-fluid: Ocupará todo el ancho (100%) de lo que podemos ver en el navegador.
<body>

  <div class="container-fluid">

  </div>

</body>
IMPORTANTE: Aunque los contenedores se pueden anidar unos dentro de otros son pocas las páginas que son tan complejas para necesitar contenedores anidados.



Como ya hemos hablado en el capítulo anterior es muy difícil que nos encontremos con páginas cuyos layouts sean tan complejos como para necesitar más de un contenedor. Así que, si nos ponemos de acuerdo en eso, en que sólo vamos a necesitar un contenedor, podemos fijar una estructura general que va a permanecer fijas para todos nuestros layouts:

árbol DOM en BootStrap 4

Y dentro de cada fila de cada row, en principio podemos tener hasta 12 columnas, aunque ya veremos posteriormente que dado a que BootStrap 4 utiliza contenedores flex podemos usar las propiedades de estos contenedores flex para poner más columnas aunque, en realidad, es difícil que tengamos que utilizar más.

Todas estas columnas están pegadas unas a otras y tiene siempre un padding a izquierda y a derecha de 15px del que hablaremos posteriormente.

Otra cosa importante es que no tenemos que olvidarnos de utilizar class=”row” ya que si nuestra estructura de columnas no está dentro de un contenedor con esa clase perderemos todas las propiedades de los contenedores flex, que son los sustentan la maquetación en BootStrap 4.



¿Qué es un breakpoint?
En el mundo del diseño responsivo un breakpoint es un tamaño de pantalla (en pixels) donde se produce un cambio en la disposición de los elementos que conforman nuestra página web.

Existen multitud de tipos de dispositivos, multitud de pantallas, pantallas que giran etc. Por lo tanto la elección de los distintos breakpoints no es algo trivial. Sin embargo, tenemos la suerte de que los muchachos de Twitter, usando su experiencia y los datos que sus millones de usuarios les proporcionan, has decidido que la elección más adecuada son 4 breakpoints:

En 576px
En 768px
En 992px
En 1200px
Teniendo en cuenta estos 4 breakpoints podemos diferenciar entre 5 tipos de pantallas

 Pantallas extra pequeñas: Entre 0 y 576px
 Pantallas pequeñas: Entre 576px y 768px
 Pantallas medianas: Entre 768px y 992px
 Pantallas grandes: Entre 993px y 1200px
 Pantallas extra-grandes: A partir de 1200px
Juntando todo nos queda la siguiente tabla:

Extra pequeñas	Pequeñas	Medianas	Grandes	Extra Grandes
Anchura máxima	576px	768px	992px	1200px	> 1200px
Prefijo de la clase	.col-	.col-sm-	.col-md-	.col-lg-	.col-xl-
Número de columnas	12
Anchura del Gutter	30px (1px a cada lado de cada columna)
Anidar	Sí
Reordenar columnas	Sí
De especial importancia son los prefijos CSS de las clases .col-* que son los que nos van a permitir establecer la anchura de los diferentes elementos que compongan nuestro layout. En definitiva son esas clases las que me proporciona BootStrap 4 para poder maquetar.

En el próximo apartado veremos cómo hacerlo.



En apartados anteriores vimos cuál era la estructura general de una página con BootStrap 4,vimos también cuáles eran los breakpoint establecidos y que, en principio, cada row puede contener hasta 12 columnas.

En este apartado vamos a ver como nosotros podemos establecer el tamaño de cada uno de los componentes de dicha row o filas y que además, podemos establecer distintos tamaños dependiendo del tamaño de nuestra pantallas.

Si queremos dar tamaño a cada de los componentes usaremos las clases vistas previamente, de esta manera :

col-X: hará que ese contendor X/12 columnas en pantallas extra pequeñas.
  <!-- col-6 ocupará justo la mitad en pantallas extra pequeñas -->
  <div class="col-6">
  </div>
col-sm-X: hará que ese contendor X/12 columnas en pantallas pequeñas.
  <!-- col-sm-4 ocupará un tercio de la pantalla en pantallas pequeñas -->
  <div class="col-sm-4">
  </div>
Y así sucesivamente para col-md-X para pantallas medianas, col-lg-X para pantalla grandes y col-xl-X para pantallas extragrandes.

Una cosa importante que hay que tener en cuenta es que si establecemos un tamaño para un cierto tamaño de pantallas ese tamaño se va a mantener para pantallas de mayor tamaño pero para pantallas menores ese div ocupará toda la pantalla, es decir si tenemos:


  <div class="col-md-6">
  </div>
Este div ocupará la mitad de la pantalla para pantallas de 768px (recordar los breakpoints) o superiores pero para tamaño menores ocupará todo el ancho de la fila que lo contiene.

Podemos también fijar a la vez anchos diferentes para distintos tipos de tamaños de pantallas. Para ello añadiremos varias clases a un mismo elemento, por ejemplo:


  <div class="col-sm-6 col-md-4 col-xl-3">
  </div>
En este caso ese div:

Ocupará toda la fila para pantallas extrapequeñas (<576px)
Ocupará la mitad de la fila para pantallas en 576px y 768px
Ocupará un tercio de la fila para pantallas entre 768px y 992px
Ocupará un cuarto para pantallas mayores de 992px
También es importante recordar que si, en un row nos pasamos de 12 columnas ese elemento que provoca que nos pasemos de las 12 columnas “pasará” debajo de los elementos de la fila actual ocupando el tamaño establecido.

Así por ejemplo si tenemos la siguiente estructura:

  <div class="row">
    <div class="col-md-6">
    </div>
    <div class="col-md-4">
    </div>
    <div class="col-md-4">
    </div>
  </div>
El tercer div irá abajo ya que 6+4+4 = 14 que es mayor que 12.



Es una de las novedades de BootStrap 4 que deriva directamente del uso de contenedor flex.

Usando elementos en los que no especifiquemos el número de columnas, el espacio que haya en la fila se va a distribuir de manera uniforme.

col : Para todo tipo de pantallas
col-sm : De pantallas pequeñas en adelante (>=576px)
col-md : De pantallas medianas en adelante (>=768px)
col-lg : De pantallas grande en adelante (>=992px)
col-xl : Para pantallas de 1200px en adelante
Veamos el primer ejemplo:


<div class="row">
    <div class="col red">
    </div>
    <div class="col black">
    </div>
</div>
En este caso en cualquier tipo de pantallas esos dos elementos se repartirán a igual manera el ancho del contenedor principal.

Debemos de tener cuidado porque en caso de que lo que contengan esas partes ocupe más de la mitad no se respetará esa proporción. Veamos este caso con un ejemplo:


<div class="row">
    <div class="col red">
      <h1>PRIMERA PARTE</h1>
    </div>
    <div class="col black">
      <h1>SEGUNDA PARTE</h1>           
    </div>
</div>
Si queremos que es reparto equitativo suceda para determinado de pantallas:


<div class="row">
    <div class="col-md yellow"></div>
    <div class="col-md pink"></div>
    <div class="col-md yellow"></div>
    <div class="col-md pink"></div>
    <div class="col-md yellow"></div>
</div>
En este caso todo se divide en 5 partes para pantallas menores de 768px pero en cuanto la pantalla es más pequeña que eso, todos los elementos pasarán a ocupar todo el centro de la pantalla.

Este funcionamiento abre la puerta a rows (filas) que tengan más de 12 columnas, por ejemplo una fila con 14 componentes:


<div class="row">
  <div class="col-md blue"></div>
  <div class="col-md pink"></div>
  <div class="col-md blue"></div>
  <div class="col-md pink"></div>
  <div class="col-md blue"></div>
  <div class="col-md pink"></div>
  <div class="col-md blue"></div>
  <div class="col-md pink"></div>
  <div class="col-md blue"></div>
  <div class="col-md pink"></div>
  <div class="col-md blue"></div>
  <div class="col-md pink"></div>
  <div class="col-md blue"></div>
  <div class="col-md pink"></div>
</div>
BootStrap 4 nos permite también ajustar el tamaño de las columnas al contenido de las mismas usando col-{breakpoint}-auto. Así por ejemplo:

`html <div class="row"> <div class="col-md-auto">Anchura ajustada</div> <div class="col-md-auto">Al contenido</div> <div class="col-md-auto">De las celdas que contiene la columna</div> </div>

IMPORTANTE: Debemos tener mucho cuidado cuando mezclemos tamaños automáticos junto tamaños, definidos por el usuario porque cuanto no quepan las columnas (y puede que no sumen 12) pasarán a la siguiente fila y se repartirán el espacio de la siguiente fila.



Si mientras estamos construyendo nuestro grid y queremos que haya un salto de línea podemos forzarlo de la siguiente manera:


  <div class="w-100"></div>
Con esa estructura aunque no hayamos ocupado las 12 columnas de nuestro grid podremos pasar a la siguiente fila. De esta manera:


<div class="row">

  <!-- Ocupamos 5/12 de la fila -->
  <div class="col-md-3"></div>
  <div class="col-md-2"></div>

  <!-- Forzamos el salto de línea -->
  <div class="w-100"></div>

  <!-- Ocupamos otra vez 5/12 pero en una nueva línea -->
  <div class="col-md-3"></div>
  <div class="col-md-2"></div>


</div>
Si nos damos cuenta esto mismo se podría haber conseguido utilizando varias rows (filas). De esta manera


<div class="row">

  <!-- Ocupamos 5/12 de la fila -->
  <div class="col-md-3"></div>
  <div class="col-md-2"></div>

</div>

<div class="row">

</div>

<div class="row">

  <!-- Ocupamos otra vez 5/12 pero en una nueva línea -->
  <div class="col-md-3"></div>
  <div class="col-md-2"></div>

</div>
De manera selectiva podemos establecer que ese cambio de línea se produzca en un determinado breakpoint de los establecidos por BootStrap 4.

Así por ejemplo:



Para más información podemos ver BootStrap4 Display Utilities



Por defecto BootStrap 4 introduce separación entre el contenido de las columnas mediante paddings y márgenes a derecha e izquierda. Es lo que se denomina gutter

Si ése no es el efecto que queremos en nuestra maquetación podemos evitarlo añadiendo al elemento que tenga la clase row la clase no-gutters.

Así de esta manera las columnas o elementos de la fila no tendrán ese padding con la posibilidad de que el contenido de la misma queden pegados.

Un ejemplo sería:


<div class="container">
  <div class="row">
    <div class="col-md-6"><h3>Elemento con Gutter</h3></div>
    <div class="col-md-6"><h3>Elemento con Gutter</h3></div>
  </div>

  <div class="row no-gutters">
    <div class="col-md-6"><h3>Elemento sin gutter</h3></div>
    <div class="col-md-6"><h3>Segundo Elemento</h3></div>
  </div>

</div>


Tal y como hemos visto en apartados anteriores podemos dar diferentes tamaños a los distintos componentes o columnas de una row o fila.

Adicionalmente podemos establecer no sólo el tamaño de la columna si no también la posición a partir de la cuál se va a posicionar.

Para conseguir eso debemos añadir la clase offset-X donde X es el número de columnas a la izquierda que desplazaremos el elemento que queremos posicionar.

Este desplazamiento puede ser también establecido de manera diferente para cada tamaño de pantalla:

offset-sm-X : Para desplazamientos para pantallas entre 576px y 768px.
offset-md-X : Para desplazamientos para pantallas entre 768px y 992px.
offset-lg-X : Para desplazamientos para pantallas entre 992 y 1200px.
offset-xl-X : Para desplazamientos para pantallas mayores de 1200px.
Por ejemplo:


<div class="container-fluid">
  <div class="row">
    <div class="col-sm-4 offset-md-1 red"></div>
    <div class="col-sm-4 offset-sm-4 offset-md-2 blue"></div>
  </div>
</div>
En este ejemplo para pantallas mayores de 768px el primer div está desplazado una columna a la izquierda y ambos bloques se separan dos columnas mediante el uso de un desplazamiento de dos columnas en el segundo bloque.

Además para pantallas entre 576px y 768px no hay desplazamiento para el primer bloque y hay un desplazamiento de 4 columnas para el segundo bloque consiguiendo, de esta forma que ese bloque quede totalmente pegado a la derecha.

IMPORTANTE: En esta nueva versión de BooStrap 4 hay un cambio importante en el nombre de las clases para desplazar los elementos de la fila. En versiones anteriores esas clases de denominaban col-yy-offset-X donde yy son las siglas del tamaño de la pantalla.



Como ya hemos descrito en apartados anteriores, BootStrap 4 utiliza contenedores flex. Precisamente utilizando las propiedades de estos elementos podremos fijar la alineación de los componentes de las rows o filas.

Podremos establecer:

La alineación vertical de los elementos de la fila.
La alineación horizontal de los elementos de la fila.
Tanto para establecer la alineación horizontal como la vertical deberemos añadir una nueva clase al contenedor row o fila.

Alineación vertical
Si queremos alinear los distintos elementos que componen una fila de manera vertical podremos hacerlo añadiendo a la row fila una de estas tres clases:

align-items-start : Los elementos de la fila se alinearán verticalemente con el borde superior de la fila.

 <div class="row align-items-start">
</div>
align-items-center : Los elementos de la fila se alinearán centrados verticalmente.

 <div class="row align-items-center">
</div>
align-items-end : Los elementos de la fila se alinearán verticalemtne con el borde inferior de la fila.

 <div class="row align-items-end">
</div>
Alineación horizontal
Para fijar la alineación horizontal de los elementos en la row (fila) dispondremos de las siguientes clases:

justify-content-start : Los elementos empezarán en la parte izquierda y ocuparán el tamaño horizontal establecido. Es la opción por defecto.

 <div class="row justify-content-start">
</div>
justify-content-center : Los elementos de la fila se centrarán horizontalmente.
justify-content-end : Los elementos de la fila se alinearán al final (la derecha normalmente) de la fila.
justify-content-around : El espacio restante se distribuirá de manera equitativa alrededor de los elementos empezando y acabando con espacios libres.
justify-content-between : El espacio restante se distribuirá de manera equitativa entre los distintos elementos estando uno de ellos totalmente a la derecha y otro totalmente a la izquierda.
Con todas estas posibilidades y lo visto anteriormente es más que suficiente para casi cualquier Layout pero existen más posibilidades que podremos descubrir en la documentación oficial.



BootStrap 4 añade clases que nos van a permitir modificar los márgenes y los paddings de las columnas. Según la documentación oficial son las Utilidades de espaciado.

Márgenes entre columnas
Para establecer los márgenes entre las columnas usaremos la clas m{lado}-{tamaño} o si queremos distinguir según los distintos tamaños de pantalla:

m{lado}-sm-{tamaño} Para pantallas entre 576px y 768px.
m{lado}-md-{tamaño} Para pantallas entre 768px y 992px.
m{lado}-lg-{tamaño} Para pantallas entre 992px y 1200px.
m{lado}-xl-{tamaño} Para pantallas de más de 1200px.
Pudiendo ser lado:

t para margen superior (top).
b para margen inferior (bottom).
l para margen izquierdo (left).
r para margen derecho (right).
x para los márgenes superior e inferior.
y para los márgenes izquierdo y derecho.
En blanco si es para todos los lados.
Y pudiendo ser tamaño de tamaño:

0 : No hay margen
1 : 0.25rem
2 : 0.25rem
3 : 1rem
4 : 1.25rem
5 : 3rem
auto : Para clases que establecen una margen auto
Centrado horizontal
Relacionado con el tema de los márgenes hay que destacar que BooStrap 4 introduce una nueva clase mx-auto que permite centrar horizontalmente un elemento dentro de su contenedor siempre que tenga una

Paddings
La notación de las clases para establecer los paddings en las columnas es muy similar a la notación de las clases para establecer márgenes entre las columnas. Simplemente tenemos que cambiar la m por la p


Hasta ahora estamos estado maquetando conforme a la estructura que hemos definido en apartados anteriores.

árbol DOM en BootStrap 4



Esta estructura establece una jerarquía contenedor -> row -> col, es decir, todas las filas tienen elementos que única y exclusivamente pertenecen a dicha fila.

Sin embargo, los layout reales son más complejos que eso y para conseguir esas estructuras complejas vamos a tener que anidar filas (row) dentro de filas. Debemos de tener en cuenta que cada una de esas filas hijas podrá tener, de igual manera, hasta 12 columnas.

En la siguiente imagen tenemos un ejemplo de ese tipo de layouts con las distintas filas señaladas.

Layout complejo con filas anidadas



Para aquellos que no tengan claro la diferencia entre imágenes y figuras podemos resumirlo de la siguiente manera:

Una imagen es únicamente el elemento gráfico el cual hemos añadido mediante las etiquetas img o picture.

  <img src="ejemplo.png">
Una figura (etiqueta figure) es un conjunto compuesto de una imagen (etiqueta img) y de un texto descriptivo sobre la imagen (etiqueta caption). Esta etiqueta es una de las novedades en HTML5.Tradicionalmente es lo que se usa en libros para hacer posteriormente un índice de figuras.

  <figure>
    <img src="ejemplo.png">
    <figcaption>Texto descriptivo de la imagen</figcation>
  </figure>
BootStrap 4, por supuesto, nos proporciona una serie de clases para tratar y dar estilos a este tipo de contenidos.

Imágenes
En relación a las imágenes las clases de interés son:

img-fluid : Que nos permite convertir una imagen en responsiva. Al añadir esa clase a una imagen ésta ocupará toda la anchura de su elemento padre manteniendo sus proporciones (aspect ratio).Si hemos utilizado la etiqueta picture debemos añadir esta clase a la img que contiene y no a picture.
img-thumbnail : Para añadir un marco redondeado a la imagen. Para esto podríamos también usar las clases relativas a bordes que veremos posteriormente en el capítulo sobre utilidades.
rounded . Si queremos que las esquinas sean redondeadas.
IMPORTANTE : En IE10 si la imagen es una imagen SVG no se respeta el aspect ratio.

Figuras
En relación a las figuras las clases de interés para dar estilos con BootStrap 4 son:

figure : Clase a añadir a la etiqueta figure.
figure-img : Clase a añadir a la etiqueta img que contiene la figura.
figure-caption : Clase añadir a la etiqueta figcation que contiene la figura. El texto se podrá adicionalmente alinear de distintas maneras usando text-justify, text-left, text-right o text-center.
IMPORTANTE : Si queremos que esto siga siendo responsivo debemos añadir .img-fluid a la imagen de la figura.


Mediante el uso de clases BootStrap 4 podemos dar distintos estilos a las tablas y hacerlas responsivas.

Estas clases relacionadas con tablas son muchas y en este apartado únicamente vamos a ver las más destacadas. Para más información os invito a visitar la documentación

Haciendo que la tabla sea tabla Bootstrap
Simplemente debemos añadir la clase table y adicionalmente la clase table-dark si queremos que se inviertan los colores de fondo y de letra.


  <table class="table">
      .....      
  </table>
Clases para la cabecera de las tablas
Para dar estilos a las cabecera de las tablas tenemos que las clases thead-light o thead-dark a la etiquetas de las filas (tr) o a las etiquetas (thead).


  <thead class="thead-light">
      <tr>
        <th>...</th>
        ......
      </tr>
  </thead>
IMPORTANTE : Este estilo sólo se aplica a la etiqueta th (celdas de cabecera).

Alternado colores
Si queremos que las filas de las tablas tengan colores alternativos para poder distinguirlas mejor debemos añadir la clase table-striped a la etiqueta table. Esto funcionará también para tablas oscuras (clase table-dark).


  <table class="table table-striped">
      .....      
  </table>
Destacar
Si queremos que conforme pase el puntero de ratón por encima de una fila (que no sea la cabecera) esa fila de destaque cambiando ligeramente de color debo añadir las clase table-hover a las etiqueta table.


  <table class="table table-hover">
      .....      
  </table>
Bordes de las tablas
Por defecto en BootStrap 4 las tablas únicamente muestran unos ligeros bordes inferiores en las filas para separar estas. Si, por el contrario, queremos que todas las celdas muestren los 4 bordes (inferior,superior, derecha e izquierda) debemos añadir la clase table-bordered a la etiqueta tabla.


  <table class="table table-bordered">
      .....      
  </table>
Haciendo las tablas responsivas
Hasta ahora únicamente hemos visto como BootStrap 4 da estilos a las tablas pero, como ya habrá quedado patente durante todo lo que llevamos de curso, la verdadera potencia de esta librería reside en la facilidad que nos da para hacer las páginas responsivas.

Existen distintas técnicas para hacer las tablas responsivas pero los desarrolladores de BootStrap 4 han optado porque aparezca un scroll horizontal cuando sea necesario.

Para conseguir esto debemos insertar nuestra tabla dentro un div con las clase BootStrap table-responsive

  <div class="table-responsive">
    <table class="table table-bordered">
        .....      
    </table>
  </div>
También puedo fijar el breakpoint a partir de la cual quiero que la tabla sea responsiva. En esos casos usaré:

table-responsive-sm
table-responsive-md
table-responsive-lg
table-responsive-xl


Aunque en la documentación oficial los formularios se encuentran en la sección de componentes lo cierto es que son un elemento fundamental que se incluye en páginas de registro, de consulta, de búsqueda etc. Por esa razón se ha decidido tratarlos de manera breve en este curso.

BootStrap proporciona una serie de clases para dar estilos a los distintos elementos de los formularios. De manera general podemos describir estas clases y la jerarquía que deben ocupar de la siguiente manera:

Estructura general de los formularios

Además, se le añadirá al final un input de tipo submit o button con las clases correspondientes a los botones cuyos ejemplos más comunes (hay muchos más) son:

btn btn-primary
btn btn-secondary
btn btn-success
btn btn-danger
btn btn-warning
Podemos además modificar ciertos aspectos de estos componentes del formulario. Los más interesantes son los siguientes.

Modificar el tamaño en altura del control. Añadiendo clases como form-control-lg (grande) o form-control-sm (pequeños) en los form-control.
Modificar el tamaño en altura de la etiqueta del control. Usando clases como col-label-lg (grandes) o col-label-sm (pequeños).
Hacer que todos los elementos del formulario se vean en la misma línea añadiendo la clase form-inline a la etiqueta form.
Hacer que las distintas opciones para elementos radio o checkbox se vean en la misma línea añadiendo al div que tenía la clase form-check la clase form-check-inline
Añadir texto de ayuda a los diferentes elementos usando un etiqueta small dentro del form-group o form-check y dando a esa etiqueta las clases form-text y text-mute.
En cuanto a su disposición, los formularios por defecto ocupan en anchura lo que ocupen el contenedor padre al que corresponden pero podemos adaptar su tamaño jugando con el grid de BootStrap 4 que hemos visto en capítulos anteriores añadiendo clases col-X (o atendiendo a distintos breakpoints) al elemento que contenga la clase form-group o form-check.

Para hacer los formularios más compactos hay una nueva clase que suprime el gutter, form-row que debe ser usada en ves de row.

Bootstrap 4 proporciona muchas más cosas en relación a los formularios, por eso, aunque con estos apuntes ya es suficiente para empezar a trabajar sin problemas, os recomiendo mirar tranquilamente la documentación.


Para entender lo que es un objeto media lo mejor es irnos a la propio definición que nos da BootStrap 4:

“son elementos complejos y repetitivos en los cuáles algún elemento multimedia (una imagen normalmente) se posiciona junto a otro elementos que “

¿ Y éso qué es?. Pues son cosas que vemos diariamente como anuncios en la web, comentarios en blogs que llevan fotos de perfil, listas de tweets etc…

BootStrap 4 nos proporciona una manera fácil de construir este tipo de estructuras utilizando elementos flex, clases y etiquetas que compongan la siguiente jerarquía:

Object Media en BootStrap 4

Por ejemplo:


  <div class="media">
    <img src="..." />
    <div class="media-body">
      <h3>Titulo</h3>
      <p>Texto relacionado</p>
      ...
    </div>
  </div>
Este tipo de estructuras se pueden anidar (como lo comentarios y las respuestas a un post).

Podemos también decidir cómo se van a disponer el resto de los elementos alrededor de la imagen usando clases como las siguiente y los márgenes correctos:

align-self-start : Que alinea el contenido verticalmente con el borde superior de la imagen.
align-self-center : La imagen queda centrada verticalmente en relación al resto de los elementos.
align-self-end : Que alinea el contenido verticalmente con el borde superior de la imagen.
Si queremos que la imagen salga a la derecha sólo tenemos que cambiar la etiqueta en el HTML.


  <div class="media">
    <div class="media-body">
      <h3>Titulo</h3>
      <p>Texto relacionado</p>
      ...
    </div>
    <img src="..." />
  </div>
Si queremos construir listas (como si fuera el timeline de twitter debemos ponerle la clase media a los elementos las etiquetas li que sustituirán al div.media anterior)

Por ejemplo:


    <ul>
      <li class="media">
        <img src="..." />
        <div class="media-body">
          <h3>Titulo 1</h3>
          <p>Texto relacionado</p>
          ...
        </div>
      </li>
      <li class="media">
        <img src="..." />
        <div class="media-body">
          <h3>Titulo 2</h3>
          <p>Texto relacionado 2</p>
          ...
        </div>
      </li>

    </ul>
IMPORTANTE : Debemos darle las dimensiones a las imágenes.


Los elementos embebidos son algo común en todas las webs , vídeos de youtube, reproductores de canciones de spotify, presentaciones de slideshare están embebidas o incrustadas por todos los sitios.

Desde el punto de vista más técnico nos estamos refiriendo a las etiquetas iframe,embed,video y object

Para hacer estas etiquetas responsivas debemos añadir la clase embed-responsive a un elemento que la contenga y la clase embed-responsive-item a la etiqueta en cuestión. Algo así:


  <div class="embed-responsive">
      <iframe src="..." class="embed-responsive-item"></iframe>
  </div>
Adicionalmente podemos modificar las proporciones elementos (su aspect ratio) añadiendo al elemento padre clases que lo modificarán:

embed-responsive-21by9 : Aspect Ratio 21x9
embed-responsive-16by9 : Aspect Ratio 16x9
embed-responsive-4by3 : Aspect Ratio 4x3
embed-responsive-1by1 : Aspect Ratio 1x1


