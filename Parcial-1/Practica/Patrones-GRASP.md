# Centro de Instalaciones deportivas

Un centro de instalaciones deportivas quiere hacer una aplicación de reservas. En el centro existen instalaciones deportivas (piscinas, gimnasios, frontones, etc.).
El centro en cuestión tiene socios, de los cuales se almacenan su dirección, ciudad, provincia, teléfono, nombre y estado.
Existen una serie de artículos que se pueden alquilar junto con las reservas (pelotas, redes, raquetas, etc.).
Cada instalación es reservada por un socio en una fecha dada desde una hora de inicio hasta una hora de fin, siempre y cuando esté al día en sus cuotas.
Cada reserva puede tener asociada uno o varios artículos deportivos que se alquilan aparte. Por ejemplo, si yo quiero hacer una reserva para jugar a voleibol tengo que reservar una instalación "polideportivo" más un artículo red, más un artículo balón.

![image](https://github.com/user-attachments/assets/ae0601c6-c04c-4eca-9405-ad5ee4670b31)


# Cadena de Supermercados

Una cadena de supermercados decide premiar a sus clientes con un vale por el importe total de la compra en los casos donde, con la compra de ese cliente incluida, el monto total de ventas del día llega a $1000000.
Al registrar la venta, el sistema deberá verificar si, con esa venta incluida, se llega a $1000000 sumando todas las ventas del día. Si se verifica esto, entonces se registra la venta y además se envía un correo electrónico al cliente con un código aleatorio que genera el sistema y el importe de la compra, para que pueda utilizarlo en próximas compras. El código aleatorio se registra también como atributo del cliente, para que se pueda validar en el momento que el cliente lo utilice en una próxima compra. De la venta se registra cliente, fecha, número, importeTotal y detalle con cantidad, precio y artículo que se vende.

## Ejercicios para recuperar Clases y Objetos

a) En base al enunciado anterior, realizar el modelo conceptual y luego de clases de sistema completando para cada clase: su nombre, atributos y adornos, y las operaciones; las cuales deberán ser asignadas aplicando patrones GRASP.
Definir la/las operaciones para el alta de la venta incluyendo el comportamiento esperado para los casos

![image](https://github.com/user-attachments/assets/dcdeb4a0-0cdc-4d50-87be-78c31b56a869)

# Periodico Deportivo

Un periódico deportivo quiere desarrollar una aplicación para gestionar la información de eventos ciclísticos de pruebas por equipo.

El sistema tendrá información sobre los ciclistas, los equipos a los que pertenecen y las pruebas en las que cada equipo participa (se asume que en la prueba participan todos los integrantes del equipo).

De cada ciclista se desea conocer su nombre, nacionalidad y fecha de nacimiento; así como el equipo al que pertenece, con la fecha de inicio y fin del contrato con ese equipo. El ciclista puede participar de muchos equipos a lo largo de su carrera deportiva.

De cada equipo también se desea conocer su nombre, país al que representa, el nombre y apellido del director y las pruebas en las que ha participado.

De las pruebas se conoce nombre, año de edición, cantidad de etapas, kilómetros totales y puesto que ocupó cada equipo en la clasificación final. Un dato adicional para las pruebas es conocer el nombre del ciclista que llegó primero a la meta.

## Ejercicio 1

a) Realizar el modelado conceptual y luego de clases de sistema completando para cada clase: su nombre, atributos y adornos, y las operaciones; las cuales deberán ser asignadas utilizando los patrones GRASP.
Definir la/las operaciones para el alta de un equipo y para la inscripción de un equipo a una prueba
Contemplar, en el modelo, la separación de los eventos generados por los usuarios a través de la interfaz de usuario, de las clases del sistema (Patrón Controller)

![image](https://github.com/user-attachments/assets/678d0fd0-1a7c-48d1-a31c-cddbf356338f)


# Estacion Agua
Se desea desarrollar un sistema que permita registrar información acerca de la calidad de las muestras de agua de distintas estaciones de toma.

Las estaciones se identifican con un número, tienen un nombre, se registra dónde están situadas, cuál es la potencia y un rango de calidad del agua: pobre (promedio de 1 a 3), normal (promedio de 4 a 6), buena (promedio de 7 a 9), excelente (promedio de 10).
Las ciudades están divididas en sectores. Cada sector posee un nombre, un código y tiene asignada dos estaciones, que actúan como titular y otra suplente. Si una acusa calidad de agua pobre, se le asigna la otra y viceversa.
Los ciudadanos pueden consultar la calidad de agua que están recibiendo en cada momento de acuerdo con la estación que se encuentra activa en el sector donde está su domicilio.
Se debe mantener un registro histórico de las calidades. En las estaciones se toman muestras cada 1 hora. De cada muestra se registra el día, la hora y valor (entre 1 y 10). Luego, la calidad de la estación se calcula como el promedio de los valores de las últimas tres muestras y se define entre pobre, normal, buena y excelente (Ver referencia de los valores).
También es necesario tener el dato de la provincia donde se ubica la estación, para poder realizar estadísticas provinciales de la calidad de agua. A veces se requiere ver la ubicación de cada estación en un mapa.

## Ejercicios para recuperar Diagrama de Clases y Objetos

a) En base al enunciado anterior, realizar el modelo conceptual y luego de clases de sistema completando para cada clase: su nombre, atributos y adornos, y las operaciones; las cuales deberán ser asignadas aplicando patrones GRASP.
Definir la/las operaciones para el alta de una muestra (que también actualiza la calidad de la estación) y para armar y mostrar el mapa de estaciones de una provincia. Para esto último, suponer la utilización de los servicios de Google Map a través de un componente que se las brinda, y que se accede a través de una interfaz: ubicarPunto(latitud, longitud) que dibuja un punto en el mapa de acuerdo a las coordenadas y mostrarMapa(provincia) imagen del mapa de la provincia con los puntos ubicados.
Contemplar, en el modelado, la separación de los eventos generados por los usuarios a través de la interfaz de usuario, de las clases del sistema (Patrón Controlador).

![image](https://github.com/user-attachments/assets/828c27d8-5452-4291-ae93-96f13d637abd)

# Ruben
![image](https://github.com/user-attachments/assets/df022c99-87fc-40f5-a7bb-9be2b15c91be)


# Inscripcion Alumnos

Se desea desarrollar un sistema que permita la inscripción de alumnos a las materias de una carrera.
La carrera tiene muchas materias, cada materia tiene un nombre y pertenece a un nivel de la carrera (1, 2, 3, 4 o 5). Al inscribirse, el alumno puede elegir una comisión de entre 1 o muchas comisiones disponibles. Las comisiones tienen un nombre, un horario de cursada dado por día de la semana hora de inicio y fin, uno o más docentes a cargo y un aula donde se cursa (se puede cursar una o dos veces por semana). Al inscribirse en una materia, el alumno elige la comisión y el sistema registra fecha y asigna un número de inscripción. Las comisiones, para cada materia, tienen un cupo dado por la capacidad del aula asignada. La inscripción puede concretarse si la comisión elegida por el alumno, para la materia en cuestión, no excede el 10% del cupo disponible.

## Ejercicios para recuperar Diagrama de Clases y Objetos

Realizar primero el modelado conceptual, y luego de clases de sistema completando para cada clase: su nombre, atributos y operaciones; las cuales deberán ser asignadas utilizando los patrones GRASP.

Definir la/las responsabilidades de las clases para los requerimientos:

"El sistema deberá permitir inscribirse en una materia"

"El sistema debe permitir dar de alta una comisión"

Escribir el pseudocódigo de las operaciones más importantes resultantes de la implementación del requerimiento dado.

![image](https://github.com/user-attachments/assets/3a265fbc-8e83-4d93-b2f0-ad6a4dbbf9df)


# Compra Trigo

El proceso de compra de trigo para un molino harinero comienza con un contrato de compra, donde se especifica: el proveedor, la cantidad de toneladas, tipo de trigo (Blando o Duro), calidad del trigo (1, 2 o 3) y el lugar de entrega. Ningún contrato de compra puede exceder las 1000 toneladas.

Una vez formalizado el contrato de compra, se reciben tantos camiones como sea necesario hasta alcanzar la cantidad de trigo acordada en el contrato. A cada camión se lo pesa en la balanza y se le realiza un análisis de la calidad del cereal que trae. Si la calidad cumple con el valor acordado en el contrato, se registra la recepción con: fecha, hora, patente, chofer, cantidad de toneladas, calidad del trigo, estado “Aceptado” y contrato al que pertenece el camión recibido; en caso contrario, la recepción queda en estado “Rechazada”.

Una vez que se ha alcanzado la cantidad de toneladas estipulada en el contrato, se cierra el contrato de compra. Los contratos de compra cerrados deben ser pagados a los 10 días del cierre. Por esto, es necesario desarrollar un proceso que corra todos los días a las 22 horas y que: registre el pago de cada contrato que tenga 10 días de haberse cerrado al momento de la corrida y realice una transferencia conectándose a un sistema de pagos que recibe la cuenta destino y el monto a transferir para realizarla. Del pago se registra número, fecha, proveedor, contrato que se paga y monto pagado.

Ejercicios 1

Realizar primero el modelado conceptual y luego de clases de sistema completando para cada clase: su nombre, atributos y operaciones; las cuales deberán ser asignadas utilizando los patrones GRASP.

Definir la/las responsabilidades de las clases para el requerimiento “El sistema deberá realizar el pago de todos los contratos que tengan 10 días de haberse cerrado”.

Contemplar, en el modelo, la separación de los eventos generados por los usuarios a través de la interfaz de usuario, de las clases del sistema (Patrón Controller).

Escribir el pseudocódigo de las operaciones más importantes resultantes de la implementación del requerimiento dado.

![image](https://github.com/user-attachments/assets/ba3c331d-7dfc-4c6f-984c-7366e3616af3)


# Sistema Monitoreo

Se desea desarrollar un sistema de monitoreo para alarmas domiciliarias.

El sistema deberá dejar registro de la fecha y hora de los movimientos detectados en los distintos ambientes monitoreados. También se desea saber si en el momento que se detectó el movimiento, se activó la sirena o no.

Los ambientes definidos en el sistema pertenecen a un área de monitoreo. El usuario del sistema podrá definir tantas áreas como ambientes quiera. También podrá activar o desactivar un área para que suene la sirena cuando se detecte movimiento en algún ambiente de esa área. Los estados de las áreas entonces serán desactivada, activada y sonando.

Por default, cuando se crea un área en el sistema, está desactivada. Si el área está activada y se detecta movimiento, pasa a estado sonando; hasta que el usuario la desactive. Si el área está desactivada, la sirena no suena por más que se detecte movimiento.

De los ambientes se conoce el nombre, tamaño en m² y el área a la que pertenece. De las áreas se conoce el nombre y una descripción. Cada área puede tener más de un ambiente, pero el ambiente pertenece a una sola área.

Cada ambiente tiene un sensor que genera una señal al momento de detectar el movimiento. El sensor tiene un número, sensibilidad (Alta, Media, Baja) y voltaje.

La alarma se conecta a una sirena que debe sonar cuando se detecta movimiento y el área está activada.

Ejercicios 1

Realizar primero el modelado conceptual y luego de clases de sistema completando para cada clase: su nombre, atributos y operaciones; las cuales deberán ser asignadas utilizando los patrones GRASP.

Definir la/las responsabilidades de las clases para el requerimiento:
"El sistema debe registrar todos los movimientos y sonar la sirena si corresponde".

Contemplar, en el modelo, la separación de los eventos generados por los usuarios a través de la interfaz de usuario, de las clases del sistema (Patrón Controller).

Escribir el pseudocódigo de las operaciones más importantes.

![image](https://github.com/user-attachments/assets/7210f228-7410-4360-9ad5-91d49c04acc5)

# Biblioteca

![image](https://github.com/user-attachments/assets/5236e189-3a1d-4351-9687-9c0ef148ce59)

# Maquinaria

![image](https://github.com/user-attachments/assets/bfb69270-b066-468e-8ccc-afec2d3c4695)

<img width="1435" height="559" alt="image" src="https://github.com/user-attachments/assets/ef9fb20e-ef37-4a33-aa4d-b418ba3692f0" />

# Evento


