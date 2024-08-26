
INBOUND: nombre que se le da a cada "chunk" de datos que ha llegado.

El análisis se separa en dos partes:

## Parte 1: Inbound 1, 2, 3, 4 y 5

En primer lugar el inbound 1, 2, 3, 4 y 5 tienen en común que no cuentan con un reporte asociado y **TODAS LAS SERIES** están en ventana pulmonar. De aqui se tiene:

| **TOTAL <br>estudios** | Total<br>Inst. |
| ---------------------- | -------------- |
| 1744                   | 663635         |

| MEDIA<br>por estudio | **MEDIANA**<br>por estudio | **MIN**<br>por estudio | **MAX**<br>por estudio |
| -------------------- | -------------------------- | ---------------------- | ---------------------- |
| 380                  | 325                        | 28                     | 1630                   

| MEDIA<br>por serie | **MEDIANA**<br>por <br>serie | **MIN**<br>por serie | **MAX**<br>por serie |
| ------------------ | ---------------------------- | -------------------- | -------------------- |
| 380                | 304                          | 1                    | 671                  |


* ESTUDIOS CON 1 SERIES 1300  -->   74.5% del total
* ESTUDIOS CON 2 SERIES 398    -->   22.8% del total
* ESTUDIOS CON 3 SERIES 44      -->   2.5% del total 
* ESTUDIOS CON 4 SERIES 2        -->   0.1% del total

## Parte 2: Inbound 6 RAW

El inbound 6 es el ultimo que llegó, tuvo como gran diferencia que coincidían los estudios con los reportes. Además existen instancias y series completas que no se encuentran en la ventana pulmonar, por lo que la curación de datos fue esencial en estos datos. De igual manera este inbound contiene muchos datos atípicos como los que se muestran a continuación


| **TOTAL <br>estudios** | Total<br>Inst. |
| ---------------------- | -------------- |
| 380                    | 222182         |

| MEDIA<br>por serie | **MEDIANA**<br>por <br>serie | **MIN**<br>por serie | **MAX**<br>por serie |
| ------------------ | ---------------------------- | -------------------- | -------------------- |
| 584                | 292                          | 1                    | 1007                 |

| MEDIA<br>por estudio | **MEDIANA**<br>por estudio | **MIN**<br>por estudio | **MAX**<br>por estudio |
| -------------------- | -------------------------- | ---------------------- | ---------------------- |
| 584                  | 618                        | 1                      | 2784                   |

* ESTUDIOS CON 1 SERIE 93     -->   24.5% del total 
* ESTUDIOS CON 2 SERIE 173   -->    45.5% del total 
* ESTUDIOS CON 3 SERIE 75     -->   19.7% del total 
* ESTUDIOS CON 4 SERIE 33     -->   8.7% del total 
* ESTUDIOS CON 5 SERIE 5       -->   1.3% del total 
* ESTUDIOS CON 6 SERIE 1       -->   0.3% del total 
#### SERIES OUTLIERS

[('4', '1974924'), ('4', '2361075'), ('4', '1850333'), ('4', '1979870'), ('4', '2718372'), ('4', '2546351'), ('4', '2141278'), ('4', '2722605'), ('4', '2051039'), ('4', '2769628'), ('4', '1890090'), ('4', '2561838'), ('4', '2239155'), ('4', '1991718'), ('4', '1990241'), ('4', '1909228'), ('4', '2469286'), ('4', '1949122'), ('4', '2114868'), ('4', '1864145'), ('4', '2570766'), ('4', '2752195'), ('4', '1833717'), ('4', '1868977'), ('4', '2428082'), ('4', '2717345'), ('4', '2770991'), ('4', '2115306'), ('4', '2772560'), ('4', '2395282'), ('4', '2345150'), ('4', '2594100'), ('4', '1830576'), ('5', '2597918'), ('5', '2001093'), ('5', '2407724'), ('5', '2615991'), ('5', '2603776'), ('6', '1977668')]

1628 instancias tiene el que tiene 6 series
### PARTE 2.1: INBOUND 6 CURADO
| RAW                  | RAW            |     | CURADO               | CURADO         |     | DIFF               | DIFF               |
| -------------------- | -------------- | --- | -------------------- | -------------- | --- | ------------------ | ------------------ |
| **TOTAL <br>series** | Total<br>Inst. |     | **TOTAL <br>series** | Total<br>Inst. |     | SERIES             | ESTUDIOS           |
| 380                  | 222182         |     | 271                  | 79057          |     | 109                | 143125             |
|                      |                |     |                      |                |     | 28.7%<br>del total | 64.4%<br>del total |
Como se aprecia al realizar la curacion, los datos bajaron considerablemente

| MEDIA<br>por serie | **MEDIANA**<br>por <br>serie | **MIN**<br>por serie | **MAX**<br>por serie |
| ------------------ | ---------------------------- | -------------------- | -------------------- |
| 291                | 311                          | 1                    | 919                  |
NO OUTLIERS

ESTUDIOS CON 1 SERIE 230     -->  84.9% del total 
ESTUDIOS CON 2 SERIE 36       -->  13.3% del total
ESTUDIOS CON 3 SERIE 5         -->  1.8% del total

### PARTE 2.2: DR176 (SELECCIONADO DESDE INBOUND6 CURADO)

Ya que existe una coincidencia reporte-estudio, se crea el DR176, pero con las siguientes consideraciones
1. Se toman aquellas series que solo contienen una serie en ventana pulmonar
2. Solo se toman aquellas series que cuentan con >200 instancias, este valor asegura que la serie contiene información visual para entrenar, ya que por ejemplo, una serie con 115 instancias como la del video, muestra solo la mitad de un estudio CT.
![[20240207-1921-49.3798988.mp4]]

| **TOTAL <br>estudios** | Total<br>Inst. |
| ---------------------- | -------------- |
| 176                    | 55531          |

| MEDIA<br>por serie | **MEDIANA**<br>por <br>serie | **MIN**<br>por serie | **MAX**<br>por serie |
| ------------------ | ---------------------------- | -------------------- | -------------------- |
| 316                | 314                          | 202                  | 500                  |


## PARTE 3: RESUMEN

se consideran igualmente los 70 estudios y 19638 instancias del DR70

| **SUMA de <br>estudios** | SUMA DE<br>Inst. |
| ------------------------ | ---------------- |
| 1927                     | 905.455          |

Es importante descubrir por que hay tantos datos atípicos, además como en los distintos inbounds llegan series complementarias unas con otras, **puede que un datarelease este incompleto y no lo sabemos aún**.


## ANEXO

Ejemplo de dos series iguales con ventana pulmonar de algun estudio con 2 series de los inbound 1, 2, 3, 4 o 5, al parecer el pacientes esta boca abajo y otro boca arriba, será la misma??? 
![[Pasted image 20240312164128.png]]

Formato de directorio de archivos:
[[Directory tree format]]