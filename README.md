# FUNDAMENTALS WINDOWS SERVER 2016

Bienvenidos a la guía básica, para principiantes, sobre Windows Server 2016 realizada por Ramon Peinado Ruiz gracias al curso ofrecido por CCN.

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

<img src="/img/8ºimagenn.png"  />

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

##  CONTROLADORES DE DOMINIO 

El rol de controlador de dominio (DC) otorga a un servidor las tareas de administración  de los servicios de Active Directory DS. La **función principal** de los controladores de  dominio **es la de autenticar** a los **usuarios**, **conceder, o denegar** , el **acceso a los recursos del dominio** y mantener la base de datos de autenticación de los usuarios.

La autenticación se realiza mediante usuario y contraseña (normalmente). Si la  máquina cliente dispone de elementos biométricos (lector de huellas digitales), se  puede utilizar para la autenticación localmente en la máquina. Una vez que el usuario se ha autenticado contra el controlador de dominio, este recibe  un token de autenticación contra ese dominio para evitar volver a realizar el proceso.

### ROLES ESPECIALES DE LOS CONTROLADORES DE DOMINIO

Los controladores de un dominio tienen otro cometido adicional que es la replicación y  propagación de la estructura Active Directory DS. Si la estructura del Active Directory DS contiene varios árboles y bosques, estos roles cobran mayor importancia. Estos roles son FSMO o Maestros de operaciones:

- **Roles de maestro de operaciones de un bosque**: Solo existe un controlador de dominio en el bosque que tiene ese rol. Existen  dos maestros de operaciones a nivel de bosque: 
  - *Maestro de esquema. Encargado de las modificaciones del esquema del Active Directory DS. Aunque el esquema está replicado en  todos los controladores de dominio, solo el controlador de dominio que  posea este rol podrá escribir modificaciones en el esquema.* 
  - *Maestro de Nomenclatura de Dominios. Garantiza la unicidad de los nombres de los dominios que se agreguen  al bosque*
- **Maestros de operaciones a nivel de dominio**:  Hay un controlador de dominio por cada función en cada uno de los dominios. 
  - *Maestro Controlador Principal de Dominio. Encargado de la  sincronización de la hora en los distintos controladores de dominio que  pertenecen al dominio.*
  - *Maestro de RID. Encargado de que los identificadores de todos  los objetos que hay en el Active Directory DS sean únicos. Para ello, este  rol asigna grupos de identificadores a los distintos controladores de  dominio para que estos los vayan asignando a los objetos que crean.  Cuando el controlador de dominio está cerca a agotar los SID que tiene  asignados, solicita otro rango de SIDs al controlador de dominio con el  rol de Maestro de RID.* 
  - *Maestro de infraestructura. Encargado de la actualización y  comprobación, en entornos de múltiples dominios, la pertenencia a  grupos universales. Actualizará referencias de objetos de su  dominio relacionadas con relaciones hacia otros dominios.* 
  - *Catálogo global. Encargado de mantener la copia completa  de todos los objetos del directorio de su dominio y una copia parcial de  solo lectura de los objetos del resto de dominios que pertenecen al  bosque.*

## ADMINISTRACIÓN DE OBJETOS DEL DIRECTORIO ACTIVO

### CONSOLAS Y METODOS DE ADMINISTRACIÓN

MS Windows Server 2016 tiene cuatro consolas de MMC (**Microsoft Management Console**) diferentes para la  administración de los diferentes parámetros y características del Directorio Activo. 

- **Usuarios y equipos de Active Directory**: Administra los recursos más cotidianos  incluyendo usuarios, grupos y equipos. Es la herramienta mas usada en tareas de administracion de Directorio Activo.

<img src="/img/9ºimagenn.PNG"  />

- **Sitios y servicios de Active Directory**: Administra la replicación de la topología y  servicios del entorno de red.

<img src="/img/10ºimagenn.PNG"  />

- **Dominios y confianzas de Active Directory**: Configura y mantiene las relaciones de confianza entre dominios, además mantiene los niveles funcionales de dominio y de bosque

  <img src="/img/11ºimagenn.PNG"  />

- **Esquema de Active Directory**: Examina y modifica la definición de los diferentes atributos y clases que definen a los objetos del Directorio Activo. Debido a su escasa utilización, esta consola no se instala por defecto en el sistema, como el resto de las consolas.

  <img src="/img/12ºimagenn.PNG"  />

Ademas existe la opción de administrar los diferentes objetos de Active Directory DS a través del Centro Administrativo de Active  Directory. Por medio de esta herramienta, basada en la gestión de tareas, es  posible: 

<img src="/img/13ºimagenn.PNG"  />

- Crear y administrar cuentas de usuarios, equipos y grupos. 
- Crear y administrar Unidades Organizativas. 
- Administrar múltiples dominios con una sola instancia. 
- Buscar y filtrar datos del directorio mediante colas de tareas. 
- Administrar políticas de contraseñas. 
- Recuperar objetos de la papelera de reciclaje del Directorio Activo.

### CUENTAS DE USUARIOS

Todos los usuarios que necesitan acceder a los recursos  compartidos de la red deben estar representados en el Directorio Activo con una  cuenta de usuario.

A través de una cuenta de usuario es posible:

- Permitir o denegar a los usuarios autenticarse en el entorno de dominio. 
- Otorgar acceso a los usuarios a procesos y servicios en un contexto específico  de seguridad.
- Administrar el acceso de usuarios a recursos como pertenecientes al dominio o  bosque, por ejemplo, objetos de Active Directory DS y sus propiedades,  carpetas compartidas, ficheros, directorios o colas de impresión, etc.

Propiedades de los usuarios:

- General. 
- Dirección. 
- Cuenta.
- Perfil.
- Teléfonos.
- Organización: Contiene datos relativos a la organización, puesto,  departamento, etc. 
- Miembro de: Permite la inclusión del usuario en grupos de seguridad que le  otorgan permisos adicionales. 
- Control remoto: Permite activar y configurar la posibilidad de acceso remoto a  la sesión del usuario.

### CUENTAS DE GRUPO

Active Directory DS administra dos tipos de cuentas de grupo:

- Los grupos de distribución. Se utilizan solamente con aplicaciones de correo  electrónico (Microsoft Exchange, por ejemplo) y no pueden recibir permisos. 
- Los grupos de seguridad. Estos grupos disponen de la funcionalidad tanto de  recibir permisos, como de utilización para uso con aplicaciones de correo  electrónico. Debido a esta doble funcionalidad, son los más utilizados. 

Cuando se crea un grupo en Active Directory DS, además de escoger entre estos dos  tipos de grupos, se deberá escoger el ámbito entre estas tres opciones: 

- Dominio Local. Se utiliza para el acceso a los recursos del dominio en el que se  encuentra. 
- Global. Se utiliza para el acceso a los recursos del bosque en el que se  encuentra. 
- Universal. Se utiliza para el acceso a los recursos de todos los dominios de  confianza.

Se recomienda la   de permisos y configuraciones a grupos de seguridad antes que a usuarios  individuales.

### CUENTAS DE EQUIPO

La gestión de las cuentas de los equipos que se van  incorporando al dominio deben ser reubicadas en una estructura de unidades  organizativas (OUs) creada para albergar las cuentas de equipos del dominio.

Existen dos formas de agregar maquinas al dominio: 

- Desde la propia maquina cliente. 

  Haciendo uso de “Panel de control-> Sistema y seguridad -> Sistema” se  puede cambiar la configuración del nombre, dominio y grupo de trabajo. Para agregar una maquina a un dominio desde la propia máquina se necesitará una cuenta del dominio al que se pretende unir con permisos para realizar  dicha acción

- Desde la consola de “Usuarios y equipos de Active Directory” del servidor. 

  Se abrirá la consola de “Usuarios y equipos de Active Directory”, sobre la  Unidad Organizativa (OU) que albergará el nuevo equipo, y mediante el botón  derecho del ratón se seleccionará la opción de nuevo del menú desplegable y  se pulsará sobre la entrada de Equipo (que aparecerá al pasar el ratón sobre la  opción de nuevo).

## POLITICAS DE GRUPO

### GESTION DE LOS SISTEMAS MEDIANTE GPO

Las directivas de grupo son una serie de reglas que controlan los diferentes elementos  de un entorno de dominio a través de los controladores de dominio y el  “Administrador de directivas de grupo”. Las directivas de grupo son una serie de reglas que controlan los diferentes elementos  de un entorno de dominio a través de los controladores de dominio y el  “Administrador de directivas de grupo”.

Las directivas de grupo se utilizan principalmente para restringir aquellas acciones que puedan presentar riesgos potenciales de seguridad.  Algunos ejemplos de directivas de seguridad podrían ser: 

- Bloquear el acceso al administrador de tareas. 
- Restringir el acceso a carpetas con contenido sensible. 
- Deshabilitar la descarga de ficheros ejecutables y de determinadas extensiones.

La consola de “Administración de directivas de grupo” es la que permitirá administrar los diferentes objetos de directivas de grupos.

<img src="/img/14ºimagenn.PNG"  />

Hemos de definir dos conceptos basicos:

- **Directiva de grupo**: Una directiva de grupo es una de las configuraciones individuales que forman parte de un objeto de directiva de grupo.

- **Objeto de directiva de grupo (GPO)**: Un conjunto de políticas de grupo que forman un objeto con una serie de parámetros de seguridad y configuraciones  y que podrá ser vinculado a un usuario, grupo de usuarios o elementos que  pertenecen a una unidad organizativa.

  Los objetos de directivas de grupo y las políticas que los componen pueden ser editados mediante el “Editor de administración de directivas de grupo”.

  <img src="/img/15ºimagenn.PNG"  />

### POLITICAS Y DIRECTIVAS

Las configuraciones de políticas de grupo permiten a los administradores forzar comportamientos y configuraciones modificando estas configuraciones específicas en el registro de las máquinas y usuarios clientes pertenecientes al dominio. Mediante estas configuraciones de seguridad se establecen las directivas o políticas y la agrupación de estas directivas forman las GPOs u Objetos de directiva de grupo.

Las GPOs contienen una o más configuraciones de políticas de grupo que aplican a la configuración del equipo, a la configuración del usuario o a ambos. Las plantillas de GPOs que se generan se almacenan en la carpeta “SYSVOL”

Estos son los tres estados posibles de las politicas de grupo(Existen comportamientos distintos a estos estados):

- **Habilitado**: Cuando una política de grupo se encuentra en estado Habilitado, aplica lo que indica su definición. 
- **Deshabilitado**: Desactiva una característica o deniega el acceso a algún recurso.
- **No configurado**: La política no cambiará nada de la configuración previa existente relacionada con esa configuración específica.(Estado por defecto).

Cada una de las directivas presenta una pestaña denominada “Explicación” que contiene una descripción detallada del comportamiento.

<img src="/img/16ºimagenn.PNG"  />

Al configurar una GPO se almacena el contenido en dos localizaciones:

-  GPC – Contenedor de política de grupo. 
  - Se almacena en la base de datos de Active Directory DS. 
  - Proporciona la información de la versión y relaciona los objetos del directorio con las configuraciones de la plantilla, pero no contiene ninguna configuración.
-  GPT – Plantilla de política de grupo. 
  - Se almacena en el directorio “SYSVOL”. 
  - Proporciona las configuraciones de políticas de grupo.

### OBJETOS EN LA CONSOLA DE DIRECTIVAS DE GRUPO

- Dominio. Las GPOs vinculadas al dominio afectarán a las máquinas de un  dominio específico. 
- Domain controllers. Las GPOs vinculadas a este contenedor afectarán solamente a los controladores de dominio de un dominio específico, este contenedor lo crea el propio Active Directory DS pero, a todo efecto, es una  unidad organizativa y puede vincular GPOs. 
- Unidades organizativas. Las GPOs vinculadas a los diferentes contenedores que  muestra la consola afectarán solo a los elementos que están almacenados en dicho contenedor. Las unidades organizativas definidas y personalizadas por el administrador del dominio aparecerán en la consola de administración de  directivas de grupo. No aparecen users y computers y no se pueden vincular objetos de directiva  de grupo a ninguno de ellos.
- Objetos de directiva de grupo. Este contenedor almacena todas las GPOs creadas, es en esta ubicación donde es posible importar o exportar GPOs. 
- Filtros WMI. Permiten especificar los criterios que deben cumplirse de cara a la aplicación de las directivas de una GPO para, en el caso de querer evitar subdivisiones innecesarias de unidades organizativas, poder evitar que la GPO  le aplique a un tipo de elementos específico. Los filtros WMI se almacenan en el contenedor  y se podrán aplicar a las GPOs. 
- GPO de inicio. Una GPO de inicio es una plantilla que ayuda al administrador a la creación de GPOs. Cuando se crea una nueva GPO, existe la posibilidad de escoger entre las GPOs de inicio y utilizar una de ellas como base, facilitando la  creación de múltiples GPOs con la misma configuración base. 
- Sitios. Este contenedor permite vincular GPOs a los sitios definidos en el dominio y permite enlazar con la herramienta “Sitios y servicios de Active  Directory”. 
- Modelado de directivas de grupo. Es un asistente que va guiando paso a paso en la creación y vinculación de GPOs así como el filtrado de seguridad y la  aplicación de filtros WMI. 
- Resultados de directivas de grupo. Es un asistente mediante el cual se puede averiguar qué directivas están aplicando sobre un elemento en cuestión. Los  resultados de las diferentes consultas se almacenan en este contenedor.



## DIRECTIVAS DE EQUIPO Y DE USUARIO

Para editar una GPO se utiliza el “Editor de administración de directivas de grupo”. Para su ejecución se deberá pulsar el botón derecho del ratón sobre la GPO a modificar y se seleccionará sobre el menú “editar”. Existen dos áreas diferenciadas en el  editor:

- Configuración de usuarios. Se modifica HKEY_CURRENT_USER en el registro de Windows. 
- Configuración de equipos. Se modifica HKEY_LOCAL_MACHINE en el registro de Windows.

Subdivididas en:

- **Directivas**. En este contenedor se almacenan las directivas de seguridad y las  plantillas administrativas que se propagan a los diferentes equipos, a los que  afecta la GPO, y fuerzan cambios en la configuración del registro. Subdivididas a su vez tanto como para equipos como para usuarios

  - *Configuración de Software: Contiene una serie de parámetros relativos a  programas:* 

    *o Despliegue de software a un equipo. Todos los usuarios que hacen uso  del equipo pueden acceder al programa.* 

    *o Despliegue de software a un usuario. Solo el usuario especificado puede  acceder al programa.* 

  - *Configuración de Windows: Contiene configuraciones de scripts y directivas de  seguridad.* 

    *o Nodo de Scripts. Este nodo permite definir dos tipos de Scripts,  Startup/shutdown (en la configuración de equipos) y logon/logoff (En la  configuración de usuarios).* 

    *o Nodo de Configuración de seguridad. Permite a los administradores de  la seguridad en el dominio configurar la seguridad del entorno a través  de GPOs.* 

    *o QoS basada en directiva. Define políticas para la administración del  tráfico de red*

  - *Plantillas administrativas: Contiene cientos de configuraciones de seguridad y  de preferencias del sistema. Existen plantillas específicas para configurar,  mediante GPOs, programas que no necesariamente deben ser de Microsoft.*

- **Preferencias**. Contiene menús de configuración. Así mismo, mientras que las directivas aplicadas a  través de GPOs en un equipo no pueden ser cambiadas por el usuario, las  preferencias sí.

### GESTION DE POLÍTICAS DE SEGURIDAD

Una vez creada una GPO y definidas todas las configuraciones de objetos de dominio,  el siguiente paso consiste en la vinculación de la GPO a un contenedor del directorio  activo. Un vínculo de GPO es la conexión lógica de la política al contenedor en el que  debe aplicar.

Las GPOs pueden ser vinculadas a los siguientes objetos contenedores: 

- Sitios. 
- Dominios.
- Unidades organizativas

GPOs predeterminadas:

- **Default Domain Policy**: Esta GPO está vinculada al dominio y no incluye grupo de seguridad o filtros WMI. Afecta a la seguridad de todos sus equipos y  usuarios. Contiene las directivas de seguridad de contraseñas, el comportamiento para desbloquear la sesión y el protocolo Kerberos. Según las prácticas recomendadas por Microsoft, Esta GPO no debería tener ninguna otra directiva configurada que las que lleva configuradas por defecto.  Lo habitual es que los administradores creen una nueva GPO con las directivas configuradas y vincularla al dominio. 
- **Default Domain Controllers Policy**: Esta GPO está vinculada a la unidad  organizativa “Domain Controllers” y debería afectar, únicamente, a los  controladores de dominio (no se deben añadir objetos a esta unidad organizativa que no sean controladores de dominio). Default Domain  Controllers Policy ha sido diseñada para proporcionar configuraciones sobre auditoría y derechos de los usuarios.

Por defecto, lo normal es que una GPO aplique a todos los objetos del contenedor y los objetos de contenedores de niveles inferiores van heredando las configuraciones de  dicha GPO. A través del filtrado de seguridad, es posible cambiar este comportamiento  y, de este modo, tener la certeza de que las directivas solamente aplican a un grupo  determinado de usuarios de esa unidad organizativa. El filtrado WMI, en cambio, se  define en el contenedor de filtros WMI. Mediante estas consultas WMI podemos  especificar qué excluir o incluir en la GPO. Estos se pueden crear desde la consola de administracion de directivas de grupo.

Existen plantillas administrativas para realizar la administracion de una manera mas centralizada tambien existe la posibilidad de delegar ciertas tareas administrativas a otros usuarios que no  pertenezcan al grupo de administradores del dominio. No solo es posible delegar  control de una determinada unidad organizativa sino, incluso, delegar determinadas  tareas.

Las siguientes tareas relacionadas con políticas de grupo pueden ser delegadas de  manera independiente: 

- Crear GPOs y GPOs de inicio. 
- Editar GPOs.  Administrar los vínculos de GPOs a sitios, dominios y unidades organizativas. 
- Utilizar el modelado de políticas de grupo. 
- Utilizar el analizador de resultados de políticas de grupo. 
- Crear filtros WMI. 

Los siguientes grupos de usuarios tienen acceso completo a la consola de  administración de directivas de grupo (Por defecto): 

- Admins. Del dominio. 
- Administradores de empresa. 
- Creator Owner. 
- Local System.

Orden de aplicacion de las GPOs:

<img src="/img/17ºimagenn.PNG"  />

Se pueden realizar copias importacion y exportacion de estas GPOS:

- Copia de seguridad de GPOs. Se pueden hacer copias de seguridad de las  diferentes GPOs de forma individual. Además, es posible hacer copia de seguridad de todas las configuraciones administradas a través de la consola de administración de directivas de grupo. Para realizar esta acción, hay que  proporcionar al sistema un espacio de almacenamiento (que puede ser local o  una carpeta compartida). Cuando se realiza una copia de seguridad de una GPO, se crea una nueva versión de copia de seguridad, lo que permite llevar un  histórico. 
- Restauración de Copias de seguridad de GPOs. Si se borra o se corrompe una  directiva, es posible recuperar una versión histórica anterior de la GPO. La interfaz de restauración proporciona la posibilidad de ver las diferentes  configuraciones que componen a la GPO antes de realizar la restauración.
- Importación de directivas. Se pueden importar configuraciones de directivas  de grupo desde una GPO a otra. Importar una GPO permite transferir las configuraciones que componen la GPO de copia de seguridad sobre una GPO existente. El proceso de importación no importa los vínculos. La importación  sobrescribe la GPO existente, por lo que todas las configuraciones especificadas  en dicha GPO, que se quieran mantener, deberán ser añadidas manualment  una vez finalizada la importación.
-  Copia de GPOs. Es posible copiar GPOs tanto dentro de un mismo dominio  como entre dominios. Una vez que ha sido copiada y pegada la GPO al  contenedor de “Objetos de directiva de grupo”, será posible renombrar la directiva que, por defecto, ha asumido el nombre “Copia de {Nombre de GPO}”.
-  Tablas de migración. Cuando se copian o importan GPOs, es posible utilizar tablas de migración para modificar referencias que necesitan ser ajustadas para su funcionamiento en el entorno de destino.

Tambien se pueden comprobar estas directivas:

RSoP son una serie de herramientas que permiten evaluar, modelar y resolver  problemas relativos a las configuraciones de políticas de grupo.a. RSoP se utiliza para comprobar la  aplicación de las diferentes directivas que actúan sobre el objeto, teniendo en cuenta  las excepciones como herencias, aplicaciones forzadas, filtros WMI, etc.

## BIBLIOGRAFIA y AGRADECIMIENTOS

Esta guía básica no podía haber sido realizada sin la ayuda de este curso:

Curso Básico STIC - Seguridad en Entornos Windows										CCN

Mencionar también la gran ayuda recibida por parte de toda la comunidad de Windows y sus foros .

