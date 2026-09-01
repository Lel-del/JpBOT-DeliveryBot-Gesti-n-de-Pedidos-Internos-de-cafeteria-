**¿Que paso bot's?**

# DeliveryBot 📦🤖

## Problema
En entornos institucionales como oficinas, universidades o grandes centros de trabajo, la gestión de pedidos de cafetería suele ser ineficiente, provocando filas largas y errores en la toma de pedidos manual. La falta de un sistema digitalizado impide que el personal de cocina organice sus tareas y que los usuarios conozcan el tiempo real de entrega de sus productos.

## Solución
DeliveryBot es una solución de automatización basada en n8n que convierte a Telegram en una terminal de pedidos inteligente. El sistema permite a los empleados o estudiantes consultar el menú, armar su carrito de compras y recibir notificaciones en tiempo real sobre el estado de su pedido (preparación, en camino, entregado), mientras genera automáticamente reportes de ventas para la administración.

---

## 🎯 Objetivos
- Implementar un sistema de pedidos digital mediante una interfaz conversacional en Telegram.
- Automatizar el cálculo de totales y la generación de números de orden únicos para cada pedido.
- Gestionar el ciclo de vida del pedido a través de estados dinámicos (Recibido, Preparación, En camino, Entregado).
- Centralizar el inventario y menú en Google Sheets para una actualización fácil por parte del administrador.
- Generar reportes diarios de ventas y métricas mediante procesos automáticos.
- Optimizar la comunicación entre la cocina y el cliente final mediante notificaciones push automáticas.

---

## 🤖 Persona del Bot: Jp (Jeipi)
**Jp** es el asistente virtual de ventas y notificaciones del sistema. Atiende pedidos con eficiencia, pero su personalidad está obsesionada con los juegos de mesa (especialmente *Tabletop Simulator* y *Four Souls*) y el mundo gamer.
- **Frase insignia:** *"¿Qué pasó bot?"*
- **Expresiones habituales:** *"ush"*, *"wosh"*, *"mucho malo"*, *"shekkete"*, *"Dc entonces?"*.

---

## ⚙️ Descripción del Sistema y Arquitectura

### Módulos Integrados
1. **Interfaz de Usuario (Telegram):** Menú digital conversacional impulsado por un agente de inteligencia artificial (Google Gemini Model), gestión de carrito y consultas de estado.
2. **Motor de Procesamiento (n8n):** Flujos integrados para recepción de pedidos, validación, cálculo de montos y notificaciones en vivo.
3. **Notificaciones de Estado:** Disparadas mediante `Google Sheets Trigger` cuando el administrador actualiza el estado de la orden.
4. **Reporte Diario de Ventas:** Ejecución programada con `Schedule Trigger` que procesa el consolidado de pedidos y ventas totales mediante un nodo de código JavaScript.

### Modelo de Datos (`DeliveryBot_DB` en Google Sheets)
- **`MENU`:** `id_producto`, `nombre`, `descripcion`, `precio`, `categoria`, `stock`.
- **`PEDIDOS`:** `id_pedido`, `id_usuario`, `detalles_pedido`, `total_pago`, `estado`, `fecha`, `hora`.
- **`USUARIOS`:** `telegram_id`, `nombre_completo`, `departamento/oficina`, `puntos_lealtad`.
- **`SESSIONS`:** `telegram_id`, `pantalla_actual`, `carrito_temporal`, `ultimo_cambio`.

---

## 📈 Resultados Esperados
- Cero pérdida de pedidos gracias al registro automático en la nube.
- Reducción de tiempos de espera en un 40% al permitir pedidos anticipados.
- Transparencia total sobre la fase de preparación del pedido.
- Inteligencia de Negocio con reportes diarios automáticos para la administración.

---

## 📁 Archivos del Repositorio
- `workflow_deliverybot.json`: Exportación del flujo modular completo en n8n.
- `README.md`: Documentación técnica del proyecto.
- `Enlace Google Sheets`: [Link a la base de datos con datos de prueba](TU_ENLACE_AQUI)
1. En el canvas de n8n, asegúrate de tener el interruptor en **`Publish`** (Activo).
2. Ve al menú superior del flujo `(...)` y selecciona **`Export`**.
3. Descarga el archivo `.json` para adjuntarlo al repositorio o entrega final.

<img width="498" height="399" alt="349013880001c70080b296829e26c4c0" src="https://github.com/user-attachments/assets/5a9a2fee-dff1-4812-a80a-4f3f354cd91e" />
<img width="1594" height="2000" alt="image" src="https://github.com/user-attachments/assets/337d23ef-b614-40dd-8cc7-8eed6ad03e3b" />

