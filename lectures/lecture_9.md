# LLM Security

Jailbraking - tricking LLM into doing something it was not designed for.

## Types of attacks

- Passive injection
- Active injection

### Active injection:

When you insert some extra prompt into the input.

### Passive injection:

When you insert some extra prompt into the training data. For example, you can insert some malicious code into the training data, and then when the model is trained on that data, it will learn to generate that code.

## Threats:

Information gathering
Fraud
Intrusion
Malware
Manipulate context
DDoS

## Attacks

Black box - you idk what happens in model
White box - you know what happens in model

- Token manipulation | Black box
- Gradient based attack | White box
- Jailbreaking | Black box
- Human red-teaming | Black box

### Red teaming

Collect all jailbreaks, test them on your model, and then fix the model to prevent those jailbreaks.

## Risks

- Data breaches
- Misinformation
- Model exploitation

### Prompt injection

- Direct prompt injection - tell LLM directly
- Indirect prompt injection - hide the injection in website, the LLM reads website and goes crazy

### Unauthorized code execution

- System compromise
- Data theft
- Mlaware installation
- Network breaches
- Operational disruption

## How to defend against these attacks?

- Robust training techniques - trained to handle these things
- Testing and Evaluation Regulary
- Continous monitoring

## Censored and uncensored LLMs

Censored LLMs - ChatGPT, Gemini, others
Uncensored LLMs - does not have any contraints

Base model -> fine tuned to be censored -> fine tune to uncensor -> model that gets a little crazy.

### Uncensored LLMs

- For research
- Content creationg
- Too see how it responds

Llama 3.2 - uncensored LLM, though it still might refuse
Llama 3 8b - uncensored LLM, tells how to make a bomb

#### Prompt level jailbreaking

- Franubg reqyests as benefucial
- Convincig through ego appeals
- Using social engineering techniques
- Stearing the conversation towards a specific topic
- Leading the model through questions

One-shot - giving an example and the model happily does it.

#### DAN - do anything now

was fun to play around
threatening sometimes works? but not always, and it is not ethical.

#### Initial Prompt stealing

When you steal the initial prompt, you can bypass some of the restrictions that the model has.

## LLM Routing

Trying to see what kind of prompts need to be sent to which model. Because
sending expensive model for simple task is not efficient, and sending simple
model for complex task is not effective.

## LLM Inference

When LLM is answering the question.

- Response time - time to first token.
- Scalability - traffic through model
- Cost
- Accuracy
- Energy consumption

### Transformers library

- temperature, context window size, etc.

### vLLM

open source for high performance
handles the attention better
the longer prompt, the more RAM, vLLM has paged attention to handle this better

## Impact on environment and employment

- Energy crisis, training most energy demanding.

CPU, GPU, TPU
\/
Software
\/
Use

1000Twh in 2026, 2500Twh by 2030 consumed

So greendata centers are solution.

## Impact on employment

New roles, new jobs, new data analysis

## Regulations on AI

EU AI act:

1. unacceptable risk - government run social scoring like in China
2. high risk - cv scanning, medical reviews, lots of requirements
3. 
4. chatbots

If ai car slams into a person, whos responsible? insurance

## Emerging research direcitons

Voice models are still trash

Multimodal models, audio spectrogram/images straight into the model through image vector representation.

- Speech LLM systems

- Full-duplex speech LLM, generates spectrograms that get converted to sound

- Specialized nodeks, lightweight models, mixture of experts, specialized hardware, analogue computing.
