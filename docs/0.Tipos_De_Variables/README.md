# Módulo 0: Tipos de Datos y Variables en STM32

## 1. Título y Objetivos
*   **Título:** Tipos de Datos y Calificadores Esenciales para Firmware en Blue Pill (STM32F103C8T6).
*   **Objetivos:**
    *   Dominar el uso de los tipos de datos de ancho fijo (`<stdint.h>`) en microcontroladores de 32 bits.
    *   Comprender y aplicar correctamente los calificadores de almacenamiento (`volatile`, `const`, `static`) para optimizar recursos y garantizar robustez a nivel de hardware.

## 2. Especificaciones del Circuito
*   **Microcontrolador:** STM32F103C8T6 (ARM Cortex-M3 de 32 bits).
*   **Herramientas:** STM32CubeIDE / Toolchain GCC.

## 3. Teoría de Operación
Para garantizar la portabilidad y previsibilidad en arquitecturas de 32 bits, utilizamos tipos de ancho fijo y calificadores clave:

### Tipos de Datos y Variables en STM32

| Tipo de Dato (`<stdint.h>`) | Tamaño | Rango / Valores | Uso Típico en STM32 |
| :--- | :--- | :--- | :--- |
| `uint8_t` / `int8_t` | 8 bits (1 byte) | `0` a `255` / `-128` a `127` | Buffers de comunicación UART/SPI, estados de pines (ON/OFF), datos de sensores de 8 bits. |
| `uint16_t` / `int16_t` | 16 bits (2 bytes) | `0` a `65.535` / `-32.768` a `32.767` | Lecturas del ADC (resolución de 12 bits), contadores de Timers de 16 bits (TIM2/TIM3 en algunos modelos). |
| `uint32_t` / `int32_t` | 32 bits (4 bytes) | `0` a `4.294.967.295` / $\pm 2.14 \times 10^9$ | Direcciones de registros de hardware, marcas de tiempo (SysTick), contadores de 32 bits. |
| `float` | 32 bits (4 bytes) | Precisión simple ($\approx 6-7$ dígitos decimales) | Cálculos con FPU integrada, algoritmos de control (PID). |
| `bool` (`<stdbool.h>`) | 8 bits (típicamente) | `true` (1) o `false` (0) | Banderas (*flags*) lógicas de control de flujo o estados de máquinas de estados. |

### Calificadores Esenciales de Variables
En sistemas embebidos, el comportamiento de las variables a nivel de hardware se complementa con calificadores clave:
*   **`volatile`**: **Crítico.** Indica al compilador que el valor de la variable puede cambiar en cualquier momento por un factor externo al flujo normal del programa (como una interrupción - ISR o un registro de hardware mapeado en memoria). Evita que el compilador optimice la variable eliminando lecturas repetidas.
*   **`const`**: Almacena los datos directamente en la **memoria Flash** en lugar de consumir valiosa memoria RAM dinámica. Ideal para tablas de coeficientes, cadenas fijas o configuraciones estáticas.
*   **`static`**: Limita el ámbito de visibilidad de la variable al archivo o función donde se declara, conservando su valor entre llamadas sucesivas (muy útil en máquinas de estado o retardos no bloqueantes).

