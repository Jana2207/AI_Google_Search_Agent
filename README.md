# 🤖🔍 AI Google Search Agent

## 📌 Project Overview

The **AI Google Search Agent** project demonstrates how an AI agent can **autonomously plan and execute internet searches** to retrieve relevant, up-to-date information for users. By leveraging the **React (Reasoning + Acting)** pattern and a Large Language Model (LLM), this agent can intelligently break down complex user queries into manageable steps, use tools like web search and weather APIs, and combine results to deliver clear, useful answers.

---

## 🎯 Project Aim

- ✅ **Streamline complex, multi-step queries**  
- ✅ **Reduce user effort in information retrieval**  
- ✅ **Showcase autonomous web search with real-time reasoning**  
- ✅ **Demonstrate multi-tool orchestration (search + custom APIs)**

---

## ⚙️ How It Works

The agent uses the [LangChain](https://python.langchain.com/) framework with the **React** design pattern, which enables the agent to:
- **Think step-by-step**
- **Choose the right tool**
- **Act, observe, and reason again**
- **Deliver a final answer with clear traceability**

---

## 🗂️ Project Structure

### 1️⃣ **Basic AI Search Agent**

**Key Steps:**
1. **Environment Setup**
   - Install libraries:  
     ```bash
     pip install langchain openai langchain-community duckduckgo-search
     ```
   - Provide your OpenAI API key.

2. **Core Components**
   - Create the `DuckDuckGoSearchRun` search tool.
   - Instantiate `ChatOpenAI` for LLM-based reasoning.

3. **Agent Construction**
   - Import `create_react_agent` and `AgentExecutor`.
   - Pull the `hwchase17/react` prompt from the LangChain Hub.
   - Build the agent with the search tool and React prompt.

4. **Execution**
   - Initialize `AgentExecutor` with `verbose=True` to see internal thoughts.
   - Run the agent with a query:  
     ```
     What are the three ways to reach Goa from Delhi?
     ```
   - Observe the loop: `Thought ➜ Action ➜ Observation ➜ Final Answer`.

---

### 2️⃣ **Improved Agent with Custom Tool**

**Extend functionality with an additional tool:**
- **Custom Weather Tool**
  - Define a Python function `get_weather_data(city)`.
  - Use an external weather API (e.g., Weatherstack).
  - Register the function as a LangChain `@tool`.

- **Integrate the new tool**
  - Add to agent’s tools list.
  - Update the `AgentExecutor`.

- **Run a multi-step query**
  - Example:  
    ```
    Find the capital of Madhya Pradesh then find its current weather condition.
    ```
  - The agent:
    1. Uses search to find the capital.
    2. Uses weather tool for live weather.
    3. Returns a combined answer with full reasoning trace.

---

## 🧩 Key Features

✔️ **Goal-driven execution**  
✔️ **Dynamic planning & breakdown**  
✔️ **Tool awareness & flexible usage**  
✔️ **Memory of previous steps**  
✔️ **Transparent ‘thought trace’**  
✔️ **Adaptable to tool failures**

---

## 🚀 Getting Started

1. **Clone this repo**
   ```bash
   git clone https://github.com/your-username/ai-google-search-agent.git
   cd ai-google-search-agent
