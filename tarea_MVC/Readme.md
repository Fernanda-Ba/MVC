# MVC
<p align="center">
    <img src="https://miro.medium.com/max/3840/1*W8l3eAbfJRzRLVkipzAMVw.png" width="420" height="300"/>
</p>

## Introducción

MVC (Model-View-Controller ó Modelo Vista Controlador es una propuesta de diseño de software que separa los datos de una aplicación, la interfaz de usuario, y la lógica de control en tres componentes distintos el modelo, la vista y el controlador. 
Fue desarrollado en el Centro de Investigaciones Xerox Corporation a finales de los años setenta en California por Trygve Reenskaug.
La arquitectura es un paradigma de programación bien conocido para el desarrollo de aplicaciones con interfaz gráfica de usuario (GUI). 
Es un patrón de software que separa los componentes de aplicación en tres niveles por sus diferentes responsabilidades.

Como se mencionó anteriormente, el patrón de diseño MVC es constituido por tres componentes:
- Modelo: Contiene sólo los datos de aplicación más puros, no contiene ninguna lógica que describa cómo presentar los datos a un usuario.
- Vista: presenta los datos del modelo al usuario. La vista sabe cómo acceder a los datos del modelo, pero no sabe qué significa esta información o qué puede hacer el usuario para manipularla.
- Controlador: Existe entre la vista y el modelo. Escucha los eventos desencadenados por la vista y ejecuta el procedimiento adecuado a estos eventos.

>https://docs.microsoft.com/es-es/aspnet/mvc/overview/older-versions-1/overview/asp-net-mvc-overview

Un patrón de diseño es:
- Una solución estándar para un problema común de programación.
- Una técnica para flexibilizar el código haciéndolo satisfacer ciertos criterios.
- Un proyecto o estructura de implementación que logra una finalidad determinada.
- Un lenguaje de programación de alto nivel.
- Una manera más práctica de describir ciertos aspectos de la organización de un programa.
- Conexiones entre componentes de programas.
Por lo tanto MVC es un patrón de diseño.

>https://www.campusmvp.es/recursos/post/que-es-el-patron-mvc-en-programacion-y-por-que-es-util.aspx

## Desarrollo

El modelo MVC utuliza frameworks, pero para entender bien primero tenemos que saber que es un frameworks.

### ¿Qué es un framework?

Es una estructura conceptual y tecnológica de soporte definido, normalmente con artefactos o módulos de software concretos, que puede servir de base para la organización y desarrollo de software. Vamos, una manera de hacernos más fácil la programación.

>https://www.orix.es/que-es-un-framework-y-para-que-se-utiliza

Entonces **¿Qué frameworks utiliza MVC?**

En la actualidad existen muchos frameworks para MVC, a continuacion se mencionaran 2 de los utiliazados:
1. **Framework Struts**

truts es un framework de aplicación web open source desarrollado por Apache. Struts está basado en el patrón MVC. Se utiliza para construir aplicaciones Web basadas en Servlets y JSP que pueden ejecutarse en cualquier contenedor de servlets incluyendo los servidores de aplicaciones J2EE. Mediante Struts se hace uso de patrones de diseño J2EE que son útiles en la construcción de aplicaciones J2EE. Y puesto que Struts sigue los patrones incluidos en el MVC, este framework es relativamente simple de usar y aprender

Struts proporciona al desarrollador un conjunto de etiquetas JSP personalizadas que facilitan la integración del framework con las páginas JSP.

**Las principales características de Struts son las siguientes:**

- Modelo Correcto. Permite modelar las aplicaciones basadas en JSP y Servlets mediante el uso del patrón de diseño MVC
- Objetos “listos para usar”. Struts incorpora el concepto de objetos “listos para usar” a través de ficheros de configuración en XML.
- Patrones de Diseño pre-construidos. Struts incluye patrones de diseño internos en el framework. Por lo que no se ha de preocupar de crear los propios patrones de diseño.
- Características Extras. Incorpora características extras como validación, internacionalización, etc. 

**Ventajas de Struts**

- Transporte automático de los datos introducidos en el cliente (JSP) hasta el controlador (Action) mediante formularios (ActionForm). 
- Transporte automático de los datos enviados por el controlador (Action) a la parte de presentación (JSP) mediante formularios (ActionForm).
- Implementa la parte común a todas las aplicaciones en la parte de Controlador (ActionServlet); la parte particular de cada aplicación es fácilmente configurable (struts-config.xml).
- La separación de los componentes en capas (MVC) simplifica notablemente el desarrollo y su mantenimiento. 

**Desventajas de Struts**

El hecho de no abarcar todas las capas de la aplicación web (deja fuera la capa de negocio y la capa de persistencia) hace que el interfaz entre Struts y estas capas no esté tan automatizado, convirtiendo los accesos a los datos (DAO) en monótonos de desarrollar.

2. **Framework Spring**

Spring es un framework open source que proporciona un marco de trabajo para el desarrollo de aplicaciones J2EE. El framework está basado en el uso de ficheros planos JavaBeans para la lógica de aplicación y archivos XML para la configuración.

**Las principales características de Spring son las siguientes:**

- Soporta: JTA, hibernate, JDO, JDBC, ODBC.
- Usa implementaciones ORM de terceros como Hibernate, Ibatis, JDO, OJB.
- Provee servicios de aplicación en forma declarativa.
- Permite usar archivos XML de configuración, programación mediante la API y mediante un estándar JSR.
- Aporta integración con la solución de código abierto Acegi (soporta seguridad declarativa basada en el uso de IoC y AOP).
- Permite el uso de cualquier servicio usando un archivo XML de configuración.
- Todos los componentes pueden ser testeados fuera del contenedor. 

**Ventajas**

- Spring recomienda el uso de Interfaces, si se decide no utilizar Spring, basta con reimplementar las interfaces.
- Spring se puede ejecutar dentro de un contenedor Web o fuera de él en una aplicación Swing. 

**Desventajas**

- La configuración de Spring es compleja ya que para cada servicio que se tenga se ha configurarlo en un XML de configuración. Aunque hay otras formas de configuración de Spring aparte del XML puro: programando por medio de la API, mediante un estándar JSR y con un mínimo XML y anotaciones.
- No se puede evaluar si un objeto ha sido bien inyectado más que en tiempo de ejecución. 
- El contenedor de Spring no es ligero (si se usan todos los módulos disponibles), no es recomendable su uso en aplicaciones de tiempo real o en aplicaciones para móviles.

>http://www.nosolounix.com/2010/03/frameworks-modelo-vista-controlador-mvc.html

## ¿Qué ventajas tiene el MVC?

Esta tecnología se centra en la escalabilidad, y permite a su vez dividir el trabajo entre un grupo de profesionales, al estar sus componentes separados entre sí.

Entre las principales ventajas que puede ofrecernos un desarrollo MVC podemos destacar las siguientes:

- Separación clara de dónde tiene que ir cada tipo de lógica, facilitando el mantenimiento y la escalabilidad de nuestra aplicación.
- Sencillez para crear distintas representaciones de los mismos datos.
- Facilidad para la realización de pruebas unitarias de los componentes, así como de aplicar desarrollo guiado por pruebas (Test Driven Development o TDD).
- Reutilización de los componentes.
- No existe ciclo de vida de las páginas. Con menos peso, menos complejidad.
- Motor de Routing asociando una URL concreta con su correspondiente controlador, permitiendo URL semánticas. Las URL semánticas se indexan mejor en los buscadores, siendo más adecuadas para el posicionamiento web.
- Recomendable para el diseño de aplicaciones web compatibles con grandes equipos de desarrolladores y diseñadores web que necesitan gran control sobre el comportamiento de la aplicación.

>https://marketiweb.com/empresa/blog/item/114-que-es-la-arquitectura-mvc-y-cuales-son-sus-ventajas

## ¿Que otros modelos/frameworks existen de patrones de diseño?

A continiacón me muestran otros framework que se utilizan

   Frameworks MVC   

- Ruby on Rails Framework MVC basado en Ruby, orientado al desarrollo de aplicaciones web 
- CodeIgniter     Poderoso framework PHP liviano y rápido 
- Kohana         Un fork de CodeIgniter 
- Django          Framework Python que promueve el desarrollo rápido y el diseño limpio
- CakePHP         Framework MVC para PHP de desarrollo rápido
- Zend Framework  Framework para PHP 5, simple, claro y open-source
- Yii             Framework PHP de alto rendimiento basado en componentes
- Pylons          Framework web para Python que enfatiza la flexibilidad y el desarrollo rápido
- Catalyst        Framework para aplicaciones web MVC elegante
- Symfony         Framework full-stack



## Resultados 

En el siguiente link se encuentra un ejemplo de MVC

>https://drive.google.com/file/d/10bTtDsA-t00i-nI0EaA44IzgNVWiC3-Y/view?usp=sharing

**Ejemplos de FrameWorks**

Aunque ya hemos visto algunos ejemplos de Frameworks, veamos un recopilatorio, dependiendo del lenguaje de programación que te pueda itneresar.
Frameworks basados en JavaScript

Algunos frameworks basados en JavaScript:

    Angular JS: framework creado por Google.
    React JS: framework creado por Facebook.

Frameworks PHP

Frameworks basados en PHP, nos ofrece todo lo necesario para crear páginas web.

    Laravel.
    Symfony.
    Zend Framework.
    CodeIgniter.
    CakePHP.
    Yii.
    Phalcon.
    FuelPHP.

Frameworks para programar entornos web

Separamos de los FrameWorks PHP, porque aquí podemos encontrar

    Ruby on Rails: basado en Ruby.
    Django: basado en Python.
    Pylons: otro framework de Python.
    Catalyst: basado en Perl.

Frameworks para crear apps móviles

También tenemos algunos entornos para poder crear aplicaciones para móviles, independientemente del lenguaje base del sistema operativo, ya sea para iOS o Android.

    Ionic: usa HTML, JS, SASS y Angular.
    Meteor: se programa en JavaScript.
    JQuery Mobile: basado en HTML5.
    PhoneGap: de Adobe.

Frameworks de Java

Para Java también tenemos entornos para crear aplicaciones.

    Spring MVC: utlizado sobretodo para entornos web.
    Struts 2: también para aplicaciones web.
    Hibernate: su utiliza sobretodo para controlar el acceso a bases de datos.
    JSF: el framework de Oracle.
    Google Web Toolkit: google también nos ofrece un framework de Java.
    Grails: otro framework web.
    
 <p align="center">
    <img src="https://programaenlinea.net/wp-content/uploads/2018/03/yii-framework.png" width="420" height="300"/>
</p>
    
 >https://lenguajesdeprogramacion.net/diccionario/que-es-un-framework/
    
 ## Conclusión
 
El patrón arquitectónico MVC favorece el diseño de sistemas software. Es un patrón que mantiene elevado el grado de desacoplamiento y todas esas virtudes contribuyen a simplificar el diseño de aplicaciones complejas que, de otra forma, resultarían mucho más difíciles de abordar y mantener.

El framework es un diseño re-usable de un sistema, se puede considerar como una aplicación genérica incompleta y configurable a la que podemos añadirle las últimas piezas para construir una aplicación concreta, ctualmente existen muchos frameworks disponibles para el desarrollo del MVC.

