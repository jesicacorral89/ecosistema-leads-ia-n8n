# Ecosistema de Automatización IA — Clasificación de Leads

Automatización que analiza mensajes de leads y los clasifica (VIP / Estándar / Descartado) 
usando inteligencia artificial, con validación humana antes de contactar al cliente.

## Stack utilizado
- **Orquestador:** n8n
- **Base de datos:** Airtable
- **Motor de IA:** Groq (Llama 3.1 8B) — API compatible con OpenAI/Anthropic
- **Canal de salida / HITL:** Telegram

## Contenido de este repositorio
- `documentación.pdf` — Diagrama de arquitectura, prints de evidencia y explicación técnica completa
- `Gestión de Leads IA - Ecosistema Final (4).json` — Blueprint exportado del flujo de n8n
- `video_demo_final.mp4` — Video demo con las 5 corridas de test (trigger, procesamiento, HITL y resultado final)

## Base de datos (modo lectura)
https://airtable.com/invite/l?inviteId=invLKVEamXERqdqPK&inviteToken=7807e6d0aacf12bc007d1e8954f3132c9ca4840400ee003d998c9e507f851db1&utm_medium=email&utm_source=product_team&utm_content=transactional-alerts

## Arquitectura del flujo
Trigger (Manual) → Registros de búsqueda (Airtable, Estado=Pendiente) → Validación de datos 
→ IA (Groq/Llama) → Human-in-the-loop (Telegram) → Actualización de registro → Notificación al lead
