# Comparación de parsers CYK vs Predictivo (Punto 4)
## Descripción

En este punto se implementan dos analizadores sintácticos para una calculadora simple:

- Un parser basado en el algoritmo CYK
- Un parser descendente predictivo

El objetivo es comparar su funcionamiento y rendimiento al evaluar expresiones aritméticas.

## Archivos del proyecto
- cyk.py: Implementación del algoritmo CYK
- predictivo.py: Parser descendente recursivo
- main.py: Ejecución y comparación de ambos métodos
- pruebas.txt: Expresiones de prueba

Se trabajan expresiones simples como:
``
3+5
2+3+4
7+8+9
``
Y también casos inválidos:
``
5+
+3
3+4+X
``
Ejecución del programa
1. Abrir terminal
``
cd PComparacion
``
3. Ejecutar el programa
``
python3 main.py
``
Salida del programa
<img width="673" height="736" alt="image" src="https://github.com/user-attachments/assets/ce77b5e3-5749-4083-b450-16e1f20cab0a" />

Pruebas realizadas

Se evaluaron diferentes tipos de expresiones:

1. Expresiones válidas
3+5
2+3+4

Resultado:
<img width="366" height="162" alt="image" src="https://github.com/user-attachments/assets/d561c050-3395-434c-aea0-bb393bea50f4" />

Ambos parsers aceptan la expresión
El parser predictivo es más rápido
2. Expresiones inválidas
5+
+3
3+4+X

Resultado:

Ambos parsers detectan el error
Se evita evaluar expresiones mal formadas
3. Expresiones largas (prueba de rendimiento)
1+2+3+4+5+6+7+8+9+10

Resultado:
<img width="375" height="82" alt="image" src="https://github.com/user-attachments/assets/50c502e0-8fc3-47b0-b88b-10f3e000c93f" />

- CYK tarda más tiempo en procesar
- Predictivo mantiene tiempo bajo
## Análisis de rendimiento
## Parser CYK
- Evalúa todas las posibles combinaciones
- Utiliza programación dinámica
- Complejidad:
``
𝑂(𝑛3)
``

## Parser predictivo
- Analiza la cadena de izquierda a derecha
- No explora alternativas innecesarias
Complejidad:
``
𝑂(𝑛)
`` 

Comparación

| Característica | CYK     | Predictivo |
| -------------- | ------- | ---------- |
| Complejidad    | Alta    | Baja       |
| Velocidad      | Lenta   | Rápida     |
| Robustez       | Alta    | Media      |
| Uso práctico   | Teórico | Real       |

## Conclusiones
- El algoritmo CYK es más general, pero menos eficiente
- El parser predictivo es más rápido y práctico
- Ambos permiten validar expresiones correctamente
- La diferencia de rendimiento se hace evidente con entradas largas
