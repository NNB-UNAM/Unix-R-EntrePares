---
layout: workshop      # NO CAMBIAR ESTO 
carpentry: "swc"    
venue: "BUAP, Puebla"        
address: "Complejo Cultural Universitario Benemérita Universidad Autónoma de Puebla"   
country: "MX"      
language: "ES"     
latlng: "19.041439,-98.206276"
humandate: "Sep 10-11, 2018"   
humantime: "4:00 pm - 7:00 pm" 
startdate: 2018-09-10      
enddate: 2018-09-11        
instructor: ["Verónica Jimenez", "Daniela Ledezma", "Delfino García", "Heladia Salgado"] 
helper: ["Pablo Peña Loredo", "Oscar Gabriel Caballero Martínez", "Gabriel Martínez Posadas", "Daniel Bustamante Martínez", "Shirley Alquicira H."]  
email: ["contacto.nnb@gmail.com"]    
collaborative_notes:             # optional: URL de las notas colaborativas del taller, por ejemplo un Etherpad o documento de Google Docs 
eventbrite:           
---

{% comment %} Ver en los comentarios que siguen las instrucciones sobre cómo editar secciones específicas de esta plantilla de taller {% endcomment %}

{% comment %}
  ENCABEZADO

  Edita los valores en el bloque de arriba para tu taller.
  Si el valor no es 'true', 'false', 'null', o un número, por favor usa
  comillas dobles alrededor del valor, salvo que se especifique de otro modo.
  Por último ejecuta 'make workshop-check' *antes* de comitear para asegurarte que los cambios estan bien.
{% endcomment %}

{% comment %}
  EVENTBRITE

  Este bloque incluye el widget para registro en Eventbrite, en caso de que 'eventbrite' haya sido especificado en el encabezado. Puedes borrarlo si no estás usando Eventbrite, o dejarlo, ya que no se mostrará si el campo 'eventbrite' en el encabezado no fue especificado. 
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}



<h1>ENTRE PARES (2018): Introducción a Unix y R aplicado a la Bioinformática</h1>

<h2 id="general">Información General</h2>

{% comment %}
  INTRODUCCIÓN 

  Edita el párrafo introductorio general debajo si quieres modificar la presentación.
  
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  PÚBLICO

  
  {% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  UBICACIÓN

   Complejo Cultural Universitario
   Benemérita Universidad Autónoma de Puebla

   Puebla, Puebla
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Dónde:</strong>
  {{page.address}}.
  Obtener direcciones con:
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  o
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
  FECHA

  Este bloque muestra la fecha y enlaces a Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>Cuándo:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  REQUERIMIENTOS ESPECIALES
  
  Modifica este bloque si hay algún requerimiento especial.
{% endcomment %}
<p id="requirements">
  <strong>Requerimientos:</strong> Las asistentes deben traer una computadora portátil con sistema operativo Mac, Linux o Windows (no tablet, Chromebook, etc.), que tenga permisos de administradora habilitados. Deben tener algunos paquetes de software específicos instalados (listados <a href="#setup">aquí</a>). 
	
También es requerido que respeten el 
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Código de Conducta</a>. 
</p>


{% comment %}
  DIRECCIONES DE CORREO ELECTRÓNICO DE CONTACTO

  Muestra los correos electrónicos de contacto definidos en el archivo de configuración.
{% endcomment %}
<p id="contact">
  <strong>Contacto</strong>:
  Por favor escribe a
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        o
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    a ser anunciado
  {% endif %}
  para más información.
</p>

<hr/>

{% comment %}
  SCHEDULE



 Muestra el cronograma del taller. Edita los ítems y horarios en la tabla para ajustarlos a tu planificación. Puede que quieras modificar 'Día 1' y 'Día 2' para mostrar fechas concretas o días de la semana.

{% endcomment %}
<h2 id="schedule">Cronograma</h2>

{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% endif %}

{% comment %}
  Notas de colaboración

  Si quieres usar un Etherpad, ve a

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  donde 'YYYY-MM-DD-site' es el identificador de su taller,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
 Utilizaremos este <a href="{{page.collaborative_notes}}"> documento colaborativo </a> para chatear, tomar notas y compartir URL y fragmentos de código.
</p>
{% endif %}

<hr/>

{% comment %}
  CURRICULA

  En inglés, syllabus. Muestra que tópicos van a ser cubiertos.

  1. Si tu taller es sobre R antes que Python, remueve el comentario
     alrededor de esa sección y pon un comentario alrededor de la sección Python.
  2. Algunos talleres van a remover SQL.
  3. Por favor asegúrate que la lista de tópicos está sincronizada con lo que
     pretendes enseñar.
  4. Podría ser que necesites mover los campos div con class="col-md-6" alrededor
     dentro de los div con class="row" para balancear el diseño multi-columnar.

  Este es uno de los lugares donde la gente frecuentemente comete errores, así que
  por favor observa la previsualización del sitio antes de comitear, y asegúrate
  de ejecutar también 'tools/check'.
{% endcomment %}
<h2 id="syllabus">Currícula</h2>

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
  CONFIGURACIÓN
 
  Borra las secciones irrelevantes de las instrucciones de configuración. Cada sección esta dentro de un 'div' que no contiene clases para que el comienzo y el final sean más fáciles de encontrar.
  Este es otro lugar en donde las personas cometen errores de forma más frecuente, por favor previsualiza tu sitio antes de commitear y además asegurate de ejecutar 'tools/check'.
  
{% endcomment %}

<h2 id="setup">Configuración</h2>

<p>
  Para participar en un taller de
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  ,
  necesitarás acceso a algunos de los programas descritos abajo.
  Además, necesitarás un navegador actualizado.
</p>
<p>
  Mantenemos una lista de problemas comunes que ocurren durante la instalación como referencia para los instructores que pueden ser útiles en la 
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>La terminal Bash</h3>

  <p>
    Bash es una de las terminales más frecuentemente utilizadas, que te permite realizar tareas simples de forma rápida.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <ol>
	 <li>Usaremos <a href="http://mobaXterm.mobatek.net">MobaXTerm</a>  como emulador de un ambiente unix</li>
	 <li>Sigue las instrucciones del tutorial que se te envió.</li>    
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">macOS</h4>
      <p>
        La terminal por defecto en todas las versiones de macOS es Bash, así que no es necesario instalar nada. Puedes acceder a Bash desde la Terminal (se encuentra en
        <code>/Applications/Utilities</code>).
        Puedes ver el <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a> de instalación de Git a modo de ejemplo de cómo abrir la Terminal. 
	Puede que quieras mantener la Terminal en tu dock para este taller. 
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        La consola por defecto es generalmente Bash, pero si tu máquina está configurada de forma distinta puedes ejecutarla abriendo una terminal y escribiendo <code>bash</code>. No hay necesidad de instalar nada.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}

<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>Text Editor</h3>

  <p>
	Si accidentalmente encuentras dificultades, prueba typing la tecla  
escape, seguido por <code>:q!</code>(colon, olon, lower-case 'q',
    exclamation mark),
	...
	Cuando estás escribiendo código, es bueno tener un editor de texto que sea
    optimizado para escribir código, con características como automático
    código de color de las palabras clave. El editor de texto predeterminado en macOS y
    Linux usualmente se establece en Vim, que no es famoso por ser
    intuitivo. Si accidentalmente te encuentras atascado en él, intenta
    escribiendo la clave de escape, seguido de <code>: q! </code> (dos puntos, minúscula 'q',
    signo de exclamación), luego presionando Volver para regresar al intérprete de comandos.
</p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
      <p>
	nano es un editor básico y el predeterminado que usan los instructores en el taller.
	Para instalarlo,
	Descargas el<a href="{{site.swc_installer}}">
          {% if page.carpentry == "swc" %}
          Software Carpentry
          {% elsif page.carpentry == "dc" %}
          Data Carpentry
          {% elsif page.carpentry == "lc" %}
          Libreria Carpentry
          {% endif %}
          Instalador de Windowns
	</a>
	 y doble click en el archivo para correrlo.
        <strong>Esta instalación requiere una conexión a Internet.</strong>
      </p>
      <p>
        Otros editores que puedes usar son
        <a href="http://notepad-plus-plus.org/">Notepad++</a> or
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
        <strong>
	Ten en cuenta que debes
        agregar tu directorio de instalación a la ruta del sistema. </strong>
        Por favor, Pídele a tu instructor que te ayude a hacer esto.
	</p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx">macOS</h4>
      <p>
	nano es un editor básico y el predeterminado que usan los instructores en el taller.
        Mira la instalacion de Git <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
       	Para un ejemplo sobre como abrir nano.
        Debe estar preinstalado.
	</p>
      <p>
	Otros editores que puedes usar son
        <a href="http://www.barebones.com/products/textwrangler/">Text Wrangler</a> or
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-linux">Linux</h4>
      <p>
	nano es un editor básico y el predeterminado que usan los instructores en el taller. 
	Para instalarlo,
      </p>
      <p>
	Otros editores que puedes usar son
        <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>,
        <a href="http://kate-editor.org/">Kate</a> or
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'editor' section. {% endcomment %}

<div id="r"> {% comment %} Start of 'R' section. {% endcomment %}
  <h3>R</h3>

  <p>
    <a href="http://www.r-project.org">R</a> es un lenguaje de programación 
    especialmente poderoso para exploración de datos, visualización y  
    análisis estadístico. Para trabajar con R, usamos
    <a href="http://www.rstudio.com/">RStudio</a>.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="r-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=q0PjTAylwoU">Video Tutorial en inglés </a>
      <p>



        Instala R descargando e instalando
        <a href="http://cran.r-project.org/bin/windows/base/release.htm">este archivo .exe </a>
        desde <a href="http://cran.r-project.org/index.html">CRAN</a>.
        Además, instala el entorno de desarrollo integrado, en inglés Integrated Development Environment (IDE) 
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio</a>.
        Ten en cuenta que si tienes cuentas separadas de usuario y administrador,
	debes correr los instaladores como administrador (haz click derecho en el 
        archivo .exe y selecciona "Ejecutar como administrador" en lugar de hacer doble click)  
        De lo contrario pueden ocurrir problemas, por ejemplo, cuando instales paquetes de R.


      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=5-ly3kyxwEg">Video Tutorial en inglés</a>
      <p>
        Instala R descargando e instalando
        <a href="http://cran.r-project.org/bin/macosx/R-latest.pkg">este archivo .pkg </a>
        desde <a href="http://cran.r-project.org/index.html">CRAN</a>.
        Además, instala el entorno de desarrollo integrado, en inglés Integrated Development Environment (IDE) 
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-linux">Linux</h4>
      <p>
        Puedes descargar los archivos binarios para tu distribución
        desde <a href="http://cran.r-project.org/index.html">CRAN</a>. O
        puedes usar tu administrador de paquetes (por ejemplo: para Debian/Ubuntu
        corre <code>sudo apt-get install r-base</code> y para Fedora corre
        <code>sudo dnf install R</code>).  Además, por favor instala el entorno de desarrollo integrado, 
	en inglés Integrated Development Environment (IDE) 
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio</a>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'R' section. {% endcomment %}




{% comment %}
<div id="vm">
  <h3>Máquina Virtual</h3>

  <p>
      Algunos instructores prefieren que los alumnos utilicen una máquina virtual
      en lugar de instalar software en sus propias computadoras. Si tus
      instructores han elegido hacer esto, por favor: 
  </p>
  <ol>
    <li>
      Instalar <a href="https://www.virtualbox.org/">VirtualBox</a>.
    </li>
    <li>
      Descarga nuestra <a href="{{site.swc_vm}}">imagen de máquina virtual</a>.
      <strong>Advertencia:</strong> este archivo pesa 1.7 GByte, entonces por favor
      descárgalo <em>antes</em> de venir al taller.
    </li>
    <li>
      Carga la máquina virtual en VirtualBox seleccionando "Importar dispositivo" 
      y cargando el archivo <code>.ova</code> .
    </li>
  </ol>
</div>
{% endcomment %}
