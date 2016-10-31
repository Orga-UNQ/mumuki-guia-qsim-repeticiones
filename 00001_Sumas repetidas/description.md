### La idea

Existen muchos problemas que requieren llevar a cabo una repetición hasta que se cumple una condición de fin. Por ejemplo, supongamos que se necesita multiplicar sin poder usar la instrucción MUL, considerando la siguiente documentación

```
; rutina mulAPorB 
; requiere un valor A almacenado en la celda F5F5
;               un valor B almacenado en la celda F6F5 
; modifica ???
; retorna en la celda F999 el valor de A*B, sin usar MUL
```

El cálculo de `A*B` se podría realizar sumando **B veces el valor A** (o viceversa) y si lo pensamos como un
programa en pseudocódigo, podríamos tener:

1. Inicializar un acumulador R1 en cero.
2. Verificar si B es cero.
3. Si B es cero, salir.
4. Asignar R1 = R1 + A. *Recordemos que la primera vez R1 es cero*
5. Asignar B = B - 1 . Al ir restando 1 a B nos acercamos al final del problema
6. Volver al paso 2


La estructura anterior es muy similar a lo que escribiríamos en un lenguaje Q5, como:

```
mulAPorB: MOV R1, 0x0000
volver: CMP R2, 0x0000
        JE salir
        ADD R1, R2
        SUB R2, 0x0001
        JMP volver
salir: RET
```

## A practicar

Utilice la rutina `mulAPorB` para multiplicar los valores que están almacenados en las celdas `A000` y `B000`