Existen 2 formas de ver si la serie es prono:
1. (0008, 103e) Series Description: Dice explícitamente si es Prono o Tórax aunque igual se encuentran otras descripciones como Tórax Post Tos o Tórax segunda inhalación
2. (0020, 0037) Image Orientation: aquí existe un array de 6 valores:
	1.  **Valor 1:** Dirección del eje X de la imagen en el espacio del paciente.
	2. **Valor 2:** Dirección del eje Y de la imagen en el espacio del paciente.
	3. **Valor 3:** Dirección del eje Z de la imagen en el espacio del paciente.
	4. **Valor 4:** Posición del origen de la imagen en el eje X del espacio del paciente.
	5. **Valor 5:** Posición del origen de la imagen en el eje Y del espacio del paciente.
	6. **Valor 6:** Posición del origen de la imagen en el eje Z del espacio del paciente.
	En el valor 5, cuando es Prono tiene un -1 y si es Tórax tiene un valor 1. Esto ultimo hay que comprobarlo con los médicos ya que es una convención que puede variar

Entiendo que en esta convención el pecho indica la dirección, por lo tanto si mi pecho apunta hacia arriba, apunta hacia los positivos del eje Y, en cambio si me pongo con el pecho en la camilla, apunto hacia los valores negativos del eje Y.

Asumo que cada eje va de -1 a 1 como en un circulo unitario

![[Pasted image 20240319173907.png]]

Debido a esta conclusión y luego de comprobar con los médicos lo propuesto, es muy sensato utilizar (0020, 0037) Image Orientation como método para chequear en que posición esta el paciente.

Por otro lado como existen algunos pacientes con varias series en tórax con diferentes preámbulos, estos podrían ser utilizados igualmente por Proximity ya que se encuentran en tórax. Es necesario confirmar lo ultimo