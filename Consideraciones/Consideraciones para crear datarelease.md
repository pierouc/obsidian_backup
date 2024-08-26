consideraciones para poder limpiar los datos de [[Crear DR1000UNSUP y EVAL200]] y generar datarelease:

- como primera opción seleccionar solo los estudios que cuentan con una sola serie para evitar conflictos. Se ordenarán por cantidad de instancias y se tomaran aquellos mas densos.
- hay estudios entre el inbound123 y el inbound4 que se repiten
- **todos los estudios que han llegado (31/01/2024) están en su ventana pulmonar, incluso aquellos que tienen 2, 3 o 4 series**
- estadísticas de cantidad de instancias en estudios DR1000UNSP:


| **TOTAL <br>SERIES** | **MEDIA** | **MEDIANA** | **MIN** | **MAX** |
| -------------------- | --------- | ----------- | ------- | ------- |
| 1000                 | 323       | 320         | 275     | 671     |

solo una vez como estaba todo separado y habian series en comun e instancias repetidas, hay que ordenar una vez mas los datos para juntar todo y con un shortuid correcto (DONE)

se deben tener al menos 200 instancias por serie

ejemplo de una con 115 instancias (muestra la mitad del recorrido del pulmon):

![[20240207-1921-49.3798988.mp4]]
al crear el datawarehouse, se deben agregar solo las ventanas pulmonares???? r: nop


