# Desafío - *Miércoles 31-08-22*

## *1. Ejercicio - Construir una Torre, usando Typescript*

- **Descripción:** Construye una torre en forma de pirámide dado un número entero positivo de pisos. Un bloque de pisos se representa con el carácter "*".
- Ejemplo
  - Por ejemplo, una torre con 3 pisos se ve así:
 
 ```typescript
 [
  "  *  ",
  " *** ", 
  "*****"
]
 ```
 
 Y una torre de 6 pisos se ve así:
 
 ```typescript
 [
  "     *     ", 
  "    ***    ", 
  "   *****   ", 
  "  *******  ", 
  " ********* ", 
  "***********"
]
 ```
 - Solución:

 ```typescript
export const towerBuilder = (nFloors: number): string[] => {
  if (nFloors === 1) return ['*'];
  const torre: string[] = [];
  const maxNumber = 2 * nFloors - 1;
  for (let i = 1; i <= nFloors; i++) {
    torre.push(
      `${' '.repeat(nFloors - i)}${'*'.repeat(2 * i - 1)}${' '.repeat(
        nFloors - i
      )}`
    );
  }
  return torre;
};
 ```
 
## *2. Ejercicio - Reunión, usando Typescript*

 **Descripción:** Juan ha invitado a algunos amigos. Su lista es: 
  - s = "Fred:Corwill;Wilfred:Corwill;Barney:Tornbull;Betty:Tornbull;Bjon:Tornbull;Raphael:Corwill;Alfred:Corwill";

- podrias hacer un programa 
  - que hace que esta cadena esté en mayúsculas 
  - lo da ordenado alfabéticamente por apellido
 
 Cuando los apellidos sean iguales, ordénalos por nombre. El apellido y el nombre de un invitado vienen en el resultado entre paréntesis separados por una coma.
 Entonces, el resultado de la(s) reunión(es) de funciones será:
 
  - "(CORWILL, ALFRED)(CORWILL, FRED)(CORWILL, RAPHAEL)(CORWILL, WILFRED)(TORNBULL, BARNEY)(TORNBULL, BETTY)(TORNBULL, BJON)"
- Puede ocurrir que en dos familias distintas con el mismo apellido dos personas tengan también el mismo nombre.
 

 - Solución:

 ```typescript
export function meeting(s: string): string {
     return s
    .toUpperCase()
    .split(';')
    .map((n: string) => '(' + n.split(':').reverse().join(', ') + ')')
    .sort()
    .join('');
}
 ```
