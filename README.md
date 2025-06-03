# 🧠 EvoAgentX: Self-Evolving AI Agent Framework

<div align="center">
  <img src="./assets/EAXLoGo.svg" alt="EvoAgentX Logo" width="50%">
</div>

## 🚀 Overview

**EvoAgentX** is a self-evolving ecosystem for building, evaluating, and optimizing AI agent workflows. It features:

- Automatic workflow generation from goals
- Configurable LLM backend (e.g., GPT-4o)
- Evolution algorithms for multi-agent optimization
- Integration-ready for research or production use

## 📦 Installation

### Quick Start (pip)

```bash
pip install git+https://github.com/CodeWithHarshAI/EvoAgentX.git
```

### Local Setup (Recommended for Devs)

```bash
git clone https://github.com/CodeWithHarshAI/EvoAgentX.git
cd EvoAgentX
conda create -n evoagentx python=3.10
conda activate evoagentx
pip install -r requirements.txt
```

## 🔐 API Key Setup

### Method 1: Environment Variable

```bash
export OPENAI_API_KEY=your-key-here
```

### Method 2: .env File

Create a `.env` file:

```env
OPENAI_API_KEY=your-key-here
```

## ⚙️ Usage Example

```python
from evoagentx.models import OpenAILLMConfig, OpenAILLM
from evoagentx.workflow import WorkFlowGenerator, WorkFlow
from evoagentx.agents import AgentManager
import os

config = OpenAILLMConfig(model="gpt-4o", openai_key=os.getenv("OPENAI_API_KEY"))
llm = OpenAILLM(config=config)

goal = "Build a to-do app in Python"
workflow_graph = WorkFlowGenerator(llm=llm).generate_workflow(goal)
agent_manager = AgentManager()
agent_manager.add_agents_from_workflow(workflow_graph, llm_config=config)

workflow = WorkFlow(graph=workflow_graph, agent_manager=agent_manager, llm=llm)
result = workflow.execute()
print(result)
```

## 📊 Evolution Algorithms Included

- TextGrad
- AFlow
- MIPRO

Benchmark tasks include:
- Multi-hop QA (HotPotQA)
- Code Generation (MBPP)
- Reasoning (MATH)

## 📂 File Structure

```
.
├── ai_Self-Evolving_agent.py    # Main script
├── requirements.txt             # Dependencies
├── assets/                      # Visual assets and logos
└── README.md                    # Project documentation
```

## 📚 License

This project is licensed under the MIT License.

---

Built with ❤️ by **Harsh**  
[GitHub: CodeWithHarshAI](https://github.com/CodeWithHarshAI)
