# Optimizaci-n-Cu-ntica-de-Celdas-de-Manufactura-Flexible

En las plantas industriales modernas de alta tecnología, la coordinación de piezas complejas que deben pasar por secuencias estrictas de maquinaria pesada —como celdas de mecanizado, brazos de soldadura y hornos de tratamiento térmico— genera un desafío crítico conocido como Job Shop Scheduling (JSSP). El cuello de botella principal radica en la gestión de la energía y los cambios térmicos: encender o apagar hornos industriales de forma desordenada por una mala secuenciación dispara el consumo energético y alarga los tiempos de entrega, superando las capacidades de cálculo de los algoritmos heurísticos tradicionales cuando el número de piezas crece.

Este proyecto propone un modelo de optimización cuántica basado en el algoritmo QAOA (Quantum Approximate Optimization Algorithm) adaptado para ejecutarse en el motor de iones atrapados IonQ Aria 1. Al aprovechar la conectividad completa (all-to-all) del procesador, el sistema resuelve las dependencias temporales y las restricciones de recursos compartidos de manera directa, minimizando el tiempo total de producción (makespan) y el desperdicio térmico en la planta.

Para traducir un problema físico de manufactura compleja al procesador cuántico, se siguió una estructura rigurosa:
1- Mapeo a Variables Binarias: Las decisiones críticas de prioridad (por ejemplo, qué pieza entra primero al horno industrial) se representan mediante cúbits ($q_0$ para la Pieza A, $q_1$ para la Pieza B).

2- Construcción de la Función de Costo (Hamiltoniano Industrial): El problema se formula como una función de energía matemática que equilibra dos fuerzas:
  - Términos Lineales ($Z_i$): Representan el costo operativo individual, el tiempo de procesamiento o el consumo térmico base de cada pieza en la máquina.
  - Términos de Interacción ($Z_0 Z_1$): Actúan como una restricción crítica de exclusión mutua. Si dos piezas compiten por el mismo recurso o intervalo de tiempo en el horno, se aplica una penalización alta en la función de costo.

3- Explotación del Hardware (Aria 1): En computadoras cuánticas tradicionales basadas en chips superconductores con diseño de celdas bidimensionales, interconectar piezas que dependen unas de otras requiere compuertas $SWAP$ masivas que degradan la señal por ruido. Con IonQ Aria 1, las compuertas de entrelazamiento global ($ZZ$) ocurren de forma nativa e inmediata gracias a su arquitectura de iones atrapados con conectividad total, preservando la precisión del cálculo.

Este proyecto reduce drásticamente el desperdicio energético derivado de ciclos térmicos innecesarios y optimiza los plazos de entrega de la línea de ensamblaje.

link proyecto Qollab: 
link video: 
