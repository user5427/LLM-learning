# Lecture 13: Agents and agentic work

It can search the web, files.
Write code, execute code, find errors and fix them.

It has a **loop** in this process.

Observe -> Reason -> Act -> Get feedback -> Decide[Continue, Stop] -> Observe -> ...


## Whats an agent?
Multiresults,
Goal oriented,
Autonomous,


1. LLM brain
2. Tools (APIs, code execution, web search, file system)
3. Memory (short term, long term) - it sits in the context window, or in RAG
4. Feedback loop/Orchestration logic (observe, reason, act, get feedback, decide)

Run -> correct itself -> run again -> correct itself -> run again -> ...

### Short term memory
It is the context window. It is the information that the model has access to at any given moment. 

**Compacting** - sumup the chat history for next interactions

### Long term memory

`AGENTS.md`
`CLAUDE.md`

user profile, episodes, chat history

memory can help but it can introduce noise, errors, privacy issues

## How to build an agent?

Infrastructure - API, access
Tool definition
Prompt engineering
State management - agent understands and reports state
Error handling - agent can handle errors and recover from them
Evaluation and safety - evaluate the agent's performance and ensure it behaves safely and ethically

ReAct-style agents - Reasoning + Acting
Plan and execute style agents - Plan a sequence of actions and then execute them
Tool routing workflows - decide which tool to use for a given task
Multi agent systems - multiple agents that can communicate and collaborate with each other
Human in the loop - involve humans in the decision making process of the agent

### ReAct-style agents
Thought -> Action -> Observation -> Thought -> Action -> Observation -> ...
use it when there is unknown number of steps

### Plan and execute style agents
Plan -> Action -> Observation -> Plan -> Action -> Observation -> ...

Decomposible subtasks, lower total LLM calls, clean seperation
Britle to unexpected states, planning overheads

### Tool routing workflows
search/code/data chains

Router LLM clasifies the query and routes it to the appropriate tool

### Multi agent systems
Hierarchical
Peer to peer
Blackboard

Agent definitions
Communication protocols

### Human in the loop
Intervention types: approval, steering, escalation



## Things to keep in mind
Tools have to be explicit
Rate limits
Step limits
Permissions
Whitelisting
Approval gates
Sandboxing

x. Make state visible
x. Separate planning from acting - The planner can be stronger than executer
x. Verifier - use another model
x. Verification - add checks like json schema, etc.

1. Tools explicit
2. Constrains
3. Simple architecture
4. Make state visible
5. Separate planning from acting
6. verification



## Failures
Hallucinations
Bad planning
Tool misuse
Infinite loops
context overload
Goal drift
Overconfidence
Safety violations


### Why evaluation is harder to measure

Errors compound, side effects, non deterministic, qrong process, right answer.

What to evaluate?
Efficiency, price, speed, correctness, safety, ethical considerations, user satisfaction, interpretability

- steps
- tool calls
- cost
- tokens
- latency

## Ethical and practical considerations

HIGH Privacy and data exposure - can execute commands, drop database, etc.
HIGH prompt injection - jailbreaking, jailbreaking 2.0
MEDIUm lack of accountability - who is responsible for the actions of the agent?
LOW cost and environmental impact - running agents can be expensive and have a significant environmental impact


Use agents selectively
Know the failure modes
Evaluate beyond final answer
Know that it will make mistakes



## OpenClaw - for local agents
Or hostinger VPS deployment

## Best practices

start small, monitor everything, handle failures, think of security