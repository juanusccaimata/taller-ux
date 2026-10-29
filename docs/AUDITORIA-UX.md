# Auditoría de UX/UI - App de Tareas

Documento de auditoría y rediseño de usabilidad y accesibilidad para la aplicación.

## 1. Tabla de Auditoría por Heurísticas de Nielsen

| Heurística | Problema encontrado | Solución aplicada |
| :--- | :--- | :--- |
| **Visibilidad del estado** | Al guardar o borrar una tarea no aparecía ninguna confirmación visual en pantalla. | Se agregó un mensaje directo en pantalla (`role="status"`) que confirma cuando una tarea fue creada o limpia. |
| **Coincidencia con el mundo real** | Los botones tenían nombres técnicos e impersonales como `submit` o `reset`. | Se renombraron a un lenguaje claro y cercano para el usuario: «Guardar tarea» y «Limpiar campos». |
| **Control y libertad** | Al presionar «Limpiar campos» se borraban todos los datos al instante sin confirmación. | Se implementó una alerta interactiva (`confirm()`) para dar la opción de cancelar la acción. |
| **Prevención de errores** | Permitía registrar tareas totalmente vacías si el usuario presionaba guardar por error. | Se añadieron validaciones en JavaScript y el atributo `required` para bloquear envíos sin datos. |
| **Reconocer, no recordar** | Los campos de entrada no tenían etiquetas fijas `<label>` y dependían solo del `placeholder`. | Se agregaron etiquetas `<label>` visibles y fijas arriba de cada campo de texto y selección. |

---

## 2. Justificación por Leyes de Usabilidad

* **Ley de Fitts:** El botón principal «Guardar tarea» se amplió con un área táctil de `44px` de alto y `100%` de ancho para facilitar el clic rápido.
* **Ley de Hick:** Se incluyó un menú desplegable (`<select>`) con categorías predefinidas para reducir el tiempo de decisión al clasificar la tarea.
* **Ley de Miller:** Se fragmentó la información separando el formulario de registro de la lista de tareas pendientes.

---

## 3. Puntuación de Accesibilidad (Lighthouse)

* **Antes del rediseño:** Puntaje de Accesibilidad: **65/100** (Falta de contraste, etiquetas ausentes y sin foco visible).
* **Después del rediseño:** Puntaje de Accesibilidad: **100/100** (Cumple WCAG 2.2 AA).