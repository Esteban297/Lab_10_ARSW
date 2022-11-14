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

**Preguntas**

* ¿Qué es un Azure Function?
* ¿Qué es serverless?
* ¿Qué es el runtime y que implica seleccionarlo al momento de crear el Function App?
* ¿Por qué es necesario crear un Storage Account de la mano de un Function App?
* ¿Cuáles son los tipos de planes para un Function App?, ¿En qué se diferencias?, mencione ventajas y desventajas de cada uno de ellos.
* ¿Por qué la memoization falla o no funciona de forma correcta?
* ¿Cómo funciona el sistema de facturación de las Function App?
* Informe
