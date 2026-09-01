**¿Que paso bot's?**

# DeliveryBot 📦🤖

Sistema automatizado de ventas, atención al cliente y notificaciones integrado con Telegram y Google Sheets utilizando n8n.

## 👤 Persona del Bot: Jp (Jeipi)
**Jp** es el asistente virtual de ventas y notificaciones del sistema. Aunque cumple con total precisión las operaciones de registros de pedidos y reportes, su personalidad es informal, apasionada por los videojuegos y obsesionada con los juegos de mesa (especialmente *Tabletop Simulator* y *Four Souls*). 

- **Frase insignia:** *"¿Qué pasó bot?"*
- **Expresiones habituales:** *"ush"*, *"wosh"*, *"mucho malo"*, *"shekkete"*, *"Dc entonces?"*.

---

## 🛠️ Arquitectura y Tecnologías
- **Motor de Automatización:** n8n (Cloud)
- **Base de Datos:** Google Sheets (Pestaña `PEDIDOS`)
- **Canal de Interacción:** Telegram Bot API
- **Modelos IA:** Google Gemini Chat Model (Procesamiento de lenguaje natural y toma de pedidos)

---

## 🚀 Módulos del Sistema

1. **Recepción y Procesamiento de Pedidos (AI Agent):**
   - Captura requerimientos del cliente por Telegram.
   - Procesa la orden y consulta el catálogo.
   - Guarda los registros en Google Sheets (`id_pedido`, `id_usuario`, `detalles_pedido`, `total_pago`, `estado`).

2. **Notificaciones de Estado en Tiempo Real (`Google Sheets Trigger`):**
   - Escucha cambios en la columna `estado`.
   - Envía alertas dinámicas a Telegram mapeando automáticamente el `id_usuario` del cliente.

3. **Reporte Diario de Ventas (`Schedule Trigger`):**
   - Ejecución programada diaria.
   - Consolida y suma las ventas totales del día mediante un nodo JavaScript (`Code`).
   - Envía el resumen consolidado al administrador.

---

## 📌 Pasos para Exportar / Entregar
1. En el canvas de n8n, asegúrate de tener el interruptor en **`Publish`** (Activo).
2. Ve al menú superior del flujo `(...)` y selecciona **`Export`**.
3. Descarga el archivo `.json` para adjuntarlo al repositorio o entrega final.
