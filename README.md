# Taller de Robótica: Programación de Sistemas Embebidos en STM32 (Blue Pill)

## 1. Título y Objetivos
*   **Título:** Guía Práctica y Arquitectura de Firmware para la Familia STM32F103 (Blue Pill) en C.
*   **Objetivos:**
    *   Establecer una base sólida y estandarizada para el desarrollo de firmware en microcontroladores ARM Cortex-M3 de 32 bits.
    *   Documentar de forma modular el paso a paso teórico y práctico desde la configuración de puertos digitales (GPIOs) hasta periféricos avanzados.
    *   Consolidar código limpio, portable y eficiente orientado al desarrollo de sistemas embebidos autónomos y robótica.

## 2. Especificaciones del Circuito y Hardware Base
*   **Microcontrolador Principal:** STM32F103C8T6 ("Blue Pill", Core ARM Cortex-M3 de 32 bits, operando a 72 MHz)[cite: 1].
*   **Memoria:** 64 KB / 128 KB de Flash, 20 KB de SRAM.
*   **Toolchain y Entorno:** STM32CubeIDE (v1.9 o superior) utilizando la capa de abstracción HAL de ST.
*   **Diagrama de Pines de Referencia:**


## 3. Teoría de Operación y Estructura del Repositorio
El repositorio se encuentra estructurado en tres directorios principales para separar la documentación teórica, las hojas de datos y los códigos de desarrollo:

*   **`docs/`**: Contiene todos los módulos teóricos en formato Markdown (`README.md`) explicados a fondo (Tipos de datos, GPIOs, Interrupciones, Timers, ADC, Comunicaciones).
*   **`manuales/`**: Almacena los datasheets oficiales, manuales de referencia del fabricante y esquemáticos técnicos de la placa.
*   **`proyectos/`**: Agrupa las carpetas de código fuente (`main.c`, drivers propios, configuraciones) correspondientes a cada práctica y sistema desarrollado en el taller.