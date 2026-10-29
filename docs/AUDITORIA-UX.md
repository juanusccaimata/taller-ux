# Auditoría UX/UI y Accesibilidad

Este documento presenta la auditoría de usabilidad y accesibilidad realizada para el **Laboratorio 11**, tomando como referencia y evolución el código del **Laboratorio 8 (DOM)**.

---

## 1. Auditoría por Heurísticas de Nielsen

| Heurística | Problema detectado (Lab 8) | Solución de rediseño (Lab 11) |
| :--- | :--- | :--- |
| **Visibilidad del estado del sistema** | Al pulsar los botones del contador o interactuar con las entradas, la retroalimentación visual era muy limitada. | Se añadieron mensajes de estado dinámicos (`role="status"`) que confirman en pantalla cada acción realizada. |
| **Coincidencia con el mundo real** | El botón de reinicio borraba el progreso de forma inmediata sin confirmación previa. | Se integró un lenguaje claro y un cuadro de diálogo interactivo de confirmación antes de reiniciar valores. |
| **Control y libertad del usuario** | Falta de opción para cancelar acciones destructivas como el reinicio del contador. | Se implementó una validación con `confirm()` que permite al usuario cancelar el reinicio si lo presiona por error. |
| **Prevención de errores** | Los campos permitían procesar envíos vacíos o correos con formato incorrecto. | Se agregaron los atributos `required`, validación de tipo `email` y control de errores mediante JS. |
| **Reconocer antes que recordar** | Los campos de entrada dependían de `placeholder` («Escribe tu nombre», «Correo») sin etiquetas visibles. | Se agregaron etiquetas `<label>` permanentes en cada campo para evitar depender de la memoria del usuario. |

---

## 2. Aplicación de Leyes de Usabilidad

* **Ley de Fitts:** Los botones «Sumar 1», «Reiniciar» y «Enviar» del Lab 8 se adaptaron a un tamaño accesible con un alto mínimo de `44px` para facilitar la interacción táctil y con ratón.
* **Ley de Hick:** Se simplificó el flujo dividiendo los ejercicios de manipulación del DOM en secciones bien definidas para agilizar la toma de decisiones.
* **Ley de Miller:** Se organizaron los componentes en tarjetas independientes (`.card`) para fragmentar la información y no saturar la vista del usuario.

---

## 3. Puntuación de Accesibilidad (Lighthouse)

Tomando como referencia el paso del **Laboratorio 8** al **Laboratorio 11**:

* **Antes (Laboratorio 8):** **87 / 100**
* **Después (Laboratorio 11):** **96 / 100** 🟢