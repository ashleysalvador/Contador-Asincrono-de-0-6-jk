# Contador asíncrono 0-6 con flip-flops JK

Simulación en Proteus de un contador de 4 bits con flip-flops JK (74LS76)
que cuenta de 0 a 6 y se reinicia automáticamente.

![Circuito](captura-circuito.png)

## Componentes
- 4 flip-flops JK (74LS76) en modo toggle (J = K = 1)
- 2 compuertas AND (U3, U4) y 1 compuerta NOT (U5)
- Generador de pulsos como reloj
- Display BCD

## Funcionamiento
1. El reloj entra al primer flip-flop. La salida de cada uno es el reloj
   del siguiente, y cada etapa divide la frecuencia entre 2.
2. Las salidas D0 a D3 van al display, que muestra el número en decimal.
3. Las compuertas AND detectan cuando D2, D1 y D0 valen 1 (número 7).
4. La compuerta NOT invierte esa señal y activa el CLR de los flip-flops,
   que vuelven a 0.
5. El estado 7 dura solo unos nanosegundos, por eso el display muestra 0 a 6.

## Secuencia
| Pulso | D3 D2 D1 D0 | Display |
|-------|-------------|---------|
| 0 | 0 0 0 0 | 0 |
| 1 | 0 0 0 1 | 1 |
| 2 | 0 0 1 0 | 2 |
| 3 | 0 0 1 1 | 3 |
| 4 | 0 1 0 0 | 4 |
| 5 | 0 1 0 1 | 5 |
| 6 | 0 1 1 0 | 6 |
| 7 | 0 1 1 1 | Reinicio a 0 |

