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

---
**Autor:** [Angel Tarcaya](https://github.com/angeltarcayadev)
