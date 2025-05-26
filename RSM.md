## Patron de Diseño RSM (Routing - Scheme - Manager)

### Historia
El patrón RSM (Routing - Scheme - Manager / Enrutamiento - Esquema - Gestor), es una nueva forma de estructurar la logica de un proyecto de software sea Web o Escritorio en el cual busca implementar aplicaciones software en en base a su funcionamiento y aumentar la seguridad y claridad de los mismos.​

En **RSM** se plantea que el codigo sea totalmente propio para evitar contaminacion externa de la aplicacion y con ello vulnerar la aplicacion o la infraestructura del negocio.

Por ello el patron de diseño cuenta con 3 tipos segun sus complementos, Propios **(a)**, De Terceros **(b)** y Mixto **(c)**.

Existe la posibilidad de reducir el Patron **RSM** y este se puede representar de 2 formas:
**RSM r1** : Variante que utiliza varios archivos los cuales cada uno cumple la funcion de un componente de **RSM**, pensado para Aplicaciones modulares y expandibles.

**RSM r2** : Variante que utiliza un unico archivo que cumple con todas las funciones de los componentes de **RSM**, pensado para Aplicaciones estaticas.

**RSM** fue desarrollado por Percy Alexander Caballero Lucano durante la inspeccion de un sistema en el cual la logica presentada era confusa y desordenada, para lo cual se procuro separar y jerarquizar la logica de la interfaz limitando el acceso a los recursos de la aplicacion solo a las clases de la misma aumentando la seguridad ya que solo existe una ruta de acceso al mismo. 

### Descripcion
Los componentes de RSM se definen a continuacion:

#### Routing (R)
Responde a eventos solicitados por el Usuario e invoca la peticiones a Scheme el cual se encarga de la presentacion y Scheme solicita los datos e informacion necesarias para ello a Manager, Routing es el encargado de recibir las acciones y enrutarla segun corresponda.

#### Scheme (S)
Presenta la información y lógica de negocio en un formato adecuado para interactuar o ser consumida, por tanto requiere de la información que debe representar como salida la cual es proporcionada por Manager.

#### Manager (M)
Gestiona la logica de negocio asi como el accesos a la información, tanto consultas como actualizaciones, implementando también los privilegios de acceso que se hayan descrito en las especificaciones de la aplicación, puede solicitar informacion general o especial a Auxiliary o Broker para complementar sus funciones.

#### Opcional
La Logica de la Aplicacion puede ser mejorarda agregando una de estas estructuras logicas, pudiendo existir 3 variantes del Patron **RSM** :
Auxiliary **(a)** : Solo se utiliza logica propias del desarrollador.
Broker **(b)** : Solo se utiliza logica proveidas por terceros
Mixta **(c)** : Combinando logica propias y de terceros.

### Interacción de los componentes
- El usuario interactúa con la interfaz de usuario (Ejm. index.php).
- Routing recibe la acción solicitada por el usuario y gestiona el evento que llega.
- Routing accede a Scheme y obtiene la actualización de la informacion y presentandolo al usuario.
- Scheme solicita a Manager la informacion necesaria para generar la presentacion o interfaz y pasarla a Routing.
- Manager se encarga de la logica y el acceso a la informacion del negocio y pasando los resultados a Scheme.
- Manager se puede comunicar con Auxiliary o Broker para consumir datos complementarios o generales para el funcionamiento de la logica de negocio.
- Auxiliary se encarga de manejar la logica general necesaria para el funcionamiento de Manager asi como funciones especiales que se han de reutilizar en otros proyectos (Login. Registros, Manejo de Archivos, etc)
- Broker se encarga de manejar logica necesaria para el funcionamiento de Manager y los cuales no son propiedad de la desarrolladora y son: software, codigo o servicios externos que el sistema o aplicativo consume.
- Despues de la entrega de la informacion la interfaz espera nuevas interacciones del usuario y comenzando el ciclo nuevamente.

### Gestion de datos
La gestion de los datos es manejada por **Manager** o **Auxiliary** los cuales son las unicas clases con la posibilidad de acceder a la base de datos
La unión entre capa de presentación y capa de negocio conocido en el paradigma de la Programación por capas representaría la integración entre el Enrutador (Routing) de eventos, la Interfaz (Scheme) y el Acceso a Datos (Manager).

### Seguridad
La gestion de la seguridad se base en acceso cero a las Clases o Modulos de forma directa por parte del usuario la unica forma de acceder a los datos es por medio de Routing filtrando y redireccionando todo evento no autorizado a una clase especializada en seguridad.
