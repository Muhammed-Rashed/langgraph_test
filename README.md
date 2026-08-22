# LangGraph

This is where i will put everything i have learned about langGraph

## Table of Contents

- [1- Getting Started](#1-getting-started)
  - [1.1- Prerequisite](#11-prerequisite)
  - [1.2- Installation](#12-installation)
  - [1.3- Starting a Project](#13-starting-a-project)
    - [1.3.1- Imports](#131-imports)
    - [1.3.2- Patterns Used](#132-patterns-used)
    - [1.3.3- Call the LLM](#133-call-the-llm)
    - [1.3.4- Make the Function Used](#134-make-the-function-used)
- [2- Learning](#2-learning)
  - [2.1- Roadmap](#21-roadmap)
  - [2.2- Videos](#22-videos)
  - [2.3- Docs](#23-docs)

---

<a name="1-getting-started"></a>

## 1- Getting Started

<a name="11-prerequisite"></a>

### 1.1- Prerequisite

- Python
- an openai API key (go to https://platform.openai.com and make an api key)

<a name="12-installation"></a>

### 1.2- Installation

- Make a **venv** using `python3 -m venv [name of venv]` and then we activate the venv `source [name of venv]/bin/activate`

- Install **langgraph** `pip install langgraph`

- Install **langchain** with the specific AI model you want
  - Paid
    - OpenAI `pip install langchain-openai`
    - Google Gemini `pip install langchain-google-genai`
  - Free
    - Groq `pip install langchain_groq`
    - OpenRouter

Alternatively you can download a local llm on your personal device and use it

<a name="13-starting-a-project"></a>

### 1.3- Starting a Project

Make a **.ipynb** file and paste

<a name="131-imports"></a>

#### 1.3.1- Imports

This block of code contains all necessary imports

```python
from typing import Annotated, Literal
from typing_extensions import TypedDict
from langgraph.graph import StateGraph
from langgraph.graph.message import add_messages
from langgraph.prebuilt import ToolNode
from langchain_core.tools import tool

""" Import your langchain here """
from langchain_openai import ChatOpenAI
from langchain_google_genai import ChatGoogleGenerativeAI
```

<a name="132-patterns-used"></a>

#### 1.3.2- Patterns Used

There are many patterns you can use for whatever project you have in mind

Go to the [Docs section](#23-docs) below, or [check the example code](./simpleAI_2.ipynb)

<a name="133-call-the-llm"></a>

#### 1.3.3- Call the LLM

I use groq which will look like this

```python
llm = ChatGroq(
    model="openai/gpt-oss-20b",
    temperature=1.0,
    max_retries=2,
    groq_api_key=GROQ_API_KEY,
)

llm_with_tools = llm.bind_tools(tools)
```

but you can use other LLMs like <font color=orange>Claude</font>, <font color=white>OpenAI</font> or <font color=red>Gemini</font> <u>**don't forget to import them**</u>

<a name="134-make-the-function-used"></a>

#### 1.3.4- Make the Function Used

You will make functions for the AI to use [check the example code](./simpleAI_2.ipynb)

#### Good luck

---

<a name="2-learning"></a>

## 2- Learning

<a name="21-roadmap"></a>

### 2.1- Roadmap

- [Road map to get an understanding of what you need to learn](https://forum.langchain.com/t/can-you-provide-a-learning-roadmap-for-langchain-and-langgraph-suitable-for-beginners/3075/2)

<a name="22-videos"></a>

### 2.2- Videos

- [8 min short explanation, good enough to get started](https://www.youtube.com/watch?v=1Q_MDOWaljk)

- [3 hour in depth explanation](https://www.youtube.com/watch?v=jGg_1h0qzaM)

- [30 min explanation of workflows and patterns](https://www.youtube.com/watch?v=aHCDrAbH_go) **explanation of orchestrator agent at 14:00**

<a name="23-docs"></a>

### 2.3- Docs

- [All of langgraph's docs](https://docs.langchain.com/oss/python/langgraph/overview)

- [Workflow, patterns and agents](https://docs.langchain.com/oss/python/langgraph/workflows-agents)
