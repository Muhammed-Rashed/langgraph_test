# LangGraph

This is where i will put everything i have learned about langGraph

---

## 1- getting started

### 1.1- prerequisite

- Python
- an openai API key (go to https://platform.openai.com and make an api key)

### 1.2- installation

- Make a **venv** using `python3 -m venu [name of venv]` and then we activate the venv `source [name of venv]/bin/activate`

- Install **langgraph** `pip install langgraph`

- Install **langchain** with the specific AI model you want
  - Paid
    - OpenAI `pip install langchain-openai`
    - Google Gemini `pip install langchain-google-genai`

  - Free
    - Groq
    - OpenRouter

Alternatively you can download a local llm in your personal device and use it

### 1.3- make your first project

Make a **.ipynb** file and paset this block of code

```python
from typing import Annotated, Literal
from typing_extensions import TypedDict
from langgraph.graph import StateGraph
from langgraph.graph.message import add_messages
from langgraph.prebuilt import ToolNode
from langchain_core.tools import tool

""" Import you langchain here """
from langchain_openai import ChatOpenAI
from langchain_google_genai import ChatGoogleGenerativeAI
```

this block of code contains all necessary imports

#### Good luck

---

## 2- Learning

### 2.1 - RoadMap

- [Road map to get an understanding of what you need to learn](https://forum.langchain.com/t/can-you-provide-a-learning-roadmap-for-langchain-and-langgraph-suitable-for-beginners/3075/2)

### 2.2- Videos

- [8 min short explanation good enough to get started](https://www.youtube.com/watch?v=1Q_MDOWaljk)

- [3 hour in depth explanation](https://www.youtube.com/watch?v=jGg_1h0qzaM)

- [30 min explanation of workflows and patterns](https://www.youtube.com/watch?v=aHCDrAbH_go) **explanation of orchestrator agent at 14:00**

### 2.3- Docs

- [workflow, patterns and agents](https://docs.langchain.com/oss/python/langgraph/workflows-agents)

---
