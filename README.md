Arquitectura de Computadores  
## Unidad 7: Manejo de Pantalla y Teclado — Post-Contenido 1  
### Ingeniería de Sistemas — 2026 
Estudiante: Sebastian Jose Padilla Escalante

---

## Descripción del laboratorio

En este laboratorio se trabajó con lenguaje ensamblador x86 usando DOSBox y NASM, enfocándose en el uso de interrupciones del sistema como INT 21h para salida de texto e INT 10h para control de pantalla.

El objetivo principal fue aprender cómo mostrar información en pantalla, manejar el cursor y aplicar colores en modo texto. También se practicó el uso de cadenas terminadas en "$" y el control de posiciones exactas en la consola.

---

# Parte 1 — Salida de texto con INT 21h

Se utilizó la interrupción INT 21h con la función 09h para imprimir cadenas en pantalla.

asm
mov ah, 09h
mov dx, msg1
int 21h
Checkpoint

El programa muestra correctamente tres líneas de texto en pantalla:

Arquitectura de Computadores
Unidad 7: Pantalla y Teclado
Laboratorio POST-1
Parte 2 — Control de pantalla con INT 10h

Se utilizó INT 10h para limpiar pantalla, posicionar el cursor y escribir caracteres con color.

Se trabajó con atributos de color donde:

Fondo = 4 bits altos
Texto = 4 bits bajos
Ejemplo de uso
mov ah, 02h
mov dh, 02h
mov dl, 0Ah
int 10h
Checkpoint
Se muestra la letra "A" en amarillo sobre fondo azul
Se muestra "U7" en rojo claro sobre negro
El cursor se posiciona correctamente en pantalla
Parte 3 — Escritura de cadenas con posición exacta

Se implementó un bucle que recorre una cadena carácter por carácter y la imprime en una posición fija usando INT 10h.

mov si, titulo
mov dl, colT
mov dh, filaT
Checkpoint
El texto "UNIDAD 7 - PANTALLA Y TECLADO" aparece en la fila 5
El texto se imprime carácter por carácter
Color verde brillante sobre fondo negro
Conclusión

Este laboratorio permitió entender cómo el sistema DOS maneja la entrada y salida mediante interrupciones. Se aprendió a controlar la pantalla, el cursor y los colores directamente desde ensamblador, lo que ayuda a comprender mejor cómo funciona la interacción entre hardware y software a bajo nivel.

Estructura del repositorio
Padilla-post1-u7/
│
├── post1.asm
├── post1b.asm
├── post1c.asm
├── README.md
└── capturas/
  
