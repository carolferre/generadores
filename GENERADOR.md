# generadores

Estructuras que extraen valores de una función y se almacenan en objetos iterables (que se pueden recorrer).

Estos valores se almacenan de uno en uno

Cada vez que un generador almacea un valor, esta permanece en un estado pausado hasta que se solicita el siguiente. Esta característica es conocida como "suspensión de estado"

Ejemplo crear una función que genere números pares:

Def generaNumeros():
  yield numeros

La instancia yield constriuye un objeto iterable en el cual está almacenado el primer valor que nos ha de devolver.Va generando números pares en un bucle while hasta que llegue al valor que queremos.


¿Qué utilidad tienen?

Son más eficientes que las funciones tradicionales

Muy útiles con listas de valores infinitos

Bajo determinados escenarios, será muy útil que un generador devuelva los valores de uno en uno


Sintaxis generador:

def generaNumeros():
  yield numeros
  
 Ejemplo: Crear un programa que genere una lista de números pares:
 
 def generaPars(limite):
 
  num=1
  
  while num<limite:
    
    yield num*2
    
    num=num+1
 devuelvePares=generaPares(10)   

for i in devuelvePares:
  print(i) #devuelve todos los pares hasta 10 con el for que lee todo hasta el límite
  
  
 En caso de que pida los 3 primeros:
 
 print(next(devuelvePares)) #devuelve el primer valor que tiene almacenado en su interior con el iterador next
 
 print("Aquí podría ir más código")
 
 print(next(devuelvePares))
 
 
 Nueva instrucción yield from:
 
 Simplificamos el código del generador en el caso de que usamos bucles anidados (un for dentro de un for) en un generador.
 
 una función generador ns devuelve un objeto generador en el que se van devolviendo objetos numéricos.
 
 def miGenerador():
 
  Yield elementos
  

Se usan bucles for anidades, el bucle for principal está accediendo a los elementos del generador principal mientras que el bucle for anidado accede a los subelementos que a su vez forma parte de los elementos del generador.


Ejemplo:


Función generador que nos devuelva ciudades:

#cuando se indica un asterisco antes dice que está recibiendo un número indeterminado de elementos y en formato de tupla

def devuelve_ciudades(*ciudaes):

  for elemento in ciudades:
    
    yield elemento
    
ciudades_devueltas=devuelve_ciudades("Madrid","Barcelona","Bilbao","Valencia")

print(next(ciudades_devueltas))

print(next(ciudades_devueltas))

#SÓLO DEVUELVE LOS DOS PRIMEROS, MADRID Y BARCELONA





 def devuelve_ciudades(*ciudaes):

  for elemento in ciudades:
  
    for subElemento in elemento:
  
        yield elemento
        
   #Nos devuelve M A que son los subelementos del primer elemento
   
    
ciudades_devueltas=devuelve_ciudades("Madrid","Barcelona","Bilbao","Valencia")

print(next(ciudades_devueltas))

print(next(ciudades_devueltas))




 
 



  
