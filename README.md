Semaforo
Tabla de decision
Regla	    Condicion	                    Estado	    Mensaje
R1	    unidades < 0	                    Error	    Cantidad invalida
R2	    unidades = 0	                    Rojo	    Agotado
R3	    unidades >= 1 Y unidades <= 10	    Amarillo	Pedir
R4	    unidades > 10	                    Verde	    Todo bien

Prueba de escritorio
Caso	                                unidades	Regla	Salida esperada
1Normal (verde)	                        15	        R4	    Verde: todo bien
2Borde: limite inferior del verde	    11	        R4	    Verde: todo bien
3Borde: limite superior del amarillo	10	        R3	    Amarillo: pedir
4Normal (amarillo)	                    5	        R3	    Amarillo: pedir
5Borde: limite inferior del amarillo	1	        R3	    Amarillo: pedir
6Borde: cero	                        0	        R2	    Rojo: agotado
7Borde: justo debajo de cero	       -1	        R1	    Error
8Normal (error)	                       -5	        R1	    Error

Año bisiesto
Tabla de decision
Regla	MOD 4 = 0	MOD 100 <> 0	MOD 400 = 0	Resultado
R1	    No	            -	            -	    No bisiesto
R2	    Si	            Si	            -	    Bisiesto
R3	    Si	            No	            No	    No bisiesto
R4	    Si	            No	            Si	    Bisiesto

Prueba de escritorio
Caso	                                    año	    MOD 4	MOD 100	  MOD 400  Regla	Salida
1Normal, no divisible entre 4	            2026	2	        26	    26	    R1	    No bisiesto
2Borde: justo despues de un bisiesto	    2025	1	        25	    25	    R1	    No bisiesto
3Normal, divisible entre 4	                2024	0	        24	    24	    R2	    Bisiesto
4Borde: divisible entre 100, no entre 400	1900	0	        0	    300	    R3	    No bisiesto
5Borde: divisible entre 100, no entre 400	2100	0	        0	    100	    R3	    No bisiesto
6Borde: divisible entre 400	                2000	0	        0	    0	    R4	    Bisiesto
7Borde: divisible entre 400	                1600	0	        0	    0	    R4	    Bisiesto