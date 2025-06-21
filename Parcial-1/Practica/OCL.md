# Primer Parcial 

![image](https://github.com/user-attachments/assets/16dcd816-a11e-4c93-baa8-f04e964e7b4b)

1. Si un cliente adeuda 2 cuotas o más, la suscripción pasa a estado “Suspendida”
```ocl
Copiar código
context Suscripcion
inv: self.cuota->select(c | c.pagada = false and c.fechaVencimiento < getDate())->size() >= 2
      implies self.estado = SuscripcionEstado::Suspendida
```

2. Las suscripciones solo pueden ser de clientes con localidad “Belgrano” o “Berisso”
```ocl
Copiar código
context Suscripcion
inv: self.cliente.domicilio.localidad.nombre = 'Belgrano' or self.cliente.domicilio.
```

3. Ninguna suscripción puede tener más de 3 servicios
```ocl
Copiar código
context Suscripcion
inv: self.servicio->size() <= 3
```

4. Ningún contenido puede tener más de 3 personajes principales
```ocl
Copiar código
context Contenido
inv: self.personaje->select(p | p.principal = true)->size() <= 3
```

5. Si el contenido es una película, no puede durar más de 150 minutos
```ocl
Copiar código
context Contenido
inv: self.oclIsTypeOf(Pelicula) implies self.oclAsType(Pelicula).duracion <= 150
```

6. Operación: cantidad de cuotas adeudadas por un cliente dado
```ocl
Copiar código
context Cliente::cuotasAdeudadas(): Integer
body: self.suscripcion->collect(s | s.cuota->select(c | c.pagada = false and c.fechaVencimiento < getDate()))->flatten()->size()
```
