# 🌿 AquaSense IoT — Hydro-smart Saver 4.0

> Sistema de Riego e Hidratación Inteligente Automatizado basado en ESP32 para el uso eficiente del agua.

![Prototipo AquaSense IoT](images/prototipo_ensamblado.jpg)

---

## 📌 Descripción General
AquaSense IoT es una solución tecnológica desarrollada para el área de Tecnología e Informática del **Colegio Jorge Gaitán Cortés I.E.D.**[span_0](start_span)[span_0](end_span). El dispositivo monitorea continuamente la humedad del suelo y controla de forma autónoma una mini bomba de agua mediante un módulo relé, evitando el desperdicio de agua y previniendo el estrés hídrico en las plantas. Incorpora una pantalla OLED local y un servidor web embebido para monitoreo remoto.

---

## 🏗️ Arquitectura del Sistema
![Diagrama de Arquitectura](images/arquitectura_sistema.png)

---

## 🔌 Tabla de Conexiones Hardware

| Componente | Pin del Componente | Pin ESP32 (GPIO) | Tipo de Señal | Voltage |
| :--- | :--- | :--- | :--- | :--- |
| **Sensor Capacitivo** | VCC / GND / AOUT | 3.3V / GND / GPIO36 (VP) | Analógica (ADC) | 3.3V |
| **Módulo Relé (1CH)** | VCC / GND / IN | 5V / GND / GPIO26 | Digital (Salida) | 5V |
| **Display OLED SSD1306** | VCC / GND / SDA / SCL | 3.3V / GND / GPIO21 / GPIO22 | Digital (I2C) | 3.3V |
| **Mini Bomba DC** | Polo (+) / Polo (-) | Terminal NO Relé / GND Ext. | Potencia (Salida)| 5V |

---

## 🛠️ Instrucciones de Instalación y Carga

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/LuanaDeLosRios/aquasense-iot-hydro-smart-saver.git](https://github.com/LuanaDeLosRios/aquasense-iot-hydro-smart-saver.git)

 * Abrir el proyecto:
   Cargar la carpeta firmware/ en Visual Studio Code con la extensión PlatformIO (o IDE de Arduino / Wokwi).
 * Instalar librerías requeridas:
   * Adafruit SSD1306
   * Adafruit GFX Library
 * Compilar y Cargar:
   Conectar el ESP32 mediante cable Micro-USB/USB-C, seleccionar el puerto COM correspondiente y ejecutar Upload.
👥 Integrante y Rol
 * Luana De Los Rios
   * Rol: Diseñadora de Hardware, Programadora Embebida y Desarrolladora Web.
   * Aportes: Diseño de circuitos, firmware C++/MicroPython, modelado 3D en OpenSCAD y redacción de documentación técnica.
📜 Historial de Commits
El desarrollo fue registrado de forma progresiva manteniendo el historial de versionamiento:
 * c9f1a23 - Inicializa estructura del proyecto y añade README.md
 * a4b2c12 - Agrega lectura analógica y calibración del sensor capacitivo
 * f8e3d45 - Implementa control de salida digital para el módulo relé de la bomba
 * b1e2f34 - Integra controladores de pantalla OLED SSD1306 por bus I2C
 * e5d6c78 - Despliega servidor web HTTP embebido para monitoreo Wi-Fi