Adamo add-on
==========

![Adamo Logo](./01.png)


**Contenido**

  - [1. Configuración del módulo](addons_modules/adamo/adamo.md#configuración-del-módulo1)
    - [1.1 Preparación de los datos](addons_modules/adamo/adamo.md#preparación-de-los-datos)
    - [1.2 Obtención del Api-Key de Adamo](addons_modules/adamo/adamo.md#obtención-del-api-key-de-adamo)
    - [1.3 Configuración del módulo](addons_modules/adamo/adamo.md#configuración-del-módulo2)
    - [1.4 Carga de Servicios](addons_modules/adamo/adamo.md#carga-de-servicios)
  - [2. Gestión de UUIS](addons_modules/adamo/adamo.md#gestión-de-uuis)
    - [2.1 Añadir UUIS](addons_modules/adamo/adamo.md#añadir-uuis)
    - [2.2 Actualizar UUIS](addons_modules/adamo/adamo.md#actualizar-uuis)
  - [3. Gestión de pedidos](addons_modules/adamo/adamo.md#gestión-de-pedidos)
    - [3.1 Listado de Pedidos](addons_modules/adamo/adamo.md#listado-de-pedidos)
    - [3.2 Alta de pedidos](addons_modules/adamo/adamo.md#alta-de-pedidos)
    - [3.3 Modificación de pedidos](addons_modules/adamo/adamo.md#modificación-de-pedidos)
    - [3.4 Cancelación/Baja de pedidos](addons_modules/adamo/adamo.md#cancelaciónbaja-de-pedidos)
    - [3.5 Provisión de pedidos](addons_modules/adamo/adamo.md#provisión-de-pedidos)
    - [3.6 Obtención de FSAN](addons_modules/adamo/adamo.md#obtención-de-fsan)
    - [3.7 Cambio de FSAN](addons_modules/adamo/adamo.md#cambio-de-fsan)
    - [3.8 Envio de incidencias](addons_modules/adamo/adamo.md#envio-de-incidencias)
    - [3.9 Citar un pedido](addons_modules/adamo/adamo.md#citar-un-pedido)
    - [3.10 Check ONT](addons_modules/adamo/adamo.md#check-ont)
    - [3.11 Refrescar pedidos](addons_modules/adamo/adamo.md#refrescar-pedidos)

<a id="configuración-del-módulo1"></a>
<br>
## 1. Configuración del módulo

<a id="preparación-de-los-datos"></a>
<br>
### 1.1 Preparación de los datos
Para el correcto funcionamiento del módulo hace falta disponer de la API-Key de Adamo, en el siguiente paso se describe cómo obtenerlo, y un acceso al correo electrónico que se facilitó a Adamo, el mismo con el que hacen login en el portal de Wholesale de Adamo, para el envío del correo necesario en caso de generar una incidencia. La contraseña se encriptará y no se utilizará para otra cosa que no sea el envío de correos a Adamo.

<a id="obtención-del-api-key-de-adamo"></a>
<br>
### 1.2 Obtención del Api-Key de Adamo
Para la obtención del Api-Key vamos a necesitar un terminal con la funcionalidad curl instalada y las credenciales para el acceso a la plataforma Wholesale. Cuando tengamos estos datos, vamos al terminal del equipo e introducimos el siguiente comando:
```sh
curl --header "Content-Type: application/json" \
     --request POST \
     --data '{"email":"xyz","password":"xyz"}' \
https://wholesale.adamo.es/api/v1/api-key
````

Se sustituirá xyz tanto en email y en la password con los datos de acceso al portal y dará una
respuesta como esta:
```sh
{
    "key":"12345abcdef12345abcdef345f60123458312345e12345abcdef45bf12345abcdef45c123456192812345e912345abcdef5731234541412345abcdefabcdef6c4",
    "role":"operator",
    "organization":"yy",
    "id":"xxx",
    "email":"xyz",
    "self_installer":z
}
````

Nos quedaremos con la key para la configuración del módulo.

<a id="configuración-del-módulo2"></a>
<br>
### 1.3 Configuración del módulo
Accederemos a **Configuración > Integraciones > Lista de módulos > splynx_adamo_addon** y rellenaremos los siguientes campos:

![Api Key configuration](./02.png)

Aquí pegamos la key que obtuvimos en el paso anterior.

![SFTP configuration](./03.png)

Completamos los datos de FTP de Adamo (IP, puerto, usuario y contraseña), en el caso de que se quiera hacer uso del botón de importación de UIs automático desde el FTP.

<a id="carga-de-servicios"></a>
<br>
### 1.4 Carga de Servicios
Para que el addon funcione, es fundamental cargar los servicios antes del primero uso. Además, en el caso de contratar un nuevo servicio con Adamo, será necesario repetir esta operación de forma manual.
Para ello, hay que acceder a Configuración > Integraciones > Adamo Services y hacer click en el botón Actualizar servicios que se muestra
a continuación:

![Carga de servicios](./33.png)

<a id="gestión-de-uuis"></a>
<br>
## 2. Gestión de UUIS

<a id="añadir-uuis"></a>
<br>
### 2.1 Añadir UUIS
Para añadir UUIS al sistema para poder realizar las altas hay que ir a Configuración > Integraciones > Adamo UIs en la que veremos en la parte superior el texto “Importar UIs” haremos click en él para que se despliegue el menú para la subida del csv. Adicionalmente, existe la posibilidad de cargar directamente desde el FTP de Adamo (siempre que se hayan configurado los datos de acceso al mismo como se puede ver en la figura anterior).

![Upload UIs](./04.png)

Los formatos soportados para la subida de unidades inmobiliarias son los formatos en los que Adamo los exporta, teniendo estas dos opciones: Formato de huella y formato de API California.

![UIs header](./05.png)

Cualquier subida con otro formato puede dar un error de de base de datos.

Una vez importado el fichero nos saldrá en la tabla inferior las UUIS ya importadas, pudiendo utilizar el buscador para encontrar una en específico.

![UIs](./07.png)

<a id="actualizar-uuis"></a>
<br>
### 2.2 Actualizar UUIS
Para actualizar una UUI o añadir otra, hay que volver a subir un fichero con el formato especificado en el punto anterior, si se vuelve a subir un fichero con UUIS solo se actualizan las que con el mismo id tengan valor distinto y se insertarán las que no estén previamente. Por lo tanto se puede subir el fichero entero de todas las UUIS sin temor a que se dupliquen.

<a id="gestión-de-pedidos"></a>
<br>
## 3. Gestión de pedidos

<a id="listado-de-pedidos"></a>
<br>
### 3.1 Listado de Pedidos
Para ver los pedidos existentes se debe acceder a la siguiente ruta desde el dashboard principal: **Clientes > Pedidos Adamo** .
Una vez en esta página se puede visualizar una tabla mostrando los pedidos del cliente tal como se
observa en la figura.

![Listado de pedidos](./08.png)

Dicha tabla incluye una fila por cada pedido de cliente y se compone de las las siguientes columnas:

- **ID**: El identificador único del cliente.
- **Cliente**: El nombre del cliente.
- **Pedido**: El identificador único del pedido.
- **Calle**: La dirección del pedido.
- **Estado**: El estado actual del pedido.

En la parte superior de la vista hay dos campos:
- **Mostrar**:
Permitiendo elegir el número de filas de la tabla de pedidos a mostrar entre las siguientes opciones: 10, 25, 50, 100, 200.

- **Buscar**:
Permitiendo filtrar las filas previamente mencionadas (ID, Cliente, Pedido, Calle, Estado) de la tabla por un valor cualquiera que incluyan.
En la parte inferior de la página también se puede elegir la siguiente vista de registro según la configuración del campo mostrar mencionado anteriormente.

<a id="alta-de-pedidos"></a>
<br>
### 3.2 Alta de pedidos
Para realizar un pedido de alta de usuario, primero se debe elegir el cliente desde la ruta **Clientes->Lista** y pulsando en el el campo “Nombre” del cliente, tal como muestra la figura a continuación.

![Listado de clientes con pedidos activos](./09.png)

Una vez abierta la vista del cliente elegido, se debe navegar hasta la pestaña “Adamo” y pulsar en el campo **“Alta de Usuario De Usuario En Adamo”** en la parte superior de esta pestaña. Tal como muestra:

![Proceso de alta](./10.png)

Una vez pulsado el campo se accede al formulario de alta de usuario en el que se cumplimentan los siguientes campos:

- **Nombre**: Nombre del Usuario objeto del pedido de Alta.
- **Teléfono**: Teléfono del Usuario objeto del pedido de Alta.
- **Calle**: Dirección del Usuario objeto del pedido de Alta.
- **ID Calamares**: Identificador de la UUI en el sistema de Adamo
- **Servicio**: Servicio objeto del pedido de Alta.
Dicho servicio debe elegirse entre el listado de servicios disponibles mostrado.

Tal como muestra la Figura a continuación

![Campos de alta](./11.png)

![Campos de alta 2](./32.png)

Una vez solicitado el alta se puede comprobar el estado de su tramitación de alta en la tabla mostrando el resumen de pedidos realizados.
Tal como muestra la Figura a continuación

![Alta de pedido](./12.png)

Pudiendo ser dichos estados:
- **Ordered**: Pedido solicitado a falta de verificación por parte de Adamo de por serviciar en esa UUI.
- **Verified**: Pedido verificado con Adamo que se puede serviciar.
- **Planned**: Se ha cerrado una cita con el cliente para la instalación.
- **Issue**: Pedido con una incidencia de falta de recursos.
- **Canceled**: Pedido cancelado, si no se llega a completar.
- **Disconnect**: Pedido de baja de cliente, una vez el pedido ha estado en Completed.
Completed: Pedido completado.

<a id="modificación-de-pedidos"></a>
<br>
### 3.3 Modificación de pedidos
Solamente se pueden realizar pedidos de modificación para los pedidos que se encuentren en el estado **Completed**.
Para modificar un pedido dependiendo de su estado se debe pulsar el icono ![Cambiar servicio](./17.png) en la columna Acciones del listado de pedidos del cliente seleccionado mostrado a continuación.

![Alta de pedido](./13.png)

Una vez pulsado dicho icono se muestra un desplegable reflejando los tipos de servicio objetivo hacia los que se puede solicitar la modificación.
Tal como muestra a continuación.

![Servicio](./18.png)

Una vez realizado el pedido de modificación se muestra el pedido actualizado en el listado de pedidos del cliente.

<a id="cancelaciónbaja-de-pedidos"></a>
<br>
### 3.4 Cancelación/Baja de pedidos
La solicitud de baja de los pedidos que no han llegado a estar en Completed se denomina Canceled, y de los que sí han estado en Completed es Disconnected. Un pedido está en Completed una vez ha provisionado una ONT en esa orden. Para modificar un pedido dependiendo de su estado se debe pulsar el icono ![Cancel/Disconnect button](./16.png) en la columna Acciones del listado de pedidos del cliente seleccionado mostrado en la figura a continuación.

![Baja de un pedido](./14.png)

Una vez pulsado dicho icono se muestra un desplegable reflejando los campos de servicio objeto del pedido de Baja. Para proseguir con el pedido de baja se debe pulsar el botón **“Confirmar Cancelación/Baja”**.

![Confirmación de baja](./15.png)

Una vez realizado el pedido de baja se muestra un nuevo pedido en el listado de pedidos del cliente.

<a id="provisión-de-pedidos"></a>
<br>
### 3.5 Provisión de pedidos
Para provisionar un pedido existe un botón como el que se muestra en la siguiente figura.

![Provision](./19.png)

Al hacer click sobre el icon de provisión, saldrá un modal con un formulario con los datos necesarios para realizar la acción.

![Datos de Provision](./20.png)

<a id="obtención-de-fsan"></a>
<br>
### 3.6 Obtención de FSAN
Para obtener el FSAN asociado a un pedido, hay que hacer click en el icono que se muestra a continuación:

![Obtencion de FSAN](./21.png)

El proceso obtendrá el FSAN desde Adamo y lo guardará en la instancia. El FSAN se podrá consultar en la pestaña de datos de usuario, en el campo adicional denominado Numero de Serie.

<a id="cambio-de-fsan"></a>
<br>
### 3.7 Cambio de FSAN
Para cambiar el FSAN asociado a un pedido, hay que hacer click en el icono que se muestra a continuación:

![Cambio de FSAN](./22.png)

Se mostrará un formulario con un campo para el nuevo numero de serie.

![Modal de Cambio de FSAN](./23.png)

<a id="envio-de-incidencias"></a>
<br>
### 3.8 Envio de incidencias
Para el envío de incidencias sobre un pedido, es necesario realizar dos acciones.
La primera consiste en poner el estado en estado issue. Para ello, hay que hacer click en el icono que se muestra a continuación:

![Incidencia](./24.png)

Se mostrará un formulario en el que es necesario marcar el tipo de incidencia.

![Modal de Incidencia](./25.png)

Una vez se envía, el estado estará cambiado a issue.

![Pedido Issue](./26.png)

Es momento de pasar al segundo paso:

![Portal Jira de Adamo](./27.png)

Se abrirá en el navegador el portal de gestión en el que habrá que continuar el proceso.

<a id="citar-un-pedido"></a>
<br>
### 3.9 Citar un pedido
Para establecer una fecha de instalación del cliente, hay que hacer click en el siguiente icono

![Cita](./28.png)

Se abrirá un modal en el que se podrá escoger una fecha

![Modal de Cita](./29.png)

<a id="check-ont"></a>
<br>
### 3.10 Check ONT
Para hacer un check ONT (check del estado de la ONT asociada a ul pedido), hay que hacer click en el siguiente icono:

![Check ONT](./30.png)

<a id="refrescar-pedidos"></a>
<br>
### 3.11 Refrescar pedidos
Los pedidos son actualizados automáticamente cada 15 minutos, pero existe la posibilidad de actualizarlos al instante de forma manual. Para ello hay que hacer click en el icono que se muestra a continuación:

![Reload de pedido](./31.png)
