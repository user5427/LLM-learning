# Evaluating LLMs

- Performance mesurement
- Quality Assurance
- Bias Detection

Types of Evaluation Methods:

## Intrinsic vs Extrinsic Evaluation
- Intrinsic: some specific tests, performance on task
- Extrinsic: like evaluating the whole application

### Intrinsic Evaluation
Basically evaluating the model itself, its performance on specific tasks.

+ **Perplexity** 
+ **BLEU** (Bilingual Evaluation Understudy) 
+ **ROUGE** (Recall-Oriented Understudy for Gisting Evaluation)
+ **METEOR** (Metric for Evaluation of Translation with Explicit ORdering)

embeding - vector representation of text, its meaningful for tasks like semantic search, clustering, etc.

#### Perplexity
Predicting the next word in a sequence. The lower the perplexity, the better the model is at predicting the next word.

#### BLEU
It matches the sequences of N-grams (words, or combinations of words) between the generated text and reference text. It measures precision.

### Extrinsic Evaluation
Measures how the model if performing in real world applications. 

* **Task performance**
* **A/B testing**
* **Human evaluation**

#### Human Evaluation
Experts review, crowdsource, user studies or feedback, qualitative analysis, etc.


## LLM Benchmarks
Evaluate how LLM behaves.

We have coding, questions, translation tests, etc.
Some kind of metrics, BLEU, ROUGE, etc.
Leaderboards, etc.

There are **various benchmarks** for evaluating LLMs, such as:
- GLUE (General Language Understanding Evaluation) - diverse NLP tasks (text classification, question answering, etc.)
- SuperGLUE - more complex tasks
- HellaSwag - how LLM is completing the sentence
- TruthfulQA - how truthful the model is
- MMLU (Massive Multitask Language Understanding) - multitask performance
- HUmanity's last exam - advanced phd level questions.


LLMs can evaluate other smaller or newer LLMs.

## Model comparison
- Tokens per second
- Latency
- Various benchmarks

# Model variety

## Google based models

Theres Gemini 3 Pro, Gemini 3 Flash,
Gemini Audio, Lyria, Gemma.

- Gemini 3 Pro: general purpose, code generation, reasoning, etc.
- Gemini 3 Flash: faster, good enough performance.
- Gemini Flash-Lite - even faster.


Vertex AI:
- AutoML
- Custom training
- Model Garden
- Generative AI
- Vertex AI agent builder
- Contact center AI

## LLaMA (Meta)
- LLaMA: 7B, 13B, 70B parameters

LLama 4 - most advanced right now. Mixture of experts.

Open source, can be fine-tuned, etc.

# Models with large token count
typically 100 000 to 200 000 tokens because larger context windows is slower and more memory intensive.

Good for legal document, codebase summarization, etc.

# Specialized LLMs
Designed for specific purpose (legal, medical, programming assistants, etc.)

* Meditron - medical LLM
* FinGPT - financial LLM
* LegalBERT - legal LLM

# Hugging Face
- For open source models, datasets, etc.
- It has spaces for running models.

**Hugging Face API** - you can use it to access various models, including LLaMA, etc.

# Mixure of Experts
- Combine multiple models, each specialized in a specific area, to create a more powerful and versatile system.

Activates only the relevant model for a given task, improving efficiency and performance, less memory usage, etc.

Input -> Router -> [`Models`]* -> Output

Two types:
* Dense MoE - all experts are active, but only a subset of them contribute to the output.
* Sparse MoE - only a few experts are active for each input, which can significantly reduce computational cost.

Not only expers are trained, but also the router, which learns to route inputs to the appropriate experts.

Benefits:
- Handling complex data
- Improved performance
- Efficiency

Challenges:
- Training complexity
- More compute for training
- Scalable algorithms
- Not clear how gating function should work, etc.
- Image understanding problems.

## Mixtral - 8x7B
8 experts, each with 7B parameters, total 56B parameters, but only 7B active at a time.

## DeepSeekMoE - 