# BNB-online

# 🧠 Idea Alchemist Agent

*A Creative AI System Powered by Google ADK + Gemma with Cloud-Run Ready Deployment*

---

## 📌 Overview

The **Idea Alchemist Agent** is an AI-powered creative brainstorming system designed to help individuals and teams generate innovative ideas—ranging from business concepts and products to content, inventions, and storytelling prompts.

Unlike typical chatbots that respond predictably, this agent is built with a **personality layer** that encourages curiosity, experimentation, and imaginative thinking. It transforms standard inputs into practical, bold, and futuristic ideas — making it a useful tool for:

* Students and researchers
* Startup founders and innovators
* Content creators and designers
* Educators and workshop facilitators

---

## 🎯 Core Features

* ⚙️ **Personality-Driven Responses** using ADK instructions
* 🧪 **Three-Tier Creativity Framework**:

  * Safe: Realistic practical ideas
  * Bold: Unique and unexpected concepts
  * Chaotic: Imaginative and futuristic explorations
* 🧵 **Session-Aware Conversations** (context persistence)
* 🚀 **GPU-accelerated inference with Gemma model**
* 📡 **Cloud Run-friendly modular architecture**
* 📈 **Load-tested using Locust for scalability validation**

---

## 🏗️ Architecture Summary

The system is built using a modular design with three major layers:

1. **Model Backend (GPU-Optimized Service)**
   Runs the Gemma LLM using Ollama with GPU acceleration.

2. **Agent Logic Layer (Google ADK + FastAPI)**
   Defines the agent’s memory, behavior, instructions, and response style.

3. **Load Testing + Observability Layer (Locust)**
   Simulates real-world user traffic and validates elasticity under load.

This separation ensures scalability, maintainability, and easy deployment across environments.

---

## 📂 Project Structure

```
idea-alchemist-agent/
│
├── agent/                # Core agent logic, persona rules, ADK config
├── server.py             # FastAPI app wired to the agent
├── Dockerfile.agent      # Agent service container
├── Dockerfile.model      # Model backend container (Ollama + Gemma)
├── load_test/locust.py   # Load testing script
├── .env.example          # Environment config template
└── README.md             # Documentation
```

---

## 🚀 Deployment Overview

### 1. Build and push containers

```
docker build -f Dockerfile.model -t idea-model .
docker build -f Dockerfile.agent -t idea-agent .
```

### 2. Deploy Model Service (Cloud Run GPU)

Expose endpoint and note URL.

### 3. Deploy Agent Service

Configure environment variables:

```
OLLAMA_API_BASE=<Model Service URL>
GEMMA_MODEL_NAME=gemma3:270m
```

### 4. Run Load Tests (Optional)

```
locust -f load_test/locust.py
```

---

## 📁 Artifacts Included

* Model Dockerfile
* Agent Dockerfile
* ADK configuration
* FastAPI service
* Load testing script (Locust)
* Environment sample file
* Documentation

---

## 🧪 Try an Example Query

```
"Mix astronomy and bakery — give me three startup ideas."
```

Expected response style:

* Safe: A space theme bakery concept
* Bold: Edible constellations with AI personalization
* Chaotic: Zero-gravity baking experience in the metaverse

---

## 🧾 License

This project is for educational and experimental use.

---

## 👤 Author

**Shradha Bhandari**
Creative AI Developer | Future Innovator

