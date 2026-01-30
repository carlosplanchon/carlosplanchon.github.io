---
layout: post
title: Tres proyectos de fin de semana - NanoSaaS, FastAPI AI Assistant, MeasureVolume
categories: programming
author:
  - Carlos A. Planchón
meta: "#programming #findesemana #proyectos"
lang: es
---

Este post cubre tres proyectos de fin de semana que abordan problemas técnicos específicos: gestión de tareas con límites de recursos, integración de asistente IA y análisis de microestructura de mercado. Cada proyecto utiliza FastAPI y Python, priorizando implementaciones directas sobre conjuntos de características comprensivas.

* * *

### 1. NanoSaaS: Control de tareas con cuotas de recursos

Un sistema ligero para gestionar tareas computacionales con límites de recursos basados en créditos.

**Características:**

- Sistema de créditos para asignación de recursos y prevención de abuso
- Monitoreo de tareas en tiempo real sin refrescos de página
- Autenticación con Google SSO
- Stack: FastAPI, Celery, Alpine.js, Tailwind CSS

El diseño está orientado a equipos pequeños o desarrolladores individuales que necesitan seguimiento de tareas con aplicación de cuotas.

GitHub: [https://github.com/carlosplanchon/nanosaas/](https://github.com/carlosplanchon/nanosaas/)

![](/media/nanosaas.png)

* * *

### 2. FastAPI AI Assistant: Plantilla de integración con OpenAI

Una aplicación minimalista de FastAPI que envuelve la API de Assistant de OpenAI con respuestas en streaming.

**Características:**

- Respuestas en streaming vía Server-Sent Events (SSE)
- Capa middleware de FastAPI entre OpenAI y el frontend
- Stack: FastAPI, Alpine.js, Tailwind CSS

La aplicación sirve como plantilla para integrar IA conversacional en sistemas existentes.

GitHub: [https://github.com/carlosplanchon/fastapi_ai_assistant](https://github.com/carlosplanchon/fastapi_ai_assistant)

![](/media/fastapi_ai_assistant.png)

* * *

### 3. MeasureVolume: Análisis de libro de órdenes

Analiza instantáneas de libros de órdenes para estimar volumen de trading y cambios de liquidez en mercados de criptomonedas.

**Características:**

- Diffing de libro de órdenes para inferir operaciones ejecutadas
- Datasets de muestra para pruebas
- Scripts de medición de actividad de takers del mercado

La herramienta proporciona un enfoque ligero para estudiar la microestructura del mercado.

GitHub: [https://github.com/carlosplanchon/measurevolume](https://github.com/carlosplanchon/measurevolume)

![](/media/measurevolume.png)
