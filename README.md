### Escuela Colombiana de Ingeniería
### Arquitecturas de Software - ARSW

## Escalamiento en Azure con Maquinas Virtuales, Sacale Sets y Service Plans

### Dependencias
* Cree una cuenta gratuita dentro de Azure. Para hacerlo puede guiarse de esta [documentación](https://azure.microsoft.com/es-es/free/students/). Al hacerlo usted contará con $100 USD para gastar durante 12 meses.
Antes de iniciar con el laboratorio, revise la siguiente documentación sobre las [Azure Functions](https://www.c-sharpcorner.com/article/an-overview-of-azure-functions/)

### Parte 0 - Entendiendo el escenario de calidad

Adjunto a este laboratorio usted podrá encontrar una aplicación totalmente desarrollada que tiene como objetivo calcular el enésimo valor de la secuencia de Fibonnaci.

**Escalabilidad**
Cuando un conjunto de usuarios consulta un enésimo número (superior a 1000000) de la secuencia de Fibonacci de forma concurrente y el sistema se encuentra bajo condiciones normales de operación, todas las peticiones deben ser respondidas y el consumo de CPU del sistema no puede superar el 70%.

### Escalabilidad Serverless (Functions)

1. Cree una Function App tal cual como se muestra en las  imagenes.

![](images/part3/part3-function-config.png)

![](images/part3/part3-function-configii.png)

## Creación
![image](https://user-images.githubusercontent.com/90571387/201090948-dcdc1291-026a-40ed-8109-95c5a1110c41.png)


2. Instale la extensión de **Azure Functions** para Visual Studio Code.

![](images/part3/part3-install-extension.png)

## Instalación
![image](https://user-images.githubusercontent.com/90571387/201091619-9f972994-5533-4b3b-b1b5-2b0d4ba4c176.png)


3. Despliegue la Function de Fibonacci a Azure usando Visual Studio Code. La primera vez que lo haga se le va a pedir autenticarse, siga las instrucciones.

![](images/part3/part3-deploy-function-1.png)

![](images/part3/part3-deploy-function-2.png)

## Despliegue
![image](https://user-images.githubusercontent.com/90571387/201094618-2773a45d-4933-4593-aaff-e6101dbd6889.png)


4. Dirijase al portal de Azure y pruebe la function.

![](images/part3/part3-test-function.png)

## Función en Azure
![image](https://user-images.githubusercontent.com/90571387/201095068-2d536a39-ee9f-46ae-b197-336805c87af6.png)
## Probando 
![image](https://user-images.githubusercontent.com/90571387/201769642-cd3d37a7-96c7-42f2-94b7-db85f3202a0e.png)



5. Modifique la coleción de POSTMAN con NEWMAN de tal forma que pueda enviar 10 peticiones concurrentes. Verifique los resultados y presente un informe.

## Colección en Postman
  ![image](https://user-images.githubusercontent.com/90571387/201775637-8985fac9-c5bc-4138-b218-ae888edfc745.png)
 
## Ejecución
  ![image](https://user-images.githubusercontent.com/90571387/201778795-b01f4986-4485-454a-94bc-65745da83573.png)
  ![image](https://user-images.githubusercontent.com/90571387/201778827-1478188d-6a81-4c85-98ca-3be027ce674f.png)


6. Cree una nueva Function que resuleva el problema de Fibonacci pero esta vez utilice un enfoque recursivo con memoization. Pruebe la función varias veces, después no haga nada por al menos 5 minutos. Pruebe la función de nuevo con los valores anteriores. ¿Cuál es el comportamiento?.

## Codigo Modificado
  ![image](https://user-images.githubusercontent.com/90571387/201783526-df7bed9b-ce30-4459-bb66-7b17a2c51bc5.png)

**Preguntas**

* ¿Qué es un Azure Function?
    > Azure Functions es un servicio en la nube disponible bajo demanda que proporciona toda la infraestructura y los recursos
    > continuamente actualizados necesarios para ejecutar sus aplicaciones.
    > Puede utilizar Functions para crear API web, responder a cambios en la base de datos, procesar flujos de IoT, gestionar
    > colas de mensajes y mucho más.
    >
    >Azure Function nos presenta una multitud de nuevos triggers para poder ejecutarlo. Entre todos estos triggers podemos 
    >encontrar: Cosmos DB, Event Hub y WebHooks.
* ¿Qué es serverless?
    > La computación sin servidor (o serverless para abreviar) es un modelo de ejecución en el que el proveedor en la nube (AWS, Azure o Google Cloud) es responsable     de ejecutar un fragmento de código mediante la asignación
    > dinámica de los recursos. Y cobrando solo por la cantidad de recursos utilizados para ejecutar el código. El código, generalmente, se ejecuta dentro de contenedores sin estado que pueden ser activados por una variedad de 
    > eventos que incluyen solicitudes HTTP, eventos de base de datos, servicios de colas, alertas de monitoreo, carga de archivos, eventos programados (trabajos cron), etc.
* ¿Qué es el runtime y que implica seleccionarlo al momento de crear el Function App?
    > Un runtime environment carga todas las aplicaciones de un programa 
    > y las ejecuta en una plataforma, en Azure se tiene disponibilidad
    > de .NET, Nodejs, Pyhton y Java. Las implicaciones que esto trae
    > es que dependiendo el plan y la version de runtime se vera afectado
    > el tiempo de timeout y el intervalo de limpieza de el cache en
    > memoria
* ¿Por qué es necesario crear un Storage Account de la mano de un Function App?
    > Azure Storage contiene todos los objetos de datos de Azure Storage: blobs, archivos, colas, tablas y discos. 
    > La cuenta de almacenamiento proporciona un espacio de nombres único para sus datos de Azure Storage al que se puede acceder 
    > desde cualquier lugar del mundo a través de HTTP o HTTPS.
* ¿Cuáles son los tipos de planes para un Function App?, ¿En qué se diferencias?, mencione ventajas y desventajas de cada uno de ellos.
  > **Consumption:** El plan de consumo de Azure Functions se factura en
    > función del consumo de recursos y las ejecuciones por segundo. El
    > precio del plan de consumo incluye una concesión mensual gratuita
    > de 1 millón de solicitudes y 400.000 GB-s de consumo de recursos
    > por mes y por suscripción en el precio de pago por uso en todas
    > las aplicaciones de funciones de esa suscripción. El plan Azure
    > Functions Premium ofrece un rendimiento mejorado y se factura
    > por segundo en función del número de vCPU-s y GB-s que 
    > consuman sus funciones Premium.

    > **Premium plan:** El plan Azure Functions Premium ofrece las 
    > mismas funciones y el mismo mecanismo de escalado utilizado en el
    > plan de consumo (basado en el número de eventos) sin arranque en
    > frío, con un rendimiento mejorado y acceso a VNET. El plan Azure
    > Functions Premium se factura en función de la vCPU y la memoria 
    > que consumen sus funciones.
* ¿Por qué la memoization falla o no funciona de forma correcta?
    > La lista creada en el código no tiene la suficiente capacidad para almacenar datos de gran tamaño
* ¿Cómo funciona el sistema de facturación de las Function App?
    > Se factura en función del consumo de recursos y las ejecuciones 
    > por segundo.
* Informe

## Ejecución Memorización
  * Como podemos ver, el tiempo de duración se redujo a la mitad aproximadamente
  ![image](https://user-images.githubusercontent.com/90571387/201784459-20d7d33a-6b66-4089-bc1d-a151f6d7347e.png)
  * CPU
  ![image](https://user-images.githubusercontent.com/90571387/201784611-ab04a588-a9c2-4663-9c86-c2d4b15339d8.png)
  ![image](https://user-images.githubusercontent.com/90571387/201784706-3b0d85cc-5e58-4dbc-896a-89818f87169c.png)



