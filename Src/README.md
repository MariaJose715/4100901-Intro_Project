#  Nota de Aplicación - Práctica STM32

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
| **Botón (B1)**         | Solo encendía el LED externo      | Enciende LED externo Y envía mensaje por UART |
| **Mensajes UART**      | Básicos o repetitivos             | Mensajes más claros: "Bienvenido...", "LED apagado", etc. |
| **Respuesta UART**     | Eco (repetía lo mismo)            | Convierte las palabras o letras que se introduzca en Z en el UART,tambien hay dos opciones mas en codigo, se puede cambiar el mensaje siempre a mayusculas y tambien si se ingresa a devuelve o muestra Z |

---

