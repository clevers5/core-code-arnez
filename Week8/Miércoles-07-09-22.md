# Desafío - *Miércoles 07-09-22*

## *1. Ejercicio - Deadfish Swim, usando Typescript*

- **Descripción:** Escriba un analizador simple que analice y ejecute Deadfish. Deadfish tiene 4 comandos, cada uno de 1 carácter:

  - i --> incrementa el valor (inicialmente 0) 
  - d --> disminuye el valor
  - s --> eleva al cuadrado el valor 
  - o --> genera el valor en la matriz de retorno
- Los caracteres no válidos deben ignorarse.
- 
 ```typescript
parse("iiisdoso") => [8, 64]
 ```
 
 - Solución:

 ```typescript
export function parse(data: string): number[] {
  let v = 0,
    result: number[] = [];
  for (let d of data.split('')) {
    switch (d) {
      case 'i':
        v++;
        break;
      case 'd':
        v--;
        break;
      case 's':
        v *= v;
        break;
      case 'o':
        result.push(v);
    }
  }
  return result;
}
 ```
 
 ## *2. Ejercicio - Codificador duplicado, usando Typescript*

- **Descripción:** El objetivo de este ejercicio es convertir una cadena en una nueva cadena donde cada carácter de la nueva cadena es "(" si ese carácter aparece solo una vez en la cadena original, o ")" si ese carácter aparece más de una vez en la cadena original. Ignore las mayúsculas al determinar si un carácter es un duplicado.
 
 - Ejemplo:
 
 ```typescript
"din"      =>  "((("
"recede"   =>  "()()()"
"Success"  =>  ")())())"
"(( @"     =>  "))((" 
 ```
 
 - Los mensajes de aserción pueden no estar claros acerca de lo que muestran en algunos idiomas. Si lee "... Debería codificar XXX", "XXX" es el resultado esperado, ¡no la entrada!
 
 - Solución:

 ```typescript
export function duplicateEncode(word: string) {
  return word
    .toLowerCase()
    .split('')
    .map((a: string, i: number, w: string[]) => {
      return w.indexOf(a) == w.lastIndexOf(a) ? '(' : ')';
    })
    .join('');
}
 ```
 
  ## *3. Ejercicio - Find The Odd Int, usando Typescript*

- **Descripción:** Dada una matriz de números enteros, encuentre el que aparece un número impar de veces. Siempre habrá un solo número entero que aparecerá un número impar de veces.
- Ejemplo
 ```typescript
[7] debería devolver 7, porque ocurre 1 vez (lo cual es impar). 
[0] debería devolver 0, porque ocurre 1 vez (lo cual es impar). 
[1,1,2] debería devolver 2, porque ocurre 1 vez (lo cual es impar).
[0,1,0,1,0] debería devolver 0, porque ocurre 3 veces (lo cual es impar). 
[1,2,2,3,3,3,4,3,3,3,2,2,1] debería devolver 4, porque aparece 1 vez (lo cual es impar).
 ```
 
 - Solución:

 ```typescript
export function findOdd(xs: number[]): number {
  return (
    xs.find(
      (x: number, i: number, a: number[]) =>
        a.filter((y: number) => y === x).length % 2 === 1
    ) || -1
  );
}
 ```
 
 
  ## *4. Ejercicio - ¿Cuáles están adentro? ejercicio, usando Typescript*

- **Descripción:** Dadas dos matrices de cadenas a1 y a2 devuelven una matriz ordenada r en orden lexicográfico de las cadenas de a1 que son subcadenas de cadenas de a2.
- Ejemplo 1
 ```typescript
a1 = ["arp", "live", "strong"]
a2 = ["lively", "alive", "harp", "sharp", "armstrong"]
returns ["arp", "live", "strong"]
 ```
 - Ejemplo 2
 ```typescript
a1 = ["tarp", "mice", "bull"]
a2 = ["lively", "alive", "harp", "sharp", "armstrong"]
returns []
 ```
 
 - Las matrices se escriben en notación "general". Consulte "Sus casos de prueba" para ver ejemplos en su idioma. 
 - En Shell bash a1 y a2 son cadenas. El retorno es una cadena donde las palabras están separadas por comas. 
 - Atención: en algunos idiomas, la r debe estar sin duplicados.
 
 - Solución:

 ```typescript
export function inArray(a1: string[], a2: string[]): string[] {
    return a1
      .filter((aWord: string) => {
        return (
          a2.find((bWord: string) => bWord.indexOf(aWord) != -1) != undefined
        );
      })
      .sort();
  }
 ```
 
 
