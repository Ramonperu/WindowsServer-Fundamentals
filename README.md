# FUNDAMENTALS WINDOWS SERVER 2016

Bienvenidos a la guía básica, para principiantes, sobre Windows Server 2016 realizada por Ramon Peinado Ruiz.

## CONCEPTOS BASICOS

Requisitos mínimos para la instalación de Windows Server

<img src="/img/3ºimagenn.PNG"  />

Cuando se instala Windows Server 2016 mediante  el Asistente para la instalación, puede elegir entre Windows Server 2016 y Windows Server 2016 (Servidor con Experiencia de escritorio)

La opción Servidor con Experiencia de escritorio instala la interfaz de usuario estándar y todas las  herramientas, incluidas las características de experiencia de cliente que requieren una  instalación independiente de Windows Server. Los roles y características de servidor se  instalan con Administrador del servidor o con otros métodos:

-  **Instalar, configurar, desinstalar roles de servidor localmente**: con el  Administrador del servidor o con Windows PowerShell.

- **Instalar, configurar, desinstalar roles de servidor remotamente**: con el  Administrador del servidor, RSAT o Windows PowerShell. En la opción Server Core hay una serie de roles, servicios de rol y características que no  se encuentran disponibles. 

 Los distintos elementos instalables, tras haber finalizado la instalación del sistema  operativo, se dividen en dos categorías: 

- **Roles**: Es un programa o el conjunto de una serie de  programas que permiten al equipo servidor realizar una función específica o  entregar un determinado servicio a los usuarios y equipos que pertenecen a la  red. 

- **Características**: Son una serie de programas que no forman  parte de los roles, pero pueden contribuir tanto en la mejora de un servicio de  rol como la funcionalidad del propio servidor como equipo. También existe la  posibilidad de que una característica sea una dependencia o prerrequisito para  la instalación de un rol.

  

## ROLES:

<img src="/img/2ºimagenn.PNG"  />

Los roles de servidor cumplen los siguientes puntos: 

- Describen la función o finalidad principal de un equipo servidor, y un servidor puede desempeñar uno o varios roles. 

- Por cuestiones de rendimiento y aislamiento de servicios, es recomendable que  cada equipo servidor cumpla un solo rol.(Dificil de llevar a cabo en empresas pequeñas) Una alternativa sería la virtualización, que permite en un equipo físico montar  varias máquinas virtuales y a cada una de ellas, instalar un Windows Server 2016 con un rol diferente. 

- Los roles proporcionan acceso a los recursos administrados por otros equipos a  los usuarios. Estos recursos podrían ser sitios web, archivos almacenados o  impresoras. 

- Los roles suelen incluir sus propias bases de datos. Un ejemplo es el rol de Active Directory que contiene una base de datos con nombres y  relaciones jerárquicas de los usuarios y equipos que pertenecen al entorno de  red. 

- Una vez instalado y configurado correctamente un rol, éste comienza a dar  servicio de inmediato y de modo automático.

Los servicios de rol proporcionan o amplían alguna funcionalidad a un rol. Cuando se instala un  determinado rol, se puede escoger entre los diferentes servicios de rol que complementan la funcionalidad. 

- Existen roles con una sola finalidad y, por tanto, no contienen servicio de rol  alguno, como el servidor DNS. 

- El servicio de escritorio remoto que por ejemplo contiene varios servicios que podrán instalarse o no en función de  las necesidades del entorno empresarial

  

### PROCESO DE INSTALACION DE ROLES Y CARACTERISTICAS

<img src="/img/1ºimagenn.PNG"  />

1. En el escritorio de Windows, haga clic en "Administrador del servidor” en la  barra de tareas de Windows. 

2. En el menú superior, haga clic en “Administrar ->  Administrar agregar Roles y  características”. 

3. En la página Antes de comenzar, compruebe que el servidor de destino y el  entorno de red estén preparados para el rol y la característica que desea  instalar y haga clic en Siguiente

4. En la página Seleccionar tipo de instalación, seleccione Instalación basada en  características o en roles para instalar todas las partes de los roles o las  características en un solo servidor, o bien seleccione Instalación de Servicios de  Escritorio remoto para instalar una infraestructura de escritorio basada en  máquina virtual o una infraestructura de escritorio basada en sesión para  Servicios de Escritorio remoto. La primera opción será la utilizada para agregar  el rol en el servidor que se esté configurando. Después, hacer clic en Siguiente. 

5. En la página Seleccionar servidor de destino, seleccione un servidor del grupo  de servidores o un VHD sin conexión. Si se trata del mismo servidor también,  directamente se puede hacer clic en Siguiente. 

6.  Ahora ya se seleccionarán los roles deseados en la página Seleccionar roles del  servidor.

###    ROLES MAS IMPORTANTES

algunos de los roles más importantes para la  configuración de un entorno de red: 

- **Servicios de dominio de Active Directory**: Este rol permite organizar de forma centralizada los diferentes elementos de la  empresa mediante la creación de objetos como usuarios, equipos o grupos de  seguridad. Así mismo, se podrán administrar las políticas de seguridad sobre los usuarios y equipos.

  <img src="/img/4ºimagenn.PNG"  />

- **Servidor DNS:** Este rol proporciona resolución de nombres para las redes TCP/IP. Es más fácil  de administrar cuando está instalado en el mismo servidor que los Servicios de  Dominio de Active Directory. DNS (Sistema de nombres de dominio) permite, de manera jerárquica y distribuida en árbol, establecer nombres a los equipos, servicios o recursos conectados a internet o a una red privada y es capaz de resolver tanto el nombre del dominio a partir de la dirección IP como la dirección IP a partir del nombre de dominio.

  

  <img src="/img/5ºimagenn.PNG"  />

  

- **Servidor DHCP** El servidor de Protocolo de configuración dinámica de host (DHCP) permite  configurar, administrar y proporcionar central y automáticamente direcciones IP y otra configuración de red a los clientes de la red. El protocolo DHCP utiliza tres métodos diferentes para la entrega de  direcciones: 

  - Asignación manual o estática. Asigna una determinada dirección IP a un determinado cliente de la red relacionando la dirección IP con la MAC del cliente. De este modo se  evita que equipos no registrados puedan recibir IP y tener, por tanto, acceso a los diferentes recursos de red. 

  - Asignación automática. Asigna una dirección IP a un cliente de la red y  esa dirección queda asignada a ese cliente hasta que éste la libera.  Cuando el número de clientes del servidor DHCP no varía habitualmente, ésta es una opción recomendable. 

  - Asignación dinámica. El administrador de la red determina un rango de  direcciones a entregar y cada vez que un cliente solicita, se le entrega  una dirección IP. Si el cliente se desconecta de la red, libera la IP automáticamente y cuando se conecta de nuevo recibe otra dirección IP que esté libre en ese momento. 

- **Servicios de archivo y almacenamiento**: Este rol incluye los servicios que se instalan siempre, así como funcionalidad que el usuario puede instalar para ayudar a administrar el almacenamiento y los servidores de archivos. Se consigue así la configuración y administración de uno o varios servidores de archivos que proporcionan ubicaciones centralizadas con un repositorio de ficheros almacenados y compartidos con los clientes de la  red. 

- **Hyper-V Hyper-V**: proporciona servicios que se pueden usar para crear y administrar  máquinas virtuales y sus recursos. 

- **Servidor web (IIS)**: Proporciona una infraestructura de aplicaciones web HTTP, HTTPS o FTP.



## CARACTERISTICAS

Las características son una serie de programas que no forman parte de los roles, pero pueden contribuir tanto en la mejora de un servicio de rol o la funcionalidad del propio  servidor como equipo.

También existe la posibilidad de que una característica sea una dependencia o  prerrequisito para la instalación de un rol.

<img src="/img/6ºimagenn.PNG"  />



## SERVICIOS DE DOMINIO DE ACTIVE DIRECTORY

### ESTRUCTURA LÓGICA DEL DIRECTORIO ACTIVO

Active Directory **permite** a los administradores  **organizar** los elementos de una red (como **usuarios, equipos y dispositivos) en una  estructura jerárquica y lógica.** Tambien almacena información acerca de los  objetos de la red, facilita la búsqueda, facilita el uso de esta información para los  usuarios y los administradores. **Los administradores**  tienen el **control de la seguridad** de los objetos del Active Directory **mediante la  asignación/denegación de permisos** a los distintos recursos

Objetos de Active Directory:

- Recursos compartidos.
- Servidores. 
- Volúmenes.
- Impresoras.
- Cuentas de equipo.
- Usuario de red.

Estructura:

<img src="/img/7ºimagenn.PNG"  />

- **Bosque de Active Directory**: Conjunto de uno o más dominios Active Directory que  comparten estructura lógica, esquema de directorio, configuración de  directorio y un catálogo global.
- **Dominio de Active Directory**: Un dominio es una **partición de un bosque de Active Directory**. La creación de diferentes dominios permite a las organizaciones replicar datos solo en donde  sea necesario. Admite varias funciones relacionadas con la  administración, entre las que se incluyen: 
  - Identidad de usuario en toda la red. 
  - Autenticación. 
  - Relaciones de confianza. 
  - Replicación.
- **Unidades organizativas de Active Directory**: Se utilizan para formar una jerarquía de  contenedores, agrupando objetos con una configuración común, dentro de un  dominio. Se pueden aplicar sobre estas unidades directivas de grupo, Listas de control de acceso  (ACL), delegación de autoridad, etc.

### IMPLEMENTADCION DE ACTIVE DIRECTORY DOMAIN SERVICE

<img src="/img/8ºimagenn.PNG"  />

Active Directory DS administra la estructura de la red de la organización y de las diferentes sedes  relacionadas, así como la gestión de varios bosques. La implementacion consta de tres fases:

- **Fase de diseño**: En esta fase se realizará el diseño de la estructura lógica de Active Directory  DS con el fin de adaptar el servicio a las necesidades de cada una de las  divisiones de la organización.

  Se deberán determinar el número de bosques que requiere la organización, los  dominios que se necesitarán y su diseño, infraestructura del sistema de nombres de  dominio (DNS) y las unidades organizativas para que permitan delegar la  administración (OU)

  Las diferentes fases de diseño de la estructura lógica serían: 

  - *Identificación de los participantes en el proyecto de implementación.* 

  - *Diseño de Bosques.* 

  - *Diseño de dominios y su ubicación en los bosques.* 

  - *Diseño de la infraestructura DNS.* 

  - *Diseño de las unidades organizativas.*

  A continuacion se debera incluir el diseño de la topologia del sitio para la red de la organización. El diseño conlleva los siguientes pasos

  - *Recopilación de la configuración de la red.* 

  - *Planificación de ubicación de los controladores de dominio.* 

  - *Diseño de sitio.* 

  - *Diseño de enlaces a sitios.*

  Tras el diseño de la topologia se procedera al diseño del uso de los controladores de dominio, hemos de tener en cuenta estos aspectos:

  - *Recopilación de información del diseño de topología de sitio.* 

  - *Determinación del número de controladores de dominio.* 

  - *Diseño de sitio.* 

  - *Evaluación de requisitos de hardware en los servidores controladores  de dominio.* 

  - *Supervisión de rendimiento de cada controlador de dominio.*

  Para concluir, se deberá determinar el nivel funcional del bosque y de cada uno de  los dominios, el nivel funcional dotará al entorno de una serie de características  adicionales

- **Fase de implementación**: Se generará un laboratorio donde se procederá a implementar  el diseño propuesto en la fase anterior. Se comenzará con la implementación del nuevo dominio raíz del bosque, continuando  con la estructura del resto de dominios presentes en el diseño. Es posible que, como  parte de la implementación, se necesite actualizar y reestructurar un entorno existente  de Active Directory DS. Este Active Directory DS deberá estar representado en el  laboratorio.

  - *Implementación del dominio raíz del bosque: El dominio raíz del bosque es el pilar fundamental de la infraestructura del  bosque, y es necesario implementarlo en primer lugar. A partir de él, se  desplegará el resto de la infraestructura. Los pasos para seguir para realizar  esta implementación serían las siguientes:*
    - *Revisión del diseño de AD DS que se realizó previamente.*
    - *Configuración de servicio DNS.* 
    - *Crear el dominio raíz del bosque:* 
      - *Implementación de controladores del dominio raíz del bosque*
      -  *Configuración de la topología del sitio para dicho dominio.* 
      - *Configuración de las funciones del maestro de  operaciones.*
    - *Elevar los niveles de las funciones del maestro de operaciones.*
  - *Implementación del resto de dominios: Despues de implementar el dominio raiz se implementaran. el resto de los bosques, árboles y dominios según  el diseño de Active Directory DS. Además, se definirán las relaciones de  confianza según esta establecido en el diseño. Estos son los pasos a seguir:*
    - *Revisión del diseño.* 
    - *Delegación de DNS para el nuevo dominio.* 
    - *Implementación del primer controlador de dominio en el  nuevo dominio.* 
    - *Implementación del resto de controladores de dominio en el  nuevo dominio.* 
    - *Configuración del servidor DNS.* 
    - *Configurar las funciones del maestro de operaciones.*

-  **Fase de operaciones**: Será la encargada del mantenimiento y operatividad  del servicio de Active Directory DS.

  

## BIBLIOGRAFIA y AGRADECIMIENTOS

Esta guía básica no podía haber sido realizada sin la ayuda de este curso:

Curso Básico STIC - Seguridad en Entornos Windows										CCN

Mencionar también la gran ayuda recibida por parte de toda la comunidad de Windows y sus foros .

