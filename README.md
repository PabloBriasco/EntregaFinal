# EntregaFinal
Entrega Final del proyecto correspondiente al curso de Desarrollo Web de la plataforma Coder House

Plataforma: Coder House.
Curso: Desarrollo Web.
Comisión: 37200.
Profesor: Fede Gilles.
Alumno: Pablo Briasco.

Objetivo del proyecto: crear un sitio web estático utilizando el conocimiento aprendido durante el curso. El sitio web debe contar con al menos 5 archivos HTML linkeados entre sí. Se explicará a continuación como se armó el sitio web.

Asunto del proyecto: Se eligió realizar una Fan Page de la serie "One Piece". Se trató de copiar el estilo de una wiki, donde se vuelca la mayor cantidad de información posible de la serie y las páginas se encuentran interconectadas por las referencias en el contenido. 

Elementos comunes a cada archivo HTML:

- Body: Para el body se utilizó una imagen de fondo estática (no se mueve con scroll). En el archivo de SASS "general.scss" está el detalle de como se hizo. La imagen de fondo luego fue superpuesta por el fondo de cada página por cuestiones estéticas.

- Links: se modificó el estilo default de los links. Se eliminó el subrayado y se cambió el color por rojo. (para el color se utilizaron las funciones de SASS each y extend).

- Box Sizing: Se utilizó border-box para todas las boxes del proyecto.

- Header: el header está compuesto por el Banner de la página y el nombre de la misma, "Camino a Laugh Tale". En el caso del index, se agregó animación de entrada al Banner. Se aplicaron estilos de texto al título de la página. El tamaño del banner se modificó utilizando Media Queries para mantener la proporción. La animación del Banner se hizo mediante un CDN.

- Nav: Para el Nav se utilizó una lista vertical para los anchos de pantalla más grandes, y un estilo de grilla para los anchos más chicos. El posicionamiento del Nav dentro de la página se hizo de dos maneras distintas: para las páginas que usan posicionamiento con grid-area, se hizo modificando el grid-template-areas. Para las páginas que usan posicionamiento con grid de Bootstrap, se utilizó flex-wrap reverse para cambiar el orden del Header y el Nav. Se utilizó :hover para los elementos del Nav.

- Footer: Para el footer se utilizó un cuadro simple de texto con fondo de color. El texto es un disclaimer con links a los sitios oficiales de la serie. 

- Clase Wrapper: para cada página se utilizó una clase wrapper justo debajo del body. Esta clase wrapper tiene un ancho máximo para que en los viewport más grandes no se estire demasiado el contenido. Además las clases wrapper cuentan con un fondo de color propio que tapa la imagen del fondo del body. Este color es un gradiente vertical descendiente de blanco a celeste.


Elementos de cada página:

- Index: El index se compone del texto de bienvenida al sitio, una breve sinopsis de la serie, una descripción de la geografía de la misma y tablas con descripciones de las "frutas del diablo". Se agregó para los viewport más grandes un aside con dos videos de Youtube con los openings y endings de la serie. Para formatos más chicos se retiró este aside ya que el tamaño del embed generaba scroll horizontal. Se agregó también para los viewport más grandes un carrousel con "novedades" de la serie. Esto es a fines puramente decorativos, no son links a ninguna página.
Para el display del index se utilizó grid-template-areas, la cual se fue modificando con Media Queries.

- Mugiwaras: en esta página están los datos de la tripulación pirata del protagonista. Se utilizó para el posicionamiento la grilla de Bootstrap (container-fluid, rows y columns). Para la presentación de la información se utilizó el componente card-group de Bootstrap. Se utilizó este elemento a fin de que todas las tarjetas quedasen con el mismo tamaño independientemente del contenido. Para acomodar el contenido a los distintos viewport se utilizaron directamente las clases de Bootstrap (col-md-6 col-lg-4) para ajustar el espacio que ocupa cada card según el viewport.

- Historia: en esta sección se resume lo sucedido en la serie desde su comienzo hasta la actualidad. Se utilizó un formato simple de títulos, subtítulos y texto, seguido de 3 imágenes/gifs para cada descripción. No se utilizaron componentes de Bootstrap pero si se utilizaron muchas clases de estilizado de Bootstrap para padding, márgenes y tamaños de fuente. El posicionamiento se hizo mediante grid de bootstrap.

- Marina: esta página cuenta con dos secciones: la primera, es una lista con los rangos de la Marina. Para los viewport más grandes se agregó también una imagen de ayuda visual. La segunda sección contiene información de algunos miembros de la Marina. Para esta segunda sección se utilizó el componente de Bootstrap Collapse, con corrimiento horizontal. No se logró que todos los componentes ocupen el mismo tamaño, independientemente del contenido. Para el posicionamiento y el responsive se utilizó la grid de Bootstrap.

- Otros Piratas: en este HTML se agregó información de otras organizaciones piratas de esta serie. Para el posicionamiento y responsive se utilizó grid de Bootstrap. Esta página cuenta con dos secciones: La primera, "Yonkos", son una serie de títulos, texto e imágenes. Para la segunda sección, "Shichibukai", se utilizó el componente de Bootstrap Accordion. Dentro de cada elemento del accordion se ubicó una imagen y un texto que se reorganizan según el viewport para que sea responsive.

- Contacto: En esta sección se utilizó posicionamiento mediante grid-template-areas. Para el formulario de contacto se utilizaron elementos de Bootstrap. Para los viewport más grandes se agregó una imagen y una frase con color de background animado utilizando diferentes gradientes. Los keyframes de dicha animación se encuentran en el archivo de SASS "general.scss".


SASS:

Propio: para el scss propio se utilizaron las funciones maps y each para generar cuatro clases con colores de texto. Estas clases luego se agregaron donde correspondía utilizando la función extend. Se utilizó también la función extend para copiar formatos comunes entre distintas clases. Se creó un archivo de SASS con los mixins, los cuales se utilizaron principalmente para el estilizado de las cajas de texto. Se creó también un mixin para encabezados.

Se creó un archivo scss para cada sector común a todos los HTML (header, nav, footer) y un scss para cada página. También se creó un scss aparte para el cuadro de título de cada página. 

Se creó un archivo scss para todas las variables, y se creó otro con cuestiones generales para todas las páginas.


Bootstrap: se descargaron los archivos scss de Bootstrap para hacerles muy pequeñas modificaciones para que se ajustasen a nuestro formato cuando correspondiese. Se modificaron los colores del componente accordion y márgenes del row.


