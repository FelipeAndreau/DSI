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

