# Servicio Emergencias

a. Un servicio de emergencias de salud está organizado en una jerarquía de bases. Algunas de estas bases realmente disponen de personal y ambulancias, mientras que otras son meramente administrativas y agrupan un conjunto de bases. Para cada base interesa modelar los siguientes datos: nombre, número de ambulancias (que en el caso de las bases compuestas es la suma de las ambulancias disponibles en las bases que las componen en ese momento), tiempo medio de asistencia (que en el caso de las bases compuestas es la media de los tiempos medios de asistencia registrados en las bases que las componen en ese momento). De las asistencias se registra fecha, hora, base que la realizó, motivo y duración.

![image](https://github.com/user-attachments/assets/fb282b91-4fb8-4894-b9b9-04274f84889b)


b. El cálculo de las comisiones para los vendedores de una empresa se realiza de la siguiente manera: suma de los importes de las ventas del mes multiplicado por 2% para vendedores mayorista y 3% para vendedores minoristas; más $10000 de viáticos para vendedores minoristas (los mayoristas no cobran viáticos); menos adelanto de sueldo que haya solicitado cada vendedor (independientemente de que sean mayoristas o minoristas) + bono de monto fijo $3000 para los vendedores mayoristas, los minoristas no cobran bono. Desarrollar la solución al proceso anterior utilizando el patrón de diseño que crea conveniente. Tener en cuenta que podrían incorporarse vendedores de otro tipo.

![image](https://github.com/user-attachments/assets/9c32598d-9f13-4c71-86b5-179f966211ee)

# Empresa con Clientes

a. Una empresa desea beneficiar a sus clientes con descuentos que dependerán de su estado. Si el cliente tiene estado “Bien”, entonces se aplicará un descuento del 20%; si el cliente tiene estado “Regular” entonces el descuento es del 10%; y si tiene estado “Mal”, entonces no se aplicará descuento. Los descuentos se aplican sobre el importe total de la factura. Modelar la solución teniendo en cuenta que podrían incorporarse al sistema otros estados del cliente con su correspondiente descuento. Importante: se debe implementar la operación donde se utiliza el patrón.

![image](https://github.com/user-attachments/assets/8815c1e3-9a2d-47de-ba85-0fc467b42f04)

b. Dispongo de la clase “Utilidad”, cuyo método filtrar elimina de un array de objetos (propio de la clase) aquellos que no cumplen cierto criterio. El método filtrar asume que los objetos del array implementan el método cumpleCriterio() que informa si el objeto cumple o no con un criterio dado. Quiero usar la clase Utilidad para eliminar del array los objetos de tipo “Registro” que son inválidos. La clase Registro dispone del método esValido() para comprobar su validez. ¿Cómo usar la clase Utilidad para filtrar los objetos inválidos del tipo Registro que se incorporen al array?

![image](https://github.com/user-attachments/assets/359b09c1-f5da-4ba7-b09d-35ac64037a90)

# Articulos

a. Se desea clasificar artículos de acuerdo con distintas categorías. Las categorías pueden ser simples o estar compuestas por otras subcategorías. Interesa la operación que muestra el nombre de la categoría, la cual mostrará solo el nombre, para casos de categorías simples; o el nombre de camino completo (tipo UML) de la categoría dado por cat1.nombre::cat2.nombre::cat3.nombre:: etc. Desarrollar un modelo basado en patrones para el objetivo planteado.

![image](https://github.com/user-attachments/assets/9900c8fe-d83b-4305-a3ab-28d5c51c0866)

b. Diseñe un sistema que muestre la hora en distintas ciudades. Para ello se utilizará una clase RELOJ que almacena internamente la fecha y hora del sistema local y puede ser consultada con la operación verHoraLocal(). El sistema deberá mostrar la hora en cierto lugar del mundo, el lugar se determina en tiempo de ejecución. La información aparecerá en pantalla con el siguiente formato:
Hora en <<Ciudad>> : <<Hora>>

![image](https://github.com/user-attachments/assets/57d24d5f-5ffe-445c-9396-7669c34c0f2b)

# Servidor Mensajeria

a. Modelar el comportamiento de un servidor de mensajería. Cuando un cliente (remitente) envía un mensaje a otro cliente (receptor), el servidor lo recibe y lo encola para que el receptor lo pueda leer. Es necesario que los receptores no estén continuamente consultando por mensajes nuevos, sino que consulten al servidor solo en el caso de que haya uno o más mensajes suyos sin leer. Tener en cuenta que, una vez que el receptor lea el mensaje, el servidor lo elimina de la cola. Para simplificar la implementación, suponer que las conversaciones son entre 2 personas, aunque esas dos personas podrían estar conectadas desde más de un dispositivo.

b. Se desea modelar el menú de un sistema, donde los ítems del menú pueden ser accesos a funciones del sistema, o submenús que son a su vez raíz de otros ítems.
La operación a incluir es mostrarMenu(); donde la misma dibujará un rectángulo con el nombre de la función que representa (esto para los casos de ítems que son funciones del sistema); o mostrará los ítems de menú hijos en un orden establecido (esto para los casos que el ítem sea submenú).

