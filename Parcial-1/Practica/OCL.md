# Primer Parcial 

![image](https://github.com/user-attachments/assets/16dcd816-a11e-4c93-baa8-f04e964e7b4b)

1. Si un cliente adeuda 2 cuotas o más, la suscripción pasa a estado “Suspendida”
```ocl
context Suscripcion
inv: self.cuota->count(c | not c.pagada and c.fechaVencimiento < getDate()) >= 2 
     implies self.estado = SuscripcionEstado::Suspendida

```

2. Las suscripciones solo pueden ser de clientes con localidad “Belgrano” o “Berisso”
```ocl
context Suscripcion
inv: self.cliente.domicilio->forAll(d | 
        d.localidad.nombre = 'Belgrano' or d.localidad.nombre = 'Berisso')
```

3. Ninguna suscripción puede tener más de 3 servicios
```ocl
context Suscripcion
inv: self.servicio->size() <= 3
```

4. Ningún contenido puede tener más de 3 personajes principales
```ocl
context Contenido
inv: self.personaje->select(p | p.principal = true)->size() <= 3
```

5. Si el contenido es una película, no puede durar más de 150 minutos
```ocl
context Pelicula
inv: Pelicula.allInstances()->forAll(p | p.duracion <= 150)
```

6. Operación: cantidad de cuotas adeudadas por un cliente dado
```ocl
context Cliente::cuotasAdeudadas(): Integer
body: self.suscripcion.cuota->count(c | not c.pagada and c.fechaVencimiento < getDate())
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
     CartaPorte.allInstances()->select(cp | cp.contrato = self)->size() = self.cantidad
```

5. Operación: cantidad de cartas de porte de un contrato
```ocl
context Contrato::cantidadCartas(): Integer
body: CartaPorte.allInstances()->select(cp | cp.contrato = self)->size()
```

6. Fecha de carta de porte ≥ fecha del contrato
```ocl
context CartaPorte
inv: self.fecha >= self.contrato.fecha
```
Se navega a contrato para comparar fechas. Asumo que fecha es única en CartaPorte.

7. Si alguna muestra tiene grado 3 → el contrato no tiene liquidación final
```ocl
context CartaPorte
inv: self.muestra.grado = Grado::grado3 implies
     self.contrato.liquidacion->select(l | l.tipo = LiqTipo::Final)->isEmpty()
```

# Tercer Parcial

![image](https://github.com/user-attachments/assets/06c2e20a-8cb9-460e-b324-9e7a29cf1faf)

1. La nota final es el promedio de las notas de los exámenes
```ocl
context Cursada::notaFinal: Float
derive: self.examen->collect(e | e.nota)->avg()
```

2. Año de carrera de la materia = año de la comisión
```ocl
context Cursada
inv: self.materia.anoCarrera = self.comision.anoCarrera
```

3. Cada materia tiene 1 profesor Adjunto y 1 JTP
```ocl
context Materia
inv: self.materiaProfesor->select(mp | mp.cargo = ProfesorCargo::Adjunto)->size() = 1 and
     self.materiaProfesor->select(mp | mp.cargo = ProfesorCargo::JTP)->size() = 1
```

4. Las notas de los exámenes deben estar en el rango 1 a 10
```ocl
context Examen
inv: self.nota >= 1 and self.nota <= 10
```

5. Si hay 10 faltas en asistencias, la cursada pasa a estado "Libre"
```ocl
context Cursada
inv: self.asistencia->select(a | not a.presente)->size() = 10
     implies self.estado = CursadaEstado::Libre
```

6. Una cursada no puede tener más de 4 exámenes
```ocl
context Cursada
inv: self.examen->size() <= 4
```

7. Cantidad de cursantes por comisión en un año lectivo ≤ 30
```ocl
context CursadaController::altaCursada(anio: Integer, com: Comision, alu: Alumno, mat: Materia)
pre: Cursada.allInstances()->select(c | c.comision = com and c.añoLectivo = anio and c.materia = mat)->size() <= 30
```
