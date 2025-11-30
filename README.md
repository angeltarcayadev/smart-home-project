# 🏠 Casa Inteligente: Sistema de Automatización Integral

Sistema completo de domótica desarrollado como Proyecto Final de Bachillerato en Robótica. Integra el control de componentes de alta tensión (220V) y sistemas mecánicos mediante una App Android personalizada con control por voz.

## 🚀 Funcionalidades Principales
1.  **Iluminación de Potencia:** Control de luces de 220V mediante módulos de Relé optoacoplados.
2.  **Sistemas Mecánicos (Acceso):**
    * Apertura automática de **Puerta Principal** (Servomotor).
    * Control de **Portón de Garage** (Servomotor).
3.  **Climatización:** Activación remota de ventilación (Motor DC).
4.  **Interfaz de Control:** App Android con botones y **Comandos de Voz** ("Abrir garage", "Encender luz").

## 🛠️ Hardware Utilizado
* **Microcontrolador:** Arduino Uno.
* **Conectividad:** Módulo Bluetooth HC-05.
* **Actuadores:**
    * 2x Servomotores (SG90 / MG995) para mecanismos de puertas.
    * 1x Módulo Relé 5V (para manejo de carga AC 220V).
    * 1x Motor DC (con driver de potencia).
* **Software:** C++ (Arduino IDE) y MIT App Inventor.

## 📡 Protocolo de Comunicación
El sistema utiliza un protocolo serial optimizado para respuesta inmediata:

| Comando | Acción | Componente |
| :---: | :--- | :--- |
| **'A' / 'B'** | ON / OFF | Luz Principal (Relé) |
| **'C' / 'D'** | ON / OFF | Ventilador |
| **'E' / 'F'** | Abrir / Cerrar | Puerta Principal |
| **'G' / 'H'** | Abrir / Cerrar | Portón Garage |

## 🔌 Diagrama de Conexiones (Pinout)

Para replicar este proyecto, realiza las siguientes conexiones en el Arduino UNO:

| Componente | Pin Arduino | Descripción |
| :--- | :---: | :--- |
| **Módulo Bluetooth (HC-05)** | RX: 0 / TX: 1 | Pines de comunicación Serial (Cruzados: RX->TX, TX->RX) |
| **Relé (Luz 220V)** | Pin 13 | Activo en HIGH (Se recomienda usar transistor si es relé desnudo) |
| **Motor DC (Ventilador)** | Pin 12 | Conectado mediante Transistor 2N2222 o Driver L293D |
| **Servo Puerta Principal** | Pin 9 | Señal PWM (Cable naranja/amarillo del servo) |
| **Servo Portón Garage** | Pin 10 | Señal PWM |
| **Alimentación** | 5V / GND | Fuente externa recomendada para los Servos y Motor |

## 📐 Esquema del Sistema

```mermaid
graph TD;
    Android[📱 App Android] -- Bluetooth (Inalámbrico) --> HC05[📡 Módulo HC-05];
    HC05 -- Serial RX/TX --> Arduino[🤖 Arduino Uno];
    
    Arduino -- Pin 13 --> Rele[💡 Relé 220V (Luz)];
    Arduino -- Pin 12 --> Motor[💨 Motor DC (Ventilador)];
    Arduino -- Pin 9 --> Servo1[🚪 Servo Puerta];
    Arduino -- Pin 10 --> Servo2[🚗 Servo Garage];
    
    style Android fill:#a2fca2,stroke:#333,stroke-width:2px;
    style Arduino fill:#3670A0,stroke:#333,stroke-width:2px,color:#fff;
    style Rele fill:#ffdd54,stroke:#333;

---
**Autor:** [Angel Tarcaya](https://github.com/angeltarcayadev)
