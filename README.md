#  Juego de luces interactivo con ESP32

### Universidad Nacional de Loja
**Facultad de la Energía, las Industrias y los Recursos Naturales No Renovables (FEIRNNR)**

**Carrera:** Computación  
**Asignatura:** Sistemas Digitales  
**Práctica:** APE N.º 002  
**Tema:** Juego de luces interactivo con ESP32

---

##  Integrantes

- Juan Calopino
- Mark Gonzalez
- Julian Vega
- Steeven Pardo
- Royel Jima

##  Descripción del proyecto

Este proyecto consiste en el diseño, programación y simulación de un **juego de luces interactivo utilizando el microcontrolador ESP32**.

El sistema controla cuatro LEDs que se encienden secuencialmente. Mediante un pulsador, el usuario puede cambiar la velocidad de la secuencia entre tres niveles: lento, medio y rápido.

La práctica permite aplicar conceptos de programación de microcontroladores, temporización no bloqueante con `millis()`, entradas y salidas digitales, resistencias pull-up internas, antirrebote y detección de flanco.

##  Objetivo

Programar en el ESP32 un juego de luces con cuatro LEDs cuya velocidad cambia mediante un pulsador, utilizando temporización no bloqueante con `millis()`, lectura del pulsador mediante `INPUT_PULLUP`, antirrebote y detección de flanco.

##  Tecnologías y herramientas

- **ESP32 DevKit V1:** microcontrolador principal.
- **Wokwi:** simulación del circuito electrónico.
- **Arduino IDE:** programación y prueba física del ESP32.
- **C++ (Arduino):** lenguaje de programación.
- **GitHub:** almacenamiento, organización y documentación del proyecto.

##  Estructura del repositorio

```text
APE2-SistemasDigitales-Jima-Vega-Calopino-Gonzalez-Pardo/
│
├── codigo1/
│   └── AP2_Codigo1.ino
│
├── codigo2/
│   └── AP2_Codigo2.ino
│
├── wokwi/
│   └── diagram.json
│
├── evidencias/
│   ├── captura_codigo1.png
│   ├── captura_codigo2.png
│   └── captura_monitor_serie.png
│
├── informe/
│   └── AP2_Informe.pdf
│
└── README.md
```

> **Nota:** Algunas carpetas y archivos se encuentran pendientes de incorporación al repositorio. Los enlaces estarán disponibles cuando se agreguen los archivos correspondientes.

##  Acceso a los archivos del proyecto

| Sección | Descripción | Enlace |
|---|---|---|
| Código 1 | Secuencia de cuatro LEDs sin `delay()` | [Ver Código 1](codigo1/AP2_Codigo1.ino) |
| Código 2 | Control de velocidad mediante pulsador | [Ver Código 2](codigo2/AP2_Codigo2.ino) |
| Wokwi | Configuración y conexiones del circuito | [Ver diagrama](wokwi/diagram.json) |
| Evidencias | Capturas de simulación y pruebas | [Ver evidencias](evidencias/) |
| Informe | Informe final de la práctica | [Ver informe PDF](informe/AP2_Informe.pdf) |

##  Funcionamiento del sistema

### Parte A. Secuencia de luces

Se implementa una secuencia de encendido de cuatro LEDs conectados a los GPIO 16, 17, 18 y 19 del ESP32.

La secuencia utiliza `millis()` para controlar el tiempo transcurrido sin detener la ejecución del programa.

Se realizan pruebas con tres períodos:

| Período | Comportamiento |
|---|---|
| 1000 ms | Secuencia lenta |
| 300 ms | Secuencia intermedia |
| 100 ms | Secuencia rápida |

### Parte B. Control de velocidad mediante pulsador

Se incorpora un pulsador conectado al GPIO 21, configurado mediante `INPUT_PULLUP`.

Cada pulsación permite cambiar entre tres velocidades:

| Velocidad | Período |
|---|---|
| Lenta | 400 ms |
| Media | 150 ms |
| Rápida | 60 ms |

El programa incluye antirrebote por software y detección de flanco para evitar múltiples cambios de velocidad durante una sola pulsación.

Los cambios de velocidad se muestran a través del Monitor Serie.

### Parte C. Prueba física del ESP32

Se contempla implementar el circuito en una protoboard y cargar el programa en una placa ESP32 DevKit V1.

El objetivo es comprobar que el funcionamiento del circuito físico coincida con el comportamiento observado en Wokwi.

##  Conexiones del circuito

| Componente | Pin ESP32 | Conexión |
|---|---|---|
| LED 1 | GPIO 16 | Resistencia de 330 Ω y LED |
| LED 2 | GPIO 17 | Resistencia de 330 Ω y LED |
| LED 3 | GPIO 18 | Resistencia de 330 Ω y LED |
| LED 4 | GPIO 19 | Resistencia de 330 Ω y LED |
| Pulsador | GPIO 21 | Pulsador conectado a GND |
| Tierra | GND | Conexión común |

##  Cómo ejecutar la simulación

1. Ingresar a [Wokwi](https://wokwi.com/).
2. Crear un proyecto nuevo con ESP32.
3. Copiar el contenido de [`wokwi/diagram.json`](wokwi/diagram.json) en el archivo `diagram.json` del proyecto.
4. Copiar el contenido de [`codigo1/AP2_Codigo1.ino`](codigo1/AP2_Codigo1.ino) en `sketch.ino`.
5. Iniciar la simulación y observar la secuencia de LEDs.
6. Reemplazar el programa por [`codigo2/AP2_Codigo2.ino`](codigo2/AP2_Codigo2.ino).
7. Iniciar nuevamente la simulación.
8. Presionar el pulsador para cambiar la velocidad y verificar los mensajes del Monitor Serie.

##  Evidencias

Las capturas de pantalla de la simulación, el funcionamiento de los códigos y las pruebas con el pulsador se almacenarán en la carpeta [evidencias](evidencias/).

##  Informe de la práctica

El informe académico contiene el procedimiento desarrollado, las tablas de resultados, las respuestas a las preguntas de control, las conclusiones y las referencias utilizadas.

 [Consultar informe AP2](informe/AP2_Informe.pdf)



---

**Universidad Nacional de Loja — Carrera de Computación**  
*Práctica APE N.º 002 — Sistemas Digitales — 2026*
