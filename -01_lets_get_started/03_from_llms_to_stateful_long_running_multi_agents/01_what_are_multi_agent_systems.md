# From LLMs to Stateful Long-Running Multi-Agent Systems

## 🌍 The Rise of Agentic AI in 2025
2025 is widely considered the **year of Agentic AI**.  
Enterprises are beginning to **develop and deploy AI agents** to automate workflows.  

Think of this as the **evolution of SaaS**:
- SaaS: Humans use software tools.  
- Agentic AI: Software (via agents) performs tasks autonomously.  

But **agentic AI goes beyond SaaS**:  
It adds **reasoning, adaptability, and autonomy** rather than just providing tools.

---

## What Are AI Agents?
**Definition**  
> "AI agents are LLMs operating in an iterative loop, using tools and environmental feedback to autonomously plan and act toward a goal, often with human checkpoints for alignment."

### 🔑 Key Components
- **LLMs** → Core intelligence.  
- **Iterative Loop** → Think → Act → Observe.  
- **Tools** → APIs/functions to interact with the world.  
- **Environmental Feedback** → Tool results guide the next step.  
- **Autonomous Planning** → No fixed script, adaptive.  
- **Human Checkpoints** → Oversight at critical stages.  

**Bottom line:** Agents are **adaptive, goal-driven systems**, not static workflows.

---

## The Role of LLM APIs
**LLM APIs** democratized access to advanced models (OpenAI, Anthropic, Gemini).  

### ✅ Capabilities
- Reason & generate text.  
- Invoke tools (via function calls).  
- Handle natural language → structured outputs.  

**Why it matters**: Before APIs, building agents required costly custom models. Now anyone can build intelligent agents quickly.

### Industry Standardization
- Early days: Each provider had unique APIs.  
- 2025: Industry has standardized on **OpenAI Chat Completion API**.  
- Evolution: OpenAI’s **Responses API** (March 2025) is the new superset.

---

## Responses API – Superset of Chat Completions
The **Responses API** is designed for **agentic AI systems**.

### Key Features
- Inherits **Chat Completion API** functionality.  
- Adds **built-in tool support & state management**.  
- Supports **multi-tool interactions** (e.g., search + file retrieval + automation).  
- Native support for **web search, file search, and computer use (CUA)**.  

### 📌 Why It Matters
- Enables **autonomous tool use**.  
- Simplifies **multi-agent orchestration**.  
- Future-proof: OpenAI will phase out the Assistants API by **mid-2026**.  
- Open-source **Agents SDK** complements it for orchestration.  

**Takeaway**: Responses API is the **new foundation** for building agentic AI.

---

## Memory in Agents
Since **LLMs are stateless**, agents rely on two forms of memory:

### Short-Term Memory
- Stored in the **prompt context window**.  
- Includes **recent messages** and interactions.  
- Limited by context length.  

### Long-Term Memory
- Stored in **external databases (e.g., vector stores)**.  
- Retrieved via **tool calls or retrieval pipelines**.  
- Used in **Agentic RAG**: agents reason, plan, and actively fetch data.  

👉 Modern design: Long-term memory is often treated as a **tool call** (e.g., `retrieve_past_interactions`) for agent flexibility.

---

## Multi-Agent Systems

### Role of System Prompts
- Each agent has a **system prompt** defining its **role, tone, and rules**.  
- Examples:  
  - Researcher Agent → "Find data."  
  - Coordinator Agent → "Delegate tasks."  

### Agent Communication
- **Handoffs via tool calls** (one agent invokes another).  
- Alternatives: **memory, queues, events**.  
- Dual role of tools:  
  - **Input** (fetching info).  
  - **Output** (taking actions).  

---

## Standards: Model Context Protocol (MCP)
**MCP = “USB-C for AI”** – a universal standard for tool calling.  

### Architecture
- **MCP Servers** → Expose tools (e.g., `get_weather`).  
- **MCP Clients** → Agents/apps discover and invoke tools dynamically.  

### Benefits
- Dynamic **tool discovery**.  
- Reduces **custom integrations**.  
- Enables scalable, interoperable agents.  

---

## Design Patterns (Anthropic: *Building Effective Agents*)
Anthropic identifies **five core patterns**:

1. **Prompt Chaining** → Sequential LLM calls.  
2. **Routing** → Classify input → direct to correct task/model.  
3. **Parallelization** → Run LLM calls simultaneously.  
4. **Orchestrator–Workers** → Central LLM delegates tasks.  
5. **Evaluator–Optimizer** → Feedback loop between generator & evaluator.  

These can run:  
- **Locally (Python, OpenAI SDK)** → short-term workflows.  
- **Cloud (Kubernetes, Serverless, Kafka)** → long-running, stateful workflows.

---

## 🖥 Local vs Cloud Agent Workflows

| Type | Characteristics | Example | Tools |
|------|----------------|---------|-------|
| **Short-Term** | Ephemeral, no persistence | Python script for trip planning | OpenAI Agents SDK |
| **Long-Term** | Persistent, scalable, reliable | Multi-week project tracking | Kubernetes, Kafka, Redis |

**Rule of Thumb**:  
- Local → ✅ lightweight, experimental tasks.  
- Cloud → ✅ durability, concurrency, uptime.  

---

## Framework Design: Layered vs Unified
Agentic systems vary by **execution style** and **timescale**:

- **Workflows** → Predefined, coded paths.  
- **Agents** → LLMs dynamically plan & act.  
- **Short-Term** → Session-based, ephemeral.  
- **Long-Term** → Persistent, asynchronous, robust.  

### Proposed Layered Architecture
- **Layer 1: Core Agentic Execution**  
  - Lightweight agent loop.  
  - Best for short-term tasks.  
  - Similar to OpenAI Agents SDK.  

- **Layer 2: Durability & Orchestration**  
  - Adds persistence, retries, monitoring.  
  - Powered by cloud infra (FastAPI, Docker, Kafka, Kubernetes).  
  - Needed for long-term multi-agent systems.  

---

## Guiding Principles for Agentic AI
1. **Streamline with Minimal Abstractions**  
   - Direct access to reasoning, tools, outputs.  
   - Transparency → customization.  

2. **Provide Building Blocks, Not Rigid Blueprints**  
   - Flexible foundation, not fixed workflows.  
   - Developers design their own systems.  

3. **Champion Adaptability & Transparency**  
   - Lean, modular, easy to troubleshoot.  
   - Supports rapid iteration.  

4. **Unlock Power Through Simplicity**  
   - “Cosmic Swiss Army knife.”  
   - Simplicity → faster experimentation.  

 **Philosophy: Less is More.**  
Offer raw AI strength with minimal constraints.  

---

# Summary
- **2025 = Agentic AI era.**  
- **LLMs + APIs + tool calling** → foundation of agents.  
- **Responses API** = future standard.  
- **Memory (short vs long)** enables adaptability.  
- **MCP** standardizes tool calling.  
- **Multi-agent design patterns** provide flexible blueprints.  
- **Local = short-term**, **Cloud = long-term stateful workflows**.  
- **Layered architecture** ensures scalability.  
- **Our guiding philosophy**: power through **simplicity, adaptability, and transparency**.
