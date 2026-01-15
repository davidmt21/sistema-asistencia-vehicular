# Sistema de Asistencia Vehicular (Ackerman Steering)

![Estado del Proyecto](https://img.shields.io/badge/Estado-Finalizado-green)
![Plataforma](https://img.shields.io/badge/Plataforma-Arduino-blue)
![Licencia](https://img.shields.io/badge/Licencia-MIT-yellow)

## Descripción General
Este proyecto consiste en el diseño y construcción de un vehículo medianamente autónomo capaz de corregir fallos de manejo en tiempo real. El sistema imita funciones de seguridad vial modernas, integrando seguimiento de líneas (carriles), detección de obstáculos y frenado automático.

A diferencia de los robots diferenciales comunes, este vehículo implementa una **geometría de dirección Ackerman**, optimizando la maniobrabilidad en curvas y minimizando el deslizamiento de las ruedas.

## Funcionalidades Principales
* **Dirección Ackerman:** Sistema mecánico con eje de aluminio para un viraje preciso y realista.
* **Asistencia de Carril:** Corrección automática de trayectoria mediante sensores infrarrojos.
* **Frenado de Emergencia:** Detección de obstáculos con sensor ultrasónico (rango 2cm - 4m) con parada automática en < 3 segundos.
* **Modo Manual:** Control remoto vía Bluetooth a través de una aplicación móvil.
* **Chasis Robusto:** Diseño impreso en 3D inspirado en el Tesla Cybertruck para protección de componentes.

## Hardware y Componentes
El sistema se basa en la siguiente arquitectura electrónica:

| Componente | Especificación | Función |
|------------|----------------|---------|
| **Microcontrolador** | Arduino UNO | Cerebro del sistema (5V) |
| **Sensores** | HC-SR04 (Ultrasónico) <br> 2x Infrarrojos (IR) | Detección de obstáculos y líneas |
| **Actuadores** | 2x Motores DC (12V) <br> Servo MG995 | Tracción trasera y Dirección delantera |
| **Driver** | Puente H L298N | Control de potencia de los motores |
| **Conectividad** | Módulo Bluetooth HC-06 | Comunicación con App móvil |
| **Energía** | Batería Li-Ion 18650 (7.4V, 5800mAh) | Autonomía superior a 1 hora |

## Lógica de Control
El vehículo opera bajo un diagrama de flujo que prioriza la seguridad:

1.  **Escaneo:** El sensor ultrasónico verifica constantemente el camino.
2.  **Decisión:**
    * *Si hay obstáculo (< 10cm):* Reduce velocidad y enciende alerta naranja.
    * *Si hay obstáculo crítico (< 5cm):* Freno total y alerta roja.
    * *Si el camino es libre:* Los sensores IR monitorean las líneas del suelo para ajustar el servo de dirección.

> **Nota sobre el diseño:** El cableado fue distribuido estratégicamente por el suelo del chasis y "en el aire" para evitar interferencias con el mecanismo de dirección.


## Resultados y Pruebas
Se realizaron pruebas de diseño factorial completo con los siguientes resultados:
* **Tiempo de respuesta de frenado:** Promedio de 2.8 segundos.
* **Autonomía:** 63.3 minutos en operación continua con carga.
* **Precisión:** El eje de aluminio corrigió la flexibilidad inicial, logrando una dirección estable.

## Autores
* **Amelia Coronado** - *Universidad Internacional del Ecuador*
* **David Mejía** - *Universidad Internacional del Ecuador*

---
*Escuela de Mecatrónica - Facultad de Ciencias Técnicas (2024)*
