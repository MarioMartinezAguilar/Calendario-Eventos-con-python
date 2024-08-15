# TITULO DEL PROYECTO    

**Creación De Calendario Personal Para Agregar Eventos con Python**

# DESCRIPCIÓN DEL PROYECTO (General)
**En este pequeño proyecto realizamos un calendario personal donde podemos agregar algún evento así como la fecha de dicho evento y los asistentes que acudirán al evento agregado a su vez también podemos agregar, eliminar, consultar actualizar los registros de nuestra base de datos (Eventos Agregados)** 

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases (class Evento))
**En el proyecto realizado creamos las clases y métodos necesarios para poder crear, actualizar, consultar y eliminar registro de nuestra base de datos. en nuestro archivo calendar_events.py comenzamos creando una clase llamada Evento y a su vez esta clase cuenta con los siguientes atributos: pk, titulo, ubicación, inicio, fin, su descripción y los asistentes que tendrá el evento en general como lo podemos ver a continuación :self.pk = pk,self.titulo = títulos, elf.ubicacion = ubicacion,self.inicio = inicio if isinstance(inicio, dt.datetime) else dt.datetime.fromisoformat(inicio),self.fin = fin if isinstance(fin, dt.datetime) else dt.datetime.fromisoformat(fin),self.descripcion = descripcion,self.asistentes = asistentes**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases (class Asistente))
**Al igual creamos una clase llamada asistentes que también cuanta con sus siguientes atributos: el identificador, email y evento esto relacionado con los asistentes del evento como se muestra a continuación: self.pk = pk, self.mail = mail, self.evento = evento**

## DESCRIPCIÓN DEL PROYECTO (creación de las funciones para poder conectarnos a la base de datos así como para la creación de tablas necesarias)
**Para poder registrar los eventos en nuestro proyecto es necesario hacer una conexión a la base de datos (sqlite3), así mis para poder crear las tablas, para ello creamos una variable que nos servirá para poder conectarnos a la base de datos (sqlite3.connect()), así mismo un nombre para la base de datos, dos funciones una de ellas para poder crear las tablas de la base de datos(eventos y asistentes) la que llamamos:iniciar_bbdd. La otra función es para poder cerrar la conexión a la base de datos la que llamamos: close_conn**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Asistentes , método objects))
**En esta parte tenemos un método llamado objects y su vez un decorador @classmethod este método recibe como parámetros una serie de condiciones(kwargs) y un operador and para poder generar la tabla asistentes en la base de datos para mayor detalle consultar el archivo calendar_events.py donde viene mas explicado**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Asistentes , método exists))
**El método exists nos indicara si existe el registro en la tabla de la base de datos es decir: Indica si el objeto se encuentra guardado en la base de datos.**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Asistentes , método save))
**Es te método es para poder guardar el registro en la base de datos en dado caso de que no exista y lo inserta en la base de datos(Tabla Asistentes)**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Asistentes , método delete))
**En este método es parta poder eliminar el objeto de la base datos, cabe decir que utilizamos un ValueError: En caos que no exista el registro en la base de datos**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Eventos , método objects))
**Al igual que la clase Asistentes el método objects recibe como parámetros un operador y los kwargs está para poder  Devolver como instancias de Evento, los registros de la base de datos que coincidan con las condiciones recibidas como kwargs.(clave: valor)**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Eventos , método day_events))
**Este método recibe como parámetro el día y devolverá como instancias de Evento, los registros de la base de datos para el día indicado en el parámetro "day".**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Eventos , método exists y save))
**Al igual que la clase asistentes cuenta con el método exist para verificar si el valor existe en la base de datos y el método save para guardar el registro en la base de datos (mayor detalle y más explicado en nuestro archivo calendar_events de nuestro repositorio)**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Eventos , delete))
**En este método eliminamos los eventos registrados , pero también eliminamos los asistentes de dicho evento registro en la base de datos**

## DESCRIPCIÓN DEL PROYECTO (creación de métodos y clases(class Eventos ,método add_asistente y delete_asistente ))
**En estos métodos se hace lo siguiente: método add_asistente este método recibe como parámetro el mail para guardar el evento antes de añadir un asistente, ahora el método delete_asistente este método recibe como parámetro también el email para  guardar el evento antes de eliminar un asistente**

# DESCRIPCION DEL PROYECTO(Manejo de interfaces)
**En esta parte del proyecto se realizó el manejo de interfaces como lo son ventanas botones, y listas. Además tenemos que instalar lo que es el  tkCalendar para poder mostrar la interfaz del calendario lo podemos instalar con el siguiente comando:pip install tkcalendar**

## DESCRIPCION DEL PROYECTO(interfaces graficas(class App))
**Aquí en esta parte al crear la clase también tenemos como atributo root,top y cal el atributo root consiste en manipular la ventana inicial de nuestro proyecto como si se cierra la ventana o se oculta, el método top es realizado para crear una ventana hija atreves de la ventana padre y por último el método cal genera lo que es nuestro calendario automáticamente tenemos que tener instalado tk_Calendar ya después agregamos los botones como se muestra en nuestro archivo calendar_interfaces.py**

## DESCRIPCION DEL PROYECTO(interfaces graficas(class ListView))
**Aquí manejamos la lista de eventos agregando algunas propiedades propias delas ventanas como lo es Scrollbar,Toplevel,Scrollbar así como los botones de la interfaz y sus eventos.**

## DESCRIPCION DEL PROYECTO(interfaces graficas(class EventoForm))
**Aquí en esta clase fue creada para poder mostrar el detalle del evento así como sus asistentes, fecha de inicio, fecha de fin, su título su ubicación, su descripción etc., también los botones que controlan la interfaz**

## DESCRIPCION DEL PROYECTO(interfaces graficas(class AsistenteForm))
**En esta clase es para crear otra interfaz del asistente donde podemos agregar su email así como los botones dela interfaz como guardar o cancelar e igual validamos si el asistente ya se encuentra en la lista**

# DESCRIPCCION DEL PROYECTO(my_calendar)
**Aquí solamente importamos los dos archivos creados e iniciamos la conexión a la base de datos y lanzamos la interfaz creada(ejecutamos en la terminal el comando PYTHON my_calendar.py para que comience nuestra aplicación)**

# DESCRIPCION DEL PROYECTO(imágenes del proyecto sus interfaces,calenadrio,etc)
**Aquí aparece el calendario donde añadimos un evento con asistentes y llenamos los datos que nos pide la interfaz**

![Imagen del calendario y agregando eventos](/img/imagen1.png)

**Aquí podemos ver seleccionando la fecha en el calendario el evento que fue agregado en esa fecha así como su detalle, podemos observar sus botones, scroll y todas las propiedades que mencionamos anteriormente, por ultimo también podemos observar el botón de eliminar los eventos los asistentes entre otras cosas mencionadas**

![calendario con fecha seleccionada y detalle del evento](/img/imagen2.png)

## Lista De Tecnologías Y Herramientas Usadas En Nuestro Proyecto  

1. PYTHON(LENGUAJE DE PROGRAMACION)
2. TERMINAL DE COMANDOS
3. SQLITE3 LO INCLUYE PYTHON
4. MODULO DE PYTHON(TK_CALENDAR)
5. OTROS MODULOS PROPIOS DE PYTHON(DATETIME) 
6. ALGUNOS PAQUETES DE PYTHON (TKINTER)   
7. GitHub

*Elaborado Por: Mario Martínez Aguilar*
 
