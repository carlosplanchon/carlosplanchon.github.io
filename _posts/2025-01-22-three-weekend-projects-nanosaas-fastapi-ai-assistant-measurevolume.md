---
layout: post
title: Three weekend projects - NanoSaaS, FastAPI AI Assistant, MeasureVolume
categories: programming
author:
  - Carlos A. Planchón
meta: "#programming #weekend #projects"
---
**This post was written using DeepSeek-R1 AI. The tool is seems to be surprisingly precise for writing!**

**This post highlights three weekend projects—small tools built to solve real problems.** No Kubernetes, no boilerplate, no grand missions. Just focused code for niche workflows: managing task quotas, simplifying AI integrations, and analyzing market data. Built with modern tools (FastAPI, Python, lightweight JS) but designed to stay simple. Think of these as blueprints, not polished products. Let’s dive in.

* * *

### **1\. NanoSaaS: A Microservice Platform for Task Control:**

**What it does**: A lightweight system to manage computational tasks (like batch jobs or data processing) with built-in resource limits.

**Key features**:

\- **Credits system**: Users get a monthly budget to run tasks, preventing resource abuse.

\- **Real-time monitoring**: Track task progress live without refreshing the page.

\- **Google SSO**: Secure login without managing passwords.

\- **Stack**: FastAPI (backend), Celery (task queue), Alpine.js + Tailwind CSS (frontend).

**Why it matters**: Perfect for small teams or solo developers who need to track jobs without overcomplicating things. No Kubernetes, no bloat—just tasks and quotas.

→ \[[https://github.com/carlosplanchon/nanosaas/](https://github.com/carlosplanchon/nanosaas/)\]([https://github.com/carlosplanchon/nanosaas/](https://github.com/carlosplanchon/nanosaas/))

* * *

### **2\. FastAPI AI Assistant: A Chatbot That Streamlines Code:**

**What it does**: A minimalist FastAPI app that wraps OpenAI’s Code Interpreter into a real-time chatbot.

**Key features**:

\- **Streaming responses**: Answers appear word-by-word via Server-Sent Events (SSE), no waiting for full completion.

\- **Simple integration**: FastAPI acts as a clean middleware layer between OpenAI and the frontend.

\- **Stack**: FastAPI (backend), Alpine.js (frontend), Tailwind CSS (styling).

**Why it matters**: Need a no-fuss way to test OpenAI’s Assistants API? This is a template for adding conversational AI to apps without drowning in boilerplate.

→ \[[https://github.com/carlosplanchon/nanosaas/](https://github.com/carlosplanchon/nanosaas/)\]([https://github.com/carlosplanchon/fastapi\_ai\_assistant](https://github.com/carlosplanchon/fastapi_ai_assistant))

* * *

### **3\. MeasureVolume: Gauging Market Taker Activity:**

**What it does**: Analyzes order book snapshots (like those from crypto exchanges) to estimate trading volume and liquidity changes.

**Key features**:

\- **Order book diffing**: Compares consecutive snapshots to infer executed trades.

\- **Sample datasets**: Includes toy data to experiment with.

\- **Scripts**: Prebuilt tool for gauge market takers activity.

**Why it matters**: For traders or researchers, this offers a lightweight way to study market dynamics without proprietary tools.

→ \[[https://github.com/carlosplanchon/nanosaas/](https://github.com/carlosplanchon/nanosaas/)\]([https://github.com/carlosplanchon/measurevolume](https://github.com/carlosplanchon/measurevolume))

* * *

If you’re stuck on a problem, sometimes a weekend and a focused idea are all you need. Code responsibly! 🛠️