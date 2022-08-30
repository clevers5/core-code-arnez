# Desafío - *Miércoles 24-08-22*

## *1. Ejercicio - Una regla de divisibilidad por 13*

- **Descripción:** "Una regla de divisibilidad es una forma abreviada de determinar si un número entero dado es divisible por un divisor fijo sin realizar la división, generalmente examinando sus dígitos". Cuando divides las potencias sucesivas de 10 por 13 obtienes los siguientes restos de las divisiones enteras: 1, 10, 9, 12, 3, 4 porque: 1, 10, 9, 12, 3, 4 
- porque: 
  - 10 ^ 0 -> 1 (módulo 13) 
  - 10 ^ 1 -> 10 (módulo 13) 
  - 10 ^ 2 -> 9 (módulo 13) 
  - 10 ^ 3 -> 12 (módulo 13) 
  - 10 ^ 4 -> 3 (módulo 13) 
  - 10 ^ 5 -> 4 (módulo 13)

- Luego se repite todo el patrón. De ahí el siguiente método: Multiplicar el dígito más a la derecha del número con el número más a la izquierda en la secuencia que se muestra arriba, el segundo dígito más a la derecha con el segundo dígito más a la izquierda del número en la secuencia. 
- El ciclo continúa y sumas todos estos productos. Repita este proceso hasta que la secuencia de sumas sea estacionaria.

- **Ejemplo:**
  - ¿Cuál es el resto cuando 1234567 se divide por 13?
  - 7      6     5      4     3     2     1  (digits of 1234567 from the right)
  - ×      ×     ×      ×     ×     ×     ×  (multiplication)
  - 1     10     9     12     3     4     1  (the repeating sequence)

Por lo tanto siguiendo el método obtenemos: 7×1 + 6×10 + 5×9 + 4×12 + 3×3 + 2×4 + 1×1 = 178 Repetimos el proceso con el número 178: 8x1 + 7x10 + 1x9 = 87 y de nuevo con 87: 7x1 + 8x10 = 87 A partir de ahora la sucesión es estacionaria (siempre obtenemos 87) y el resto de 1234567 por 13 es igual al resto de 87 por 13 (es decir, 9).
- Tarea: Llame a la función que procesa esta secuencia de operaciones en un número entero n (>=0). thirt devolverá el número estacionario. thirt(1234567) calcula 178, luego 87, luego 87 y devuelve 87. thirt(321) calcula 48, 48 y devuelve 48


- **Solución:**
```typescript
export function thirt(n: number): number {
  let remainders: number[] = [1, 10, 9, 12, 3, 4];
  let result = n
    .toString()
    .split('')
    .reverse()
    .map((c: string, i: number) => parseInt(c) * remainders[i % 6])
    .reduce((p: number, c: number) => (p += c));
  return n == result ? result : thirt(result);
}
```

## *2. Ejercicio - *

- **Descripción:** Algunos números tienen propiedades divertidas. Por ejemplo: 
- 89 --> 8¹ + 9² = 89 * 1 
- 695 --> 6² + 9³ + 5⁴= 1390 = 695 * 2 
- 46288 --> 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 * 51

- Dado un entero positivo n escrito como abcd... (a, b, c, d... siendo dígitos) y un entero positivo p queremos encontrar un entero positivo k, si existe, tal que la suma de las cifras de n elevadas a las sucesivas potencias de p sea igual a k * n.
- En otras palabras: ¿Existe un número entero k como: (a ^ p + b ^ (p+1) + c ^(p+2) + d ^ (p+3) + ...) = n * k Si es el caso devolveremos k, si no devolveremos -1.
- Nota: n y p siempre se darán como números enteros estrictamente positivos.

- **Ejemplo:**
  - dig_pow(89, 1) should return 1 since 8¹ + 9² = 89 = 89 * 1
  - dig_pow(92, 1) should return -1 since there is no k such as 9¹ + 2² equals 92 * k
  - dig_pow(695, 2) should return 2 since 6² + 9³ + 5⁴= 1390 = 695 * 2
  - dig_pow(46288, 3) should return 51 since 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 * 51

- **Solución:**
```typescript
export class G964 {
  public static digPow = (n: number, p: number) => {
    const x = n
      .toString()
      .split('')
      .reduce(
        (s: number, d: string, i: number) => s + Math.pow(Number(d), p + i),
        0
      );
    return x % n ? -1 : x / n;
  };
}
```
