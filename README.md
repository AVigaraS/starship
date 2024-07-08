## Datos de ejemplo

Los datos de ejemplo son del cuarto lanzamiento del cohete starship de spaceX

Los datos obtenidos no son perfectos ya que se utiliza un algoritmo de reconocimiento de imagenes el cual puede fallar

Tambien he de decir que los datos han sido obtenidos mientras veia el directo del canal "Control de mision" a velocidad normal en youtube.

Esto ha podido aumentar la tasa de fallo ya que la calidad de youtube no es perfecta, ademas los numeros cambian constantemente por lo que si la caputura del dato en pantalla se produce mientras cambiaba el numero cambia, la captura sale borrosa y no se puede reconocer ningun dato.

## Como funciona

Este programa hace capturas de pantalla de areas definidas, las procesa y obtiene la telemetria mediante el reconocimiento de imagenes.

### Capturas

Las capturas que hace son de un area determinada, cuanto más pequeñas sean más rápido hace el reconocimiento de los datos.

Para obtener el csv anterior he realizado capturas en estos rectangulos de mi pantalla.

```python
    ('Hora', rectangulo(708, 829,742, 855)),
    ('Minuto', rectangulo(748, 830,782, 854)),
    ('Segundo', rectangulo(787, 829,821, 855)),
    ('Velocidad Booster', rectangulo(313, 802, 376, 822)),
    ('Altura Booster', rectangulo(331, 829,376, 848)),
    ('Velocidad Starship', rectangulo(1147, 804,1233, 823)),
    ('Altura Starhip', rectangulo(1189, 829,1235, 849))
```

Lo suyo es que la captura recoja unica y exclusivamente el numero a reconocer para evitar errores, los cuales son inevitables ya que el fondo del numero cambia constantemente, y para que no reconozca otros caracteres

### Procesado

Una vez se hacen las caputras se procesa todo en paralelo para que sea lo mas rapido posible.

### Guardado

Una vez se ha reconocido todos los datos se almacenan en un csv para su posterior tratamiento