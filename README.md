# Nombre del Proyecto: Control de equipos e inmobiliarios Habana Entregas.

## Ejecutores:

### Lider: 
    
    Sheyla Leyva Sánchez

### Integrantes: 

* DaríoFragas González
* Rainel Fernández Abreu
* Karlos Alejandro Alfonso
* Diamis Alfonso
  

# 1.Introducción
## 1.1 Propósito del Documento
## 1.2 Alcance del Producto
## 1.3 Definiciones, Acrónimos y abreviaturas

En lo adelante se usan las siguientes abreviaturas:

- BD: Base de Datos.
- CRUD: Create, Read, Update, Delete

Se tienen en cuenta las siguientes definiciones utilizadas a lo largo de este documento:
- aplicación de escritorio: se refiere al software con el que los usuarios interactuarán de forma
directa.
- autenticación básica: modode autenticar un usuario basado en un nombre de usuario y una
contraseña.
- medio: se refiere a medios básicos. Estos serán equipos electrónicos, mobiliario o medios
de transportación,
- entidad: representación en el sistema de los medios
- acción destructiva: acciones que puede hacer un usuario del producto que sean
irreversibles. Ej: eliminar entidades, eliminar datos de la BD
- MySQL: sistema de gestión de bases de datos relacional.
- Qt: framework multiplataforma orientado a objetos ampliamente usado para desarrollar
programas que utilicen interfaz gráfica de usuario, así como también diferentes tipos de
herramientas para la línea de comandos y consolas para servidores que no necesitan una
interfaz gráfica de usuario.
- Python: lenguaje de programación.
- PySide: una biblioteca para Python que hace de binding(conector) para las herramientas de
interfaz gráfica de usuario de Qt.
- ORM: (Object Relational Mapping) mapeo objeto-relacional es una técnica de
programación para convertir datos entre el sistema de tipos utilizado en un lenguaje de
programación orientado a objetos y la utilización de una base de datos relacional como
motor de persistencia.
- Operaciones CRUD: Operaciones de creación, actualización, lectura y eliminación de
entidades

## 1.4 Referencias
## 1.5 Resumen del resto del documeto
# 2. Descripción General
## 2.1 Perspectiva del Producto

Diseñar e implementar un Sistema Automatizado de Control de equipos y mobiliario para una
empresa de entregas, mediante una arquitectura de software suficientemente escalable,
extensible y de fácil mantenimiento que contribuya a mejorar y hacer más eficiente el proceso
de manejo y control de los medios básicos. En Habana Entregas el trabajo de control de los
medios comienza cuando arriba a él un lote de artículos para utilizar con diferentes fines. En ese
momento cada medio se incorpora al registro de Medios Básicos. Donde se clasifican
dependiendo del tipo (equipos electrónicos, mobiliario y equipo de transporte), el número de
inventario, el costo unitario, el estado en que se encuentra (bien, mal, regular) y la fecha de
ingreso. En el caso de los equipos electrónicos se conoce además del tipo (refrigerador, TV,
ventilador, aire acondicionado, computadora), la marca (Sony, Atec Panda, LG), el proveedor
usual y los años de garantía. En el caso del mobiliario se conoce el tipo (silla, mesa, buró,
mueble PC), el proveedor, el tiempo estimado de explotación y el local donde está ubicado
(recepción, almacén, oficina). En el caso de los equipos de transporte se conoce el tipo(camión,
montacargas, carro), la marca, proveedor usual, años de garantía, departamento en el que se
utiliza y función.

## 2.2 Funciones del Producto

El producto será capaz de:
Consultar de forma ágil información sobre algún medio que se encuentra en la empresa.
Añadir nuevos medios a la base de datos de la aplicación.
Actualizar algunas de las características de medios ya existentes en la base de datos.
Eliminar medios del sistema.
Modificar, otorgar o eliminar permisos que permitan acceder a algún tipo de información
delicada.
Conocer la cantidad de Equipos de un mismo tipo desglosados.
Conocer la cantidad total de medios en mal estado desglosados por tipo.
Conocer los principales proveedores de Equipamiento y Moviliario.
Conocer el costo promedio por tipo de Equipo y por tipo de Mueble.

## 2.3 Características de los usuarios

Las características de los futuros usuarios expuestas por el cliente evidenciaron que los mismos
no están familiarizados con entornos informáticos, el trabajo para mantener en inventario los
medios de la empresa siempre se habia hecho mediante el papel.
Para el uso de la aplicación no se necesitarán grandes conocimientos o experiencia en software
para el manejo de bases de datos, el producto será bastante intuitivo para que los usuarios se
sientan cómodos en su manejo.
Los usuarios que trabajarán con la aplicación tienen conociemientos sobre Excel por lo que el
manejo de tablas es una habilidad con la que están familiarizados y se enfocará gran parte del
entorno visual de la aplicacion a lograr un estilo similar al que ya conocen.

## 2.4 Restricciones Generales

De las conversaciones con el cliente se manifestó cierta inclinación sobre algunas caracteísticas
que debía presentar el software y otras que no incluían al producto.Algunas de estas fueron:

1. El tiempo de entrega del producto no podía superar los 3 meses, y debían hacerse
presentaciones mensuales de como avanzaba el proyecto.
2. No se harían reuniones fuera de las previstas de manera mensual.
3. La aplicación debia presentar una interfaz discreta y amigable para usuarios de cualquier
edad (por discreta se hacia referencia al no uso de colores muy fuertes o ventanas muy
cargadas de botones)
4. La aplicación no deberá exigir el uso de computadoras potentes.

## 2.5 Dependencias y suposiciones
Para utilizar la aplicación debemos tener conectados los usuarios que la utilicen a la base de
datos donde se encuentra la información de todos los medios de la empresa. Base de datos que
desarrollará nuestro equipo.
A solicitud del cliente la aplicación deberá correr en el Sistema Operativo Windows, no se
restringe en qué lenguaje o framework debe ser desarrollada la aplicación.
Existen las siguientes peticiones por parte del cliente:

1. Sobre los medios que se encuentren en mal estado: esta característica una vez que se
alcanza no puede ser modificada de nuevo.
2. Can aras de ganar seguridad, los permisos de jerarquía para quienes puedan acceder a
información delicada de la base de datos solo podrá ser concedida por el director de la
empresa.
3. En cuanto al tema visual se exige el uso de una tipografía legible para personas de
avanzada edad que puedan trabajar con el producto.
4. Debe existir una opción que permita reparar un error cometido de manera involuntaria (un
botón para deshacer la última opción ejecutada y diálogos de confirmación para cuando se
tomen acciones destructivas).

# 3. Requerimientos Específicos

## 3.1 Requerimientos Funcionales

El cliente no ha sido claro en cómo desea las funcionalidades del producto, el equipo ha
decidido tener una aplicación de escritorio que conecta con un sistema de gestión de base de
datos que estará alojada en la Intranet de la empresa.
Una primera vista donde el usuario se pueda autenticar con su cuenta. Existirá un sistema de
permisos a nivel de entidades. Se tendrán usuarios con más permisos que otros. Estos permisos
serán operaciones de CRUD sobre las entidades del sistema. En un inicio se tendrá un
superusuario que tendrá todos los permisos y que podrá crear usuarios con permisos
específicos.
En una segunda vista se mostrará un menú lateral donde se podrán acceder a la sección por
entidades y el resto de la vista ofrece un dashboard con un conjunto de gráficos con métricas
generales de los medios. En la vista de cada entidad se tendrá una tabla que lista las instancias
de la entidad y a la izquierda un panel con un conjunto de posibles filtros. Las columnas de la
tabla permitirán la alteración del orden de los elementos. Al tocar un elemento de la tabla se
abrirá un formulario que permite la edición de dicho elemento. Así mismo se tendrá un
formulario que permita la creación de entidades. Finalmente se tendrá un resumen a modo de
gráficas con la información solicitada para cada entidad.

## 3.2 Requerimientos no funcionales
El acceso al sistema será mediante autenticación básica. Cada usuario dentro del sistema tendrá
permisos a nivel de objeto. Para la autenticación el usuario se identifica a partir de un correo
electrónico y una constraseña. El correo tiene que corresponder a una cuenta de correo de la
empresa. La contraseña debe contener al menos 8 caracteres. La creación de nuevos usuarios
corresponderá a un manager que tenga permisos de creación de usuarios o un superusuario
que tendrá todos lo permisos en un inicio.
Se hace necesario que los datos existentes puedan ser incorporados al sistema desde un inicio.
De acuerdo al cliente estos datos se llevan en papel y solo se tienen parcialmente digitalizados
en tablas Excel.
Se espera que el producto no necesite mantenimiento periódico. Así mismo, no se espera a
corto plazo el agrego de nuevas características.
Se asume que los dispositivos donde operará el poducto serán computadoras con sistema
operativo Windows, de baja capacidad de cómputo aunque en un futuro es posible que esto
varíe.
La BD se espera que no varíe su esquema, al menos no cambios bruscos y que no exija de
migraciones complejas.
La interacción con el sistema será mediante teclado y mouse. La interfaz gráfica será simple e
intuitiva. Se proveerá además un manual y video tutoriales de cómo usar el sistema para
usuarios menos capacitados.
El software tendrá una documentación detallada para futuros desarrolladores y su
funcionalidades estarán cubiertas por tests unitarios. Se planea tener una cobertura de al menos
el 90% del código.

## 3.3 Requerimientos de entorno

Se tendrá un servidor MySQL para almacenar la información. Dicho servidor estará alojado en el
servidor de la empresa y accesible desde la Intranet de la misma. La interacción con la BD se
hará mediante un ORM integrado en la aplicación de escritorio.
La aplicación de escritorio será desarrollada usando el framework Qt, con su binding en lenguaje
Python PySide. Se tratará además que durante el desarrollo las dependencias con el sistema
operativo sean mínimas. Esto permitirá que la app sea multiplataforma aunque en un inicio se
quiere sólo para Windows.
La interacción con la base de datos será protegida por roles de accesos que dichos roles tendrá
una relación directa con el sistema de usuarios y permisos de la aplicación de escritorio. No es
totalmente necesario que la comunicación entre aplicación y la BD sea encriptada puesto que el
software operará totalmente dentro de las redes de la empresa.
Anexos
Personas etrevistadas:

1. Juan Ramón González Gonzáles, director general de la empresa Habana Entrega.
2. Mabel López Labrador, directora del departamento de Servicios Públicos.

Se produjeron dos encuentros, el primero con fecha el día 14-03-2022, que tuvo una duación de
1:30 horas con el objetivo de presentar el equipo de trabajo y tener el primer acercamiento a las
necesidades del cliente. El segundo encuentro tuvo fecha 19-03-2022 con una duración de 3:00
horas, donde el equipo hizo su propuesta del producto y se esclarecieron dudas.
Las reuniones fueron fructíferas, a pesar de que el cliente no tenia la idea del producto del todo
clara, pues, supieron expresar las funcionalidades fundamentales que necesitaban.
Al no estar convencidos de la necesidad del software se mostraron algo renuentes a concertar
varias reuniones, pero estamos satisfechos del resultado final.
