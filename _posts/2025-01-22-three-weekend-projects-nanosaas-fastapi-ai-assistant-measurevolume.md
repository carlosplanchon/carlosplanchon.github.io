---
layout: post
title: Three weekend projects - NanoSaaS, FastAPI AI Assistant, MeasureVolume
categories: programming
author:
  - Carlos A. Planchón
meta: "#programming #weekend #projects"
lang: en
---

This post covers three weekend projects addressing specific technical problems: task management with resource limits, AI assistant integration, and market microstructure analysis. Each project uses FastAPI and Python, prioritizing straightforward implementations over comprehensive feature sets.

* * *

### 1. NanoSaaS: Task control with resource quotas

A lightweight system for managing computational tasks with credit-based resource limits.

**Features:**

- Credit system for resource allocation and abuse prevention
- Real-time task monitoring without page refreshes
- Google SSO authentication
- Stack: FastAPI, Celery, Alpine.js, Tailwind CSS

The design targets small teams or individual developers who need task tracking with quota enforcement.

GitHub: [https://github.com/carlosplanchon/nanosaas/](https://github.com/carlosplanchon/nanosaas/)

![](/media/nanosaas.png)

* * *

### 2. FastAPI AI Assistant: OpenAI integration template

A minimal FastAPI application that wraps OpenAI's Assistant API with streaming responses.

**Features:**

- Streaming responses via Server-Sent Events (SSE)
- FastAPI middleware layer between OpenAI and frontend
- Stack: FastAPI, Alpine.js, Tailwind CSS

The application serves as a template for integrating conversational AI into existing systems.

GitHub: [https://github.com/carlosplanchon/fastapi_ai_assistant](https://github.com/carlosplanchon/fastapi_ai_assistant)

![](/media/fastapi_ai_assistant.png)

* * *

### 3. MeasureVolume: Order book analysis

Analyzes order book snapshots to estimate trading volume and liquidity changes in cryptocurrency markets.

**Features:**

- Order book diffing to infer executed trades
- Sample datasets for testing
- Market taker activity measurement scripts

The tool provides a lightweight approach to studying market microstructure.

GitHub: [https://github.com/carlosplanchon/measurevolume](https://github.com/carlosplanchon/measurevolume)

![](/media/measurevolume.png)
