# Sistema de Asistencia Vehicular (Ackerman Steering)

![Estado del Proyecto](https://img.shields.io/badge/Estado-Finalizado-green)
![Plataforma](https://img.shields.io/badge/Plataforma-Arduino-blue)
![Licencia](https://img.shields.io/badge/Licencia-MIT-yellow)

## Descripción General
[cite_start]Este proyecto consiste en el diseño y construcción de un vehículo medianamente autónomo capaz de corregir fallos de manejo en tiempo real[cite: 123]. [cite_start]El sistema imita funciones de seguridad vial modernas, integrando seguimiento de líneas (carriles), detección de obstáculos y frenado automático[cite: 127].

[cite_start]A diferencia de los robots diferenciales comunes, este vehículo implementa una **geometría de dirección Ackerman**, optimizando la maniobrabilidad en curvas y minimizando el deslizamiento de las ruedas[cite: 205, 295].

## Funcionalidades Principales
* [cite_start]**Dirección Ackerman:** Sistema mecánico con eje de aluminio para un viraje preciso y realista[cite: 205, 278].
* [cite_start]**Asistencia de Carril:** Corrección automática de trayectoria mediante sensores infrarrojos[cite: 124, 249].
* [cite_start]**Frenado de Emergencia:** Detección de obstáculos con sensor ultrasónico (rango 2cm - 4m) con parada automática en < 3 segundos[cite: 142, 537].
* [cite_start]**Modo Manual:** Control remoto vía Bluetooth a través de una aplicación móvil[cite: 268].
* [cite_start]**Chasis Robusto:** Diseño impreso en 3D inspirado en el Tesla Cybertruck para protección de componentes[cite: 348, 359].

## Hardware y Componentes
[cite_start]El sistema se basa en la siguiente arquitectura electrónica [cite: 210-235]:

| Componente | Especificación | Función |
|------------|----------------|---------|
| **Microcontrolador** | Arduino UNO | Cerebro del sistema (5V) |
| **Sensores** | HC-SR04 (Ultrasónico) <br> 2x Infrarrojos (IR) | Detección de obstáculos y líneas |
| **Actuadores** | 2x Motores DC (12V) <br> Servo MG995 | Tracción trasera y Dirección delantera |
| **Driver** | Puente H L298N | Control de potencia de los motores |
| **Conectividad** | Módulo Bluetooth HC-06 | Comunicación con App móvil |
| **Energía** | Batería Li-Ion 18650 (7.4V, 5800mAh) | [cite_start]Autonomía superior a 1 hora [cite: 539] |

## Lógica de Control
El vehículo opera bajo un diagrama de flujo que prioriza la seguridad:

1.  **Escaneo:** El sensor ultrasónico verifica constantemente el camino.
2.  **Decisión:**
    * [cite_start]*Si hay obstáculo (< 10cm):* Reduce velocidad y enciende alerta naranja[cite: 400].
    * [cite_start]*Si hay obstáculo crítico (< 5cm):* Freno total y alerta roja[cite: 398, 408].
    * [cite_start]*Si el camino es libre:* Los sensores IR monitorean las líneas del suelo para ajustar el servo de dirección[cite: 416].

> [cite_start]**Nota sobre el diseño:** El cableado fue distribuido estratégicamente por el suelo del chasis y "en el aire" para evitar interferencias con el mecanismo de dirección[cite: 428].

## Galería y Esquemas
*(Te recomiendo subir las capturas de la Fig. 4 y Fig. 5 de tu PDF a una carpeta llamada `/img` en tu repo y descomentar las líneas de abajo)*

## Resultados y Pruebas
[cite_start]Se realizaron pruebas de diseño factorial completo con los siguientes resultados[cite: 446]:
* [cite_start]**Tiempo de respuesta de frenado:** Promedio de 2.8 segundos[cite: 544].
* [cite_start]**Autonomía:** 63.3 minutos en operación continua con carga[cite: 511].
* [cite_start]**Precisión:** El eje de aluminio corrigió la flexibilidad inicial, logrando una dirección estable[cite: 278].

## Autores
* **Amelia Coronado** - *Universidad Internacional del Ecuador*
* **David Mejía** - *Universidad Internacional del Ecuador*
* **Diego Crespo** - *Universidad Internacional del Ecuador*

---
[cite_start]*Escuela de Mecatrónica - Facultad de Ciencias Técnicas (2024)* [cite: 120]
