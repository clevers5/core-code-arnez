# DESAFÍO *Miércoles-27-07-22*


## *1. Continúe con el curso de HTML*

- Aprendiendo

## *2. Ejercicio Char from ASCII Value*

- **Descripción:**
  Escriba una función get_char() / getChar() que tome un número y devuelva el carácter ASCII correspondiente a ese valor.
  
- Solución

```javascript

function getChar(c){
  return String.fromCharCode(c);
}
```

## *3. Ejercicio de suma binaria*

- **Descripción:**
Implemente una función que sume dos números y devuelva su suma en binario. La conversión se puede hacer antes o después de la adición. El número binario devuelto debe ser una cadena. Ejemplos:(Entrada1, Entrada2 --> Salida (explicación)))
1, 1 --> "10" (1 + 1 = 2 in decimal or 10 in binary)
5, 9 --> "1110" (5 + 9 = 14 in decimal or 1110 in binary)

- Solución

```javascript
function addBinary(a,b) {
return (a + b).toString(2);
}
```

## *4. Ejercicio de calificación final del estudiante*

- **Descripción:**
Cree una función notaFinal, que calcule la nota final de un estudiante en función de dos parámetros: una nota para el examen y una cantidad de proyectos completados.
Esta función debe tomar dos argumentos: examen - calificación del examen (de 0 a 100); proyectos - número de proyectos completados (de 0 en adelante); Esta función debería devolver un número (calificación final). 

  - Hay cuatro tipos de calificaciones finales:
     - 100, si la calificación del examen es superior a 90 o si el número de proyectos terminados es superior a 10. 
     - 90, si la calificación del examen es superior a 75 y si el número de proyectos completados es mínimo 5.
     - 75, si la calificación del examen es superior a 50 y si el número de proyectos completados es mínimo 2. 
     - 0, en otros casos

  - Ejemplos (Entradas-->Salida): 
    - 100, 12 --> 100 
    - 99, 0 --> 100 
    - 10, 15 --> 100 
    - 85, 5 --> 90 
    - 55, 3 --> 75 
    - 55, 0 --> 0 
    - 20, 2 --> 0

- Solución

```javascript
function finalGrade (exam, projects) {
  let resultado = 0;
  if(exam > 90 || projects > 10){
      resultado = 100;
    } else if (exam > 75 && projects >= 5){
      resultado = 90;
    } else if(exam > 50 && projects >= 2){
      resultado = 75;
  }else{
    resultado = 0;
  }
  return resultado;
}
```
