# 📄 Requerimientos del Sistema

## 1. Lista general de requerimientos

El sistema de TechCup tiene los siguientes requerimientos (descripción a alto nivel):

### 1.1 Requerimientos funcionales

El sistema de TechCup debe tener la capacidad de:

1. La aplicacion TechCup debe permitir tener un sistema de pagos integrado
2. La aplicacion TechCup debe permitir registrar un torneo a los organizadores
3. La aplicacion TechCup debe tener un sistema de registro de la forma usuario - contraseña
4. La aplicacion TechCup debe mostrar la informacion de los torneos registrados a los organizadores
5. La aplicacion TechCup debe permitir que los organizadores puedan modificar el estado de los torneos
6. La aplicacion TechCup debe permitir registrar un equipo a un torneo a los capitanes de cada equipo

### 1.2 Requerimientos no funcionales

El sistema de TechCup debe tener:

1. La aplicacion TechCup debe tener los colores institucionales de la escuela
2. La aplicacion TechCup debe generar un ID unico para cada torneo que consista de 5 digitos con el año y semestre vigentes en este orden, sin espacios y sin simbolos especiales, por ejemplo 20262
3. La aplicacion TechCup debe tener un texto con la frase "Pago realizado" como elemento visual que al momento de consultar los equipos en un torneo indique aquellos que ya realizaron el pago para el torneo
4. La aplicacion TechCup debe generar el reporte de pago realizado por cada equipo en formato JSON
5. La aplicacion TechCup debe tener una interfaz grafica de tipo tabla que presente los participantes de un torneo
6. La aplicacion TechCup debe tener para cada torneo solamente 3 posibles estados "En progreso", "Cerrado" o "Cancelado"
7. La aplicacion TechCup debe permitir realizar pagos por PSE

## 2. Diagramas de caso de uso

### 2.1 Requerimiento Funcional 1

| Campo | Descripción |
|------|-------------|
| **ID** | RF-01 |
| **Nombre del requerimiento** | La aplicacion TechCup debe permitir tener un sistema de pagos integrado |
| **Descripción** | *El sistema debe por cada equipo que se registre a un torneo, debe permitir a los capitanes de cada equipo pagar la tarifa del torneo impuesta por los organizadores, donde el pago realizado genere un reporte del pago con toda la informacion asociada al pago en formato JSON dirigiendose hacia la oficina del decano* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, TechCup debe tener previamente un sistema de acceso de la forma usuario - contraseña, debe tener integrado un sistema de registro de torneos, debe tener integrada una interfaz grafica que permita realizar un pago, se debe permitir pagos por PSE, debe permitir registrar equipos a torneos, el actor Capitan tuvo que haber inscrito su equipo al torneo previamente al pago* |
| **Actor** | *Capitan* |
| **Flujo principal** | 1. El actor Capitan ingresa con su usuario y contraseña en la plataforma<br>2. El sistema verifica sus credenciales y lo habilita para acceder a la cuenta<br>3. El sistema muestra el menu principal de la aplicacion<br>4. El actor Capitan ingresa al torneo que quiere pagar la tarifa<br>5. El sistema muestra la pagina principal del torneo dentro de la aplicacion<br>6. El actor Capitan le da al boton pagar inscripcion<br>7. El sistema muestra el menu de pagos y muestra las opciones disponibles que en este caso solamente esta por PSE<br>8. El actor Capitan da al boton "pagar por PSE"<br>9. El sistema redirecciona al actor hacia una ventana segura de pagos donde pueda ingresar sus datos<br>10. El sistema debe detectar de forma automatica si el pago fue realizado o no<br>11. El sistema regresa al menu principal |
| **Diagrama de caso de uso** | ![Caso1](docs/uml/CasoDeUso1.png) |
| **Poscondiciones** | *Se espera como resultado dentro de la informacion del torneo el equipo quede registrado como "Pago realizado", debe generar un informe de la transaccion en formato JSON y debe ser enviada a la oficina de decanatura* |


### 2.2 Requerimiento Funcional 2

| Campo | Descripción |
|------|-------------|
| **ID** | RF-02 |
| **Nombre del requerimiento** | La aplicacion TechCup debe permitir registrar un torneo a los organizadores |
| **Descripción** | *El sistema debe permitir a los organizadores poder registrar un torneo, dandole un nombre, fecha y tarifa al torneo* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, TechCup debe tener previamente tener un sistema de acceso de la forma usuario - contraseña, debe existir un elemento previamente creado que permite acceder al menu de crear nuevo torneo a los Organizadores, debe existir un formato menu previamente construido para el registro de torneos* |
| **Actor** | *Organizador* |
| **Flujo principal** | 1. El actor Organizador ingresa con su usuario y contraseña en la plataformaEl sistema verifica sus credenciales y lo habilita para acceder a la cuenta<br>3. El sistema muestra el menu principal de la aplicacion<br>4. El actor Organizador se dirigue a la seccion de crear un torneo<br>5. El sistema muestra el menu de creacion de un nuevo torneo, donde se solicitara un nombre del torneo, la fecha de realizacion, la tarifa de ingreso y una descripcion asociada al torneo<br>6. El actor Organizador da click sobre los recuadros que solicitan la informacion<br>7. El sistema responde permitiendole escribir al organizador<br>8. El actor Organizador da click en registrar torneo<br>9. El sistema registra internamente el torneo en el sistema<br>10. El sistema muestra al usuario un mensaje que verifica la creacion del torneo de forma satisfactoria<br>11. El sistema regresa al menu principal |
| **Diagrama de caso de uso** | ![Caso2](docs/uml/CasoDeUso2.png) |
| **Poscondiciones** | *Se espera como resultado el torneo se vera reflejado en el sistema, se encuentre de forma automatica en estado "En progreso", se genere un ID unico que identifique al torneo de la forma año y semestre vigente al momento de la creacion del torneo* |

### 2.3 Requerimiento Funcional 3

| Campo | Descripción |
|------|-------------|
| **ID** | RF-03 |
| **Nombre del requerimiento** | La aplicacion TechCup debe tener un sistema de registro de la forma usuario - contraseña |
| **Descripción** | *El sistema debe poder darle acceso a los usuario que estan registrados en el sistema, de lo contrario se les negara el acceso, de igual forma, se debe permitir poder registrarse en el sistema* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, TechCup debe tener previamente un sistema de alojamiento de datos donde se encuentren todos los usuarios ya registrados, se debe tener un sistema que permita modificar esta lista y agregar o quitar usuarios, se debe tener la interfaz grafica del menu, el menu de nuevo usuario y el menu principal de la aplicacion* |
| **Actor** | *Estudiantes* |
| **Flujo principal** | 1. El actor Estudiante ingresa en la aplicacion e ingresa sus credenciales<br>2. El sistema debe reconocer si estas credenciales son validas, en caso de que no lo sean sera rechazado en ingreso<br>3. El actor Estudiante ingresa en el boton de nuevo usuario<br>5. El sistema muestra al usuario el menu de registro de nuevo usuario con las opciones de darse un nombre de usuario y una contraseña<br>6. El actor da en las casillas permitadas para escribir<br>7. El sistema debe permitir escribir al usuario dentro de estas casillas<br>8. El actor da al boton registrar usuario<br>9. El sistema debe registrar al nuevo usuario<br>10. El sistema debe darle acceso al usuario<br>11. El sistema muestra el menu principal al usuario con su cuenta ingresada |
| **Diagrama de caso de uso** | ![Caso3](docs/uml/CasoDeUso3.png) |
| **Poscondiciones** | *Se espera como resultado el sistema acceda al menu principal y/o agrege un nuevo usuario o rechazar el ingreso de un usuario sin credenciales validas* |

## 3. Preguntas

Este espacio es para poder responder todas las preguntas propuestas en esta parte del laboratorio, donde las respuestas a las mismas son las siguientes

1. Los requisitos que se sintio que necesitaban mas detalle eran los respectivos al registro y a la creacion de nuevos torneos, esto debido a que faltan detalles como la diferenciacion entre organizadores y capitanes es de forma general en la aplicacion o por torneo, es decir, un capitan puede ser organizador tambien, junto a que no se indica ningun formato tanto para el registro de nuevos usuarios como para el registro de nuevos torneos

2. No se detectaron ningun tipo de contradiccion entre los requisitos planteados para esta parte del laboratorio

3. Los que se consideran mas importantes son los de registro de usuario y los de registro de torneo, esto debido al alto impacto que tienen en el proyecto, sin mencionar que son importantes para un correcto flujo de la aplicacion

4. Un requisito que no deberia implementarse es el de tener los coloes institucionales, no es algo que afecte al proyecto y se le puede dar de forma integra el diseño a la pagina para tener una identidad propia
