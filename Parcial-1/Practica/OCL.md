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

# Segundo Parcial

![image](https://github.com/user-attachments/assets/1ed0ef8b-aa96-45c7-95ed-80050a3104ba)
![image](https://github.com/user-attachments/assets/5c83e828-febd-4428-a117-ebee2558f32a)

1. El origen no puede ser igual al destino
```ocl
context CartaPorte
inv: self.origen <> self.destino
```

2. Neto de origen debe ser ≥ neto de destino
```ocl
context CartaPorte
inv: self.netoO >= self.netoD
```
3. Neto de destino = bruto destino − tara destino
```ocl
context CartaPorte
inv: self.netoD = self.brutoD - self.taraD
```

4. Si el contrato es de tipo “Camión”, la cantidad de cartas de porte = cantidad del contrato
```ocl
context Contrato
inv: self.tipo = ContratoTipo::Camion implies
     self.cartaPorte->size() = self.cantidad
```

5. Operación: cantidad de cartas de porte de un contrato
```ocl
context Contrato::cantidadCartas(): Integer
body: self.cartaPorte->size()
```

6. Fecha de carta de porte ≥ fecha del contrato
```ocl
context CartaPorte
inv: self.fecha >= self.contrato.fecha
```
Se navega a contrato para comparar fechas. Asumo que fecha es única en CartaPorte.

7. Si alguna muestra tiene grado 3 → el contrato no tiene liquidación final
```ocl
context Contrato
inv: self.cartaPorte.muestra->exists(m | m.grado = Grado::Grado3)
     implies self.liquidacion->forAll(l | l.tipo <> LiqTipo::Final)
```
