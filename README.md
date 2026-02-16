# LangGraph Basics 🦜🕸️

A comprehensive collection of design patterns and workflows implemented using **LangGraph**, **LangChain**, and **Groq**. This repository serves as a guide for building stateful, multi-agent systems ranging from simple linear chains to complex iterative loops.

## 🚀 Overview

This repository explores the fundamental building blocks of agentic workflows. By leveraging LangGraph, these scripts move beyond simple "prompt-in, response-out" interactions to create systems with memory, reasoning, and self-correction capabilities.

## 📂 Repository Structure

The project is organized into seven key modules, each focusing on a specific LangGraph pattern:

### 1. Iterative Workflow (Self-Correction)
* **File:** `7_post.ipynb`
* **Description:** A "Critique-and-Refine" loop that generates, evaluates, and optimizes tweets.
* **Key Features:** Uses a **Critic Node** to provide structured feedback and an **Optimizer Node** to punch up the content until it meets quality standards.

### 2. Parallel Workflows
* **Description:** Demonstrates "fan-out" and "fan-in" patterns where multiple nodes execute tasks simultaneously to save time and aggregate diverse perspectives.

### 3. Conditional Routing
* **Description:** Implements dynamic decision-making using `add_conditional_edges`. The graph decides the next step (e.g., END or OPTIMIZE) based on the state's evaluation results.

### 4. Basic Chains
* **Description:** Introduction to `StateGraph` and linear node-to-node transitions.

### 5. Multi-Agent Collaboration
* **Description:** Specialized agents (e.g., Researcher, Writer) passing the state to one another to complete complex tasks.

## 🛠️ Tech Stack

* **Orchestration:** [LangGraph](https://github.com/langchain-ai/langgraph)
* **LLM Provider:** [Groq](https://groq.com/) (Llama 3.3 70B)
* **Schemas:** [Pydantic](https://docs.pydantic.dev/) for structured output and evaluation
* **State Management:** `TypedDict` with `Annotated` list reducers for history tracking

## 📋 Prerequisites

1.  **Groq API Key**: Set your key in the environment variables:
    ```bash
    export GROQ_API_KEY='your_api_key_here'
    ```
2.  **Install Dependencies**:
    ```bash
    pip install langgraph langchain-groq pydantic
    ```

## ⚙️ Core Logic: The Iterative Loop

The primary example (`7_post.ipynb`) follows this stateful logic:
1.  **Generate**: Drafts a tweet based on a topic.
2.  **Evaluate**: A "ruthless critic" checks for humor and character limits.
3.  **Route**: If approved, the process ends. If rejected, it routes to optimization.
4.  **Optimize**: Refines the tweet based on feedback and loops back to evaluation.

---

**Would you like me to help you create a `requirements.txt` file to go along with this repository?**
