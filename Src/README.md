# 📑 Nota de Aplicación - Práctica STM32

## Título
**Interfaz básica con LED, Botón y UART en STM32**

---

## Resumen
Este programa implementa una aplicación básica interactiva en la tarjeta STM32.  
Utiliza el **LED interno (LD2)** como señal de “heartbeat”, un **LED externo** controlado por el botón **B1** y la **comunicación UART** para enviar/recibir mensajes con la PC.  
Además, el programa modifica la respuesta de la placa al recibir caracteres, permitiendo personalizar el comportamiento de la comunicación serial.

---

## Funciones principales
- **LD2 (Heartbeat):** Parpadea periódicamente como señal de que el programa está en ejecución.  
- **Botón B1:** Al presionarlo, enciende el LED externo por un tiempo definido y envía un mensaje por UART.  
- **LED externo:** Se mantiene encendido durante un intervalo configurable y luego se apaga automáticamente.  
- **UART:**  
  - Envía un mensaje de bienvenida al iniciar.  
  - Reporta eventos como la presión del botón o el apagado del LED externo.  
  - Procesa caracteres recibidos desde la PC y responde con un carácter distinto (por ejemplo, convirtiendo minúsculas a mayúsculas).  

---

## Parámetros configurables
- Intervalo de parpadeo de **LD2**.  
- Tiempo que permanece encendido el **LED externo**.  
- Mensajes personalizados enviados por **UART**.  
- Respuesta personalizada a los caracteres recibidos.  

---

## Conclusión
Este programa combina **GPIO**, **interrupciones** y **comunicación serial UART**, constituyendo una práctica introductoria al desarrollo de aplicaciones embebidas en **STM32**.  
La integración de hardware (LEDs y botón) con software (UART interactivo) lo convierte en un ejemplo práctico de interacción hombre-máquina en sistemas embebidos.



# 📑 Nota de Aplicación - Práctica STM32

## Título
**Encender LEDs y comunicarse con la PC en STM32**

---

## Resumen
Este programa muestra cómo usar de forma sencilla una tarjeta **STM32** para interactuar con el usuario:  
- El **LED interno (LD2)** parpadea como “latido” para indicar que el programa está corriendo.  
- El **botón B1** controla un **LED externo**, que se enciende solo un tiempo y luego se apaga.  
- La tarjeta se comunica con la **PC por el puerto serial (UART)** para enviar mensajes y responder lo que el usuario escribe.  

El objetivo es que cualquier persona pueda **ver el LED funcionando**, **pulsar el botón** y **hablar con la tarjeta desde la PC**, de manera clara y sin necesidad de conocimientos técnicos avanzados.  

---

## Funciones principales
- **LED interno (LD2):** Parpadea cada medio segundo, simulando el “latido” del sistema.  
- **Botón B1:** Cuando se pulsa, enciende un LED externo y avisa por pantalla.  
- **LED externo:** Se mantiene encendido **2 segundos** y luego se apaga solo.  
- **UART (comunicación con la PC):**  
  - Al iniciar, muestra un mensaje de bienvenida.  
  - Informa eventos (ejemplo: “Botón presionado”, “LED apagado”).  
  - Convierte las letras minúsculas que envía el usuario en **mayúsculas** como respuesta.  

---

## Parámetros configurables
- Tiempo de parpadeo del **LED interno** (ejemplo: 500 ms).  
- Tiempo que permanece encendido el **LED externo** (ejemplo: 2000 ms).  
- Mensajes enviados por UART (pueden personalizarse).  
- Respuesta a los caracteres recibidos (ejemplo: de minúscula a MAYÚSCULA).  

---

## 📊 Comparación de Cambios Realizados

| Elemento              | Versión inicial                   | Versión mejorada (actual)             |
|------------------------|-----------------------------------|----------------------------------------|
| **LED interno (LD2)** | Parpadeaba cada 100 ms            | Parpadeo cambiado a 500 ms (más visible) |
| **LED externo**        | Encendido indefinido al presionar el botón | Encendido solo 2 segundos y luego apagado automático |
| **Botón (B1)**         | Solo encendía el LED externo      | Enciende LED externo **y** envía mensaje por UART |
| **Mensajes UART**      | Básicos o repetitivos             | Mensajes más claros: "Bienvenido...", "LED apagado", etc. |
| **Respuesta UART**     | Eco (repetía lo mismo)            | Convierte minúsculas en **MAYÚSCULAS** |
| **Interactividad**     | Limitada a encender/apagar LEDs   | LED visible, botón con tiempo y conversación básica por UART |

---

## Conclusión
Con esta versión mejorada, la práctica no solo enciende LEDs sino que **guía al usuario con mensajes**, **limita los tiempos de encendido** para hacerlo más claro y **responde inteligentemente a lo que se escribe desde la PC**.  
Esto la convierte en una **introducción práctica y amigable** al mundo de los sistemas embebidos con **STM32**.
