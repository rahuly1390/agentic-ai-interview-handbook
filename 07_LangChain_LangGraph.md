# 🧠 LangChain + LangGraph – Interview Cheat Sheet

> High-yield revision for Agentic AI interviews

---

# 🔷 1. LangChain (What it is?)

LangChain = Framework to build LLM applications using:
- Chains
- Agents
- Tools
- RAG pipelines
- Memory

---

# 🔹 Core Components

## 1. PromptTemplate
```python
from langchain.prompts import PromptTemplate
```

Used to structure prompts.

---

## 2. LLM Wrapper
```python
from langchain_openai import ChatOpenAI
```

---

## 3. Chains
Sequence of LLM calls.

```python
chain = prompt | llm
```

---

## 4. LCEL (VERY IMPORTANT)

LangChain Expression Language

```python
chain = prompt | model | output_parser
```

✔ Modern LangChain style  
✔ Replaces old chain classes  

---

## 5. Agents

Agents = LLM decides actions dynamically

- tool calling
- reasoning loop
- decision making

---

## 6. Tools

External functions

```python
@tool
def search(query: str):
    return result
```

---

## 7. Memory

Stores conversation context

Types:
- Buffer Memory
- Summary Memory

---

## 8. RAG

```
User → Retriever → LLM → Answer
```

---

# 🔷 2. LangGraph (What it is?)

LangGraph = **State machine for LLM workflows**

✔ Replaces simple agent loops  
✔ Supports multi-step + multi-agent systems  
✔ Deterministic + controllable flows  

---

# 🔹 Core Concepts

## 1. State

Shared memory across nodes

```python
class State(TypedDict):
    messages: list
```

---

## 2. Nodes

Functions (LLM / tools)

```python
def agent(state):
    return state
```

---

## 3. Edges

Flow between nodes

```
Agent → Tool → Agent → End
```

---

## 4. Conditional Edges

Dynamic routing

```python
if condition:
    go_to("tool")
```

---

## 5. Graph Execution

```python
graph.invoke(state)
```

---

# 🔹 LangGraph vs LangChain

| Feature | LangChain | LangGraph |
|--------|----------|------------|
| Structure | Linear | Graph |
| Control | Low | High |
| Multi-agent | Limited | Native |
| State management | Weak | Strong |
| Production use | Medium | High |

---

# 🔥 Key Interview Insight

👉 LangChain = orchestration  
👉 LangGraph = control system for agents  

---

# 🔥 Agent Flow Example

```
User
 ↓
Agent Node
 ↓
Tool Node
 ↓
Decision Node
 ↓
Final Answer
```

---

# 🚀 Where used in Agentic AI

- Multi-agent systems
- Tool-using agents
- ReAct loops
- RAG pipelines
- Autonomous workflows
