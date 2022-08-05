# Desafío - *Miércoles 03-08-22*

## *1. Ejercicio - Parentesis válidos*

- **Descripción:** Escribe una función que tome una cadena de paréntesis y determine si el orden de los paréntesis es válido. La función debe devolver verdadero si la cadena es válida y falso si no es válida.

- **Ejemplo:**
  - "()"              =>  true
  - ")(()))"          =>  false
  - "("               =>  false
  - "(())((()())())"  =>  true

- Restricciones 
  - 0 <= entrada.longitud <= 100

- **Solución:**
```javascript
function validParentheses(parens) {
  let valid = 0;
  for (let i = 0; i < parens.length; i++) {
    if (parens[i] === ')') valid--;
    if (parens[i] === '(') valid++;
    if (valid < 0) return false;
  }
  return valid == 0;
}
```


## *2. Ejercicio - Convertir cadena en caso de camello*

- **Descripción:** Complete el método/función para que convierta las palabras delimitadas por guiones/guiones bajos en mayúsculas y minúsculas. La primera palabra dentro de la salida debe estar en mayúsculas solo si la palabra original estaba en mayúsculas (conocido como Upper Camel Case, también conocido como caso Pascal).

- **Ejemplo:**
  - "the-stealth-warrior" gets converted to "theStealthWarrior"
  - "The_Stealth_Warrior" gets converted to "TheStealthWarrior"

- **Solución:**

```javascript
function toCamelCase(str){
  let resultado = '';
  let pos = str.length;
  for(let i = 0; i < pos; i++){
    if(i != 0 && (str[i - 1] === '_' || str[i - 1] === '-')) {
      resultado += str[i].toUpperCase();
    } else if (str[i] != '-' && str[i] != '_') {
      resultado += str[i];
    }
  }
  return resultado;
}
```


## *3. Ejercicio - único en orden*

- **Descripción:** Implemente la función unique_in_order que toma como argumento una secuencia y devuelve una lista de elementos sin ningún elemento con el mismo valor uno al lado del otro y conservando el orden original de los elementos.

- **Ejemplo:**
  - uniqueInOrder('AAAABBBCCDAABBB') == ['A', 'B', 'C', 'D', 'A', 'B']
  - uniqueInOrder('ABBCcAD')         == ['A', 'B', 'C', 'c', 'A', 'D']
  - uniqueInOrder([1,2,2,3,3])       == [1,2,3]

- **Solución:**
```javascript
function uniqueInOrder(iterable) {
  let result = [];
  let last;
  for (let i = 0; i < iterable.length; i++) {
    if (iterable[i] !== last) {
      last = iterable[i];
      result.push(last);
    }
  }
  return result;
}
```
