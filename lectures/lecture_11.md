# Frameworks

## What are LLM frameworks?

Allows to do things easier and faster. Basically hide all the complexities

### LlamaIndex

A little outdated, open source, helps to develop LLM applications.
Python and TypeScript based.

Data - various formats, pdfs, text, APIs, databases
Embeddings - converting text to venctor
LLMs
Vectors
Evals

\/

Q&A
Inteligent chatbots
Agents - continous loop of tool usage until the goal is achieved
Semantic search
Structured extraction


Flexible data, memory management, inteligent data structures, context window limitations and optimizations

**Use Cases**
QA
Sumup
Data analysis
Knowledge management
retrieval of data
...

Normal mode or stram mode

Tool caling with `FuncitonTool.from_default` tool making.

You can use local models and also limit context window.

FunctionAgent, give tools and system_prompt, then ask for response, whatever...

`Context` from the continous chat, it knows what happened before.

## LangChain

LLMs, Prompts, Memory, Chains, Agents, Tools

**Benefits:**
Comunity, Scalable, Debugable, Extendable, Composable

## Semantic Kernel

created by Microsoft, presented as SDK

C#, Python, Java languages

Enables to create plugins, strongly typed


- MS product so integrates with Azure and OpenAI stuff.
- Embedings and vector operations
- Skill systems - MCP - Memory, Context, Planner
    - `A skill is description of actions (prompt + code) to achieve some kind of goal.`
- Planning capabilities

## Haystack

open-source, created by a company.


Modular design
Components
Flexible configuration

Components:
- Retrievers - find, search (semantic or old fashion) data
- Readers & Generators
- Generator

Prompt
\/
Generator
\/
Answer

Prompt
\/
Retriever <-> External DB
\/
Generator
\/
Answer

Prompt
\/
Retriever <-> External DB
\/
Generator
\/
Context | Start-end positions of answer

## LitellM

Simple, nice, creates one unified API to access models, supports streaming

Everything is the same no matter the provider (Google, OpenAI, etc...)

It can do load balancing across multiple deployments.
It can do routing strategies (based on question difficulty)
It does retries, fallbacks
You can have custom models

Flexible, formating, cost saving, Open WebUI - like personal chatGPT.

### Batching
Without it each request is processed at a time.
Static batching - process when the bucket is full
Dynamic batching - when full or time passed, run
Continous batching - Keep adding new as old get processed.

## vLLM

Library for inference, for running LLMs locally. So far we have been using
`hugging face lib` to run locally. This lib instead gets models from hf and
servers them via API.

its efficient, paged attention, better memory and compute utilization

- LoRA adapters - takes 1000x1000 matrix and converts to 1000 x n * n x 1000 matrix multiplication to reduce parameter count, or for fine tuning, its like 100MB addon layer/adapter
- Flash attention integration
- Quantization support
- KV caching support - key valua pairs

### vLLM LoRA adapters

When we generate request we define the adapter path

### vLLM attention backend

## Medusa

Very fast
Close to 3x faster than regular model

## LM Studio

academic, prototyping, healtcare, whatever

# Advantages of frameworks

Faster, Consistent, Security, Testing, Cost efficient

# Challanges of frameworks  

more time to learn it, overhead, limited flex, dependency, issues on integration, versioning......

## Balance between inovation and stability


Chatbots and virtual assitance
RAG
LLM-Driven Content Generation

Fine tuning is costly, its great only for fast speeds.

## Hybrid approaches - mixing models, but managing becomes difficult

## Evaluating performance of LLM frameworks

Future trends - better efficiency, integration