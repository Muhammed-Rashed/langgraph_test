# LangGraph

This is where i will put everything i have learned about langGraph

---

## 1- getting started

### 1.1- prerequisite

- Python
- an openai API key (go to https://platform.openai.com and make an api key)

### 1.2- installation

- Make a **venv** using `python3 -m venu [name of venv]` and then we activate the venv `source [name of venv]/bin/activate`

- Use the following commands to install **langgraph** and **langchain** `pip install langgraph` and `pip install langchain-openai`

### 1.3- make your first project

Make a **.ipynb** file and pase this block of code

```python
from typing import Annotated, Literal
from typing_extensions import TypedDict
from langgraph.graph import StateGraph
from langgraph.graph.message import add_messages
from langgraph.prebuilt import ToolNode
from langchain_core.tools import tool
from langchain_openai import ChatOpenAI
```

this block of code contains all necessary imports

#### Note to self

Since gpt and Claude are paid you can use free versions of gemini or local llms if you need to

#### Good luck

---

## 2- Learning

### 2.1- Videos

- https://www.youtube.com/watch?v=1Q_MDOWaljk <font color="red"> 8 min short explanation good enough to get started </font>

- https://www.youtube.com/watch?v=jGg_1h0qzaM <font color="red"> 3 hour in depth explanation </font>

- https://www.youtube.com/watch?v=aHCDrAbH_go <font color="red"> 30 min explanation of workflows and patterns **explanation of orchestrator agent at 14:00**</font>

### 2.2- Docs

- https://docs.langchain.com/oss/python/langgraph/workflows-agents <font color="green"> Workflows and agents </font>

- [workflow](https://mirror-feeling-d80.notion.site/Workflow-And-Agents-17e808527b1780d792a0d934ce62bee6?pvs=143) <font color="green"> Workflows and agents </font>

## 3- Working Examples with state diagrams

### 3.1- Simple AIs

- <font size="4">**simpleAI_1** <sub>Weather bot</sub></font>
  Chat bot that tells you the weather.

```mermaid
stateDiagram-v2
  direction TB
  message --> start
  start --> chat_prompt
  chat_prompt --> conditional_edge
  conditional_edge --> Tool
  Tool --> chat_prompt
  conditional_edge --> end
  message: message
  chat_prompt: chat_prompt
  conditional_edge: conditional_edge
```

<hr style="border-top: dotted 4px; background: transparent" />

- <font size="4">**simpleAI_2** <sub>Travel planner</sub></font>
  Tells you if the place you are going is good or not
