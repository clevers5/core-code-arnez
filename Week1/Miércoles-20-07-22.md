# Desafío - *Miércoles 20-07-22*

## *1. Ejercicio Fecha de nacimiento en la matrix*

- *1024, 512, 256, 128, 64, 32, 16, 8, 4, 2, 1*

**Fecha de nacimiento**

30/04/1997

--> Traduciendo a Binario

### **(30)**/*--/----*

- 30-16 = 14 --> 1
- 14-8 = 6 --> 1
- 6-4 = 2 --> 1
- 2-2 = 0 --> 1
- 0-1 = -1 --> 0 

Respuesta --> **11110**

### *--/**(04)**/----*

- 4-4 = 0 --> 1
- 0-2 = -2 --> 0
- -2-1 = -3 --> 0 

Respuesta --> **100**

### *--/--/**(1997)***
- 1997-1024 = 973 --> 1
- 973-512 = 461 --> 1
- 461-256 = 205 --> 1
- 205-128 = 77 --> 1
- 77-64 = 13 --> 1
- *13-32 = -19 --> 0*
- *-19-16 = -35 --> 0*
- 13-8 = 5 --> 1
- 5-4 = 1 --> 1
- *1-2 = -1 --> 0*
- 1-1 = 0 --> 1

Respuesta --> **11111001101**

## Fecha de nacimiento en binario --> 11110/100/11111001101

## *2. Ejercicio MIPS*

- ### *2.1. Programa para agregar 2 números por el usuario*

```assembly
  .data
        resultado: .asciiz "\nEl resultado es: "
        número1: .asciiz "\nIngrese el pirmer número: "
        número2: .asciiz "\nIngrese el segundo número "
  .text
        main:
             
            
              li $v0, 4
              la $a0, número1
              syscall

              li $v0, 5
              syscall
              
              move $t0, $v0

              li $v0, 4
              la $a0, número2
              syscall

              li $v0, 5
              syscall

              move $t1, $v0

              add $t2, $t0, $t1

              li $v0, 4
              la $a0, resultado
              syscall

              li $v0, 1
              move $a0, $t2
              syscall
              
```

- ### *2.2. Programa para mostrar el nombre*

```assembly

.data
	      nombre: .asciiz "\nClever Arnez Ponce\n"
  .text
	      main:
              li $v0, 4
              la $a0, nombre
              syscall

```
