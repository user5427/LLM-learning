# Prompt types

**System prompts:**
before your text there is a initial prompt (the LLM is not starting fresh). It sets context, tone, interaction, instructions.
**Normal prompt:**
the user provided query.


Initial prompt:
* Tells to be a helpful assistant, a programmer, a teacher...
* It tells the date and time.
* Extra instructions for the model to behave, not to reveal the prompt.

# Iterative prompt design
Create a prompt, test it, and then refine it based on the output. Repeat this process until you get the desired result.

You can ask LLM to improve the prompt itself, that is generate the question.

## Incremental prompt growing
- Start with a simple prompt
- Analyze the output and identify what is missing or could be improved.
- Add more details or constraints to the prompt to guide the model towards the desired output.

**Not efficient** - you are burning tokens on the iterations, better to ask for help in the prompt design itself.


# Spelling errors

- Pretrained knowledge - knows the rights and wrongs
- Contextual analysis - helpts to understand the meaning of the sentence
- Error tolerance - designed to tolerate and correct spelling errors, epsecially from context.

** How much errors can LLMs handle?**

Same as humans. Depends on type of errors, context, typos, phonetic errors, etc.


# Repeated action processing with LLMs

## Batch processing
- Process multiple inputs in a single request.
- More efficient than sending individual requests for each input, less tokens used.

Though it tends to forget huge tasks or instructions like humans.

## Optimization
Enchancing efficiency by optimizing the prompt design, reducing unnecessary tasks.

### Usage
- Data processing: cleaning, transforming, and analyzing data.
- Sentiment analysis: analyzing customer feedback, social media posts, etc.
- Translating text: translating documents, websites, etc.
- Extracting information: extracting specific information from text, such as names, dates, etc.
- Generating content: generating articles, summaries, etc.
- Correcting grammar and spelling: correcting errors in text.

### Why:
- Input costs, but its cheapere, output is more expensive
- Batching is useful for this.


# Machine translation

Attention mechanism - allows the model to focus on specific parts of the input sequence when generating the output, which is crucial for translation tasks.

Transformers in machine translation - allows you to do the translation and change the sequence of the words, which is important for languages with different word order.

Transformers:
- encoder-decoder architecture: the encoder processes the input sequence and generates a representation, which is then used by the decoder to generate the output sequence.
- self-attention mechanism: allows the model to weigh the importance of different words in the input sequence when generating the output, which is crucial for understanding context and producing accurate translations.
- positional encoding: allows the model to understand the order of words in the input sequence, which is important for languages with different word order.

"šuo ėda maistą"
"Maistą ėda šuo"

Same meaning, positional encoding fixes this issue.

## Encoding layer
- Data gets encoded into a format that the model can understand, typically a vector representation.

## Decoding layer
- The model generates the output sequence based on the encoded representation of the input and passes the output through the decoding again to itself to be output aware.


### Fixes
- Ambiguity reduced
- Context understanding improved
- Syntax and grammar handled better
- Resource contraints addressed - not all subjects have the same amount of data, so the model can focus on the most relevant information.
- Evaluation metrics improved


# LLM API
- Generate the API key and make requests to the API endpoint.

API providers:
- OpenAI API
- Google Gemini API
- Anthropic API

Deepinfra API - provides a lot of open source models.

Groq API - provde open source models with fast response times.

LM Studio - localy, chat, or server

gpt4all - localy


# API rate liiting and cost optimization
- Control the use, prevent abuse, manage reliable performance
- `429` if too many requests in a short period of time

Deepinfra limits to 200 concurrent requests per model
OpenAI limits requests per minute, per day and tokens per minute, per day and images per day.


** Cost optimization:**
- For simple requests, do not use the most expensive model, use a cheaper one.

