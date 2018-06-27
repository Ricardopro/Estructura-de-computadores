# Estructura-de-computadores

Primero una breve explicación sobre lo que hemos estado haciendo y como lo hemos intentado implementar.

Primeramente hemos prestado la debida atención a la obtención de los flags de la manera que hace la maquina elemental y no directamente poner los que nos da la maquina pdp-11.

También hemos hecho las restas de la manera que nos la hace la maquina muleta, es decir, la maquina no resta sino, hace sumas con el segundo operando cambiado de signo. Esto lo hacemos complementando el valor y sumando uno al valor que queremos restar y acabamos sumando el operando destino y el operando fuente cambiado de signo.

También hemos hecho la multiplicación de la forma que no utilizamos el comando mult del apéndice de instrucciones. Esto lo conseguimos con el algoritmo sumas succesivas. 

Hemos comprobado que la multiplicación funcionase con operandos nulos, es decir 0x0 o cualquier combinación de números nulos con números no nulos

La subrutina la hemos hecha según la especificación del enunciado. Antes de entrar en ella se ha reservado un sitio en la pila para el valor que obtenemos y hemos introducido también el eir dentro de la pila y luego hacemos el comando oportuno para ir a la subrutina. Cuando la subrutina ha acabado el programa principal vuelve a tener el control y se dispone a borrar el espacio de la pila y recuperar el valor que nos ha devuelto la subrutina por la pila.

También hemos tenido que utilizar otra especie de subrutina. En este caso, no es de librería, donde hemos implementado la decodificación de los registros en un subrutina aparte ya que si no lo hacíamos así nos encontrábamos que superábamos con creces los 95 etiquetas permitidas en esta practica.

Después de reducirlo mucho nos ha quedado un programa con 91 etiquetas.

También hay que decir que hemos comprobado manualmente todas las instrucciones. 
Hemos hecho primero de todo un repaso a la desmuleta por si había fallos. Hemos aplicado el programa sin la ejecución como hicimos en las primeras practicas en el laboratorio. Seria del estilo:

eprog: 000003,000400,001000,001400,002000,003000,
eprg2: 003400,004000,004100,004200,004300,004400,
eprg3: 004500,004600,005000,006000


También hemos probado cada instrucción con codificación diferente y comprobar los flags que nos daban por si eran los adecuados. También hemos mirado que todas las instrucciones funcionaran con cada uno de los registros. Y seguidamente comprobar la obtencion de los flags conflictivos. Como por ejemplo cuando hay overflow y se desbordan los 12 bits. 

A continuación hemos comprobado que todo el tiempo los valores de los registros tomaran siempre como máximo 12 bits manteniendo los demás siempre a cero. Cuando necesitábamos hacer operaciones siempre lo hacíamos a través de los registros del pdp-11 y nunca usábamos los er0, er1,..,er7 para hacer operaciones intermedias.

Finalmente pasamos al programa en cuestión debidamente comentado a alto nivel.
