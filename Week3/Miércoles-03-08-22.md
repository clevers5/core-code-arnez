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

- **Descripción:** 

- **Ejemplo:**
  - 

- **Solución:**
```javascript

```


## *3. Ejercicio - único en orden*

- **Descripción:** 

- **Ejemplo:**
  - 

- **Solución:**
```javascript

```
