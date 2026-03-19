# LLM Fine tuning

Model learns to predict the next word in the sentence. After lots of training, it starts to generalize.

With fine-tuning, we train it to answer specific questions, the weights are updated.

## Fine-tuning

Dataset is labeled, while in pre-training it is just raw text. 

If it was not fine-tuned, you would have to write prompts in a very specific way
to get the model to auto-complete the sentence.

### Task-specific examples:

**Prompt**{...}, -> **Response**{...}

### Challenges of fine-tuning
- Overfitting - model performs well on training data but poorly on unseen data, it does not generalize well.
- Difficult to balance new knowledge with existing knowledge - model may forget previously learned information. You tipically **freeze** some layers of the model to prevent this.
- Fine-tuning another fine-tuned model can be more efficient.

### Datasets needed
- With examples and scenarios and expected output.
- 100 billion tokens for fine-tuning is sufficient.

There is retrieval augmentation - generate vector representation of the query, search for similar vectors in the database, and use the retrieved information to generate a response. But its slower for the model to generate a response.

**Examples of fine-tuning datasets:**
- SQuAD - question answering dataset
- CNN/Daily Mail - summarization dataset
- MathQA - math problem-solving dataset

High quality, used everywhere as a benchmark for fine-tuning.

### Data source variation:
- Lexical variation (synonymy)
- Lexical variation (world knowledge)
- Syntactic variation (different sentence structures)
- Multiple sentence reasoning
- Ambiguous

### Variants of fine-tuning:
- Prompting - tailored instructions to guide the model's response.
- RAG - retrieval augmented generation, retrieve relevant information from a database to generate a response.
- Fine-tuning - updating the model's weights based on a labeled dataset.
- Pre-training - training the model on a large corpus of text to learn general language patterns.

#### Continued pre-training
[Common crawl data] Base model -> [give lots of lithuanian text] Base model -> Fine tuning -> We get a model that is good at understanding and generating Lithuanian text.

#### Supervised fine-tuning
These already include moral and ethical guidelines.

**Examples of supervised fine-tuning:**
- Question answering
- Sentiment analysis
- Text summarization
- Instruction following
- Named entity recognition (NER) - identifying and classifying named entities in text (e.g., people, organizations, locations).

#### Reinforcement learning with human feedback (RLHF)
Give several responses to the same prompt, and ask human annotators to rank them. Then use this feedback to train a reward model, which is used to fine-tune the language model.

The reward model is fed by prefer/unprefered text from human feedback. The reward model then trains the aligned model, which is the final model that we use.
There is a lot of human annotation involved, which is expensive and time-consuming.

There is PPO (Proximal Policy Optimization) algorithm and DPO (Direct Preference Optimization) algorithm, which are used to optimize the model based on human feedback.

## Quantization

Lower size, but also lower quality. 32 bits -> 16 bits -> 8 bits -> 4 bits -> 2 bits or even 1 bit.

### Types of quantization:
- Weight quantization - reduce the precision of the model's weights while keeping the activations at full precision.
- Activation quantization - 
- Post-training quantization - train the model at full precision and then quantize it after training.
- Quantization-aware training - during the training process, we are already simulating the effects of quantization

**Benefits of quantization:**
- Saves RAM and storage space.
- Faster inference - less computational resources needed.


- You can make it int 8, removing the decimal part
- you can map the weights from float to int -128 to 127, based on probability

### LLM Inference optimization:
Different quantization techniques use different amounts of resources.

- Linear quantization
- Weighted quantization
- Log quantization

Llama-3.2-3B-instruct-Q5_K_M


Q8 - linear compression, not very efficient
Q6_K - K type, quantization with attention to outliers
Q5_K_M - K type, quantization with attention to outliers, and mixed precision for some layers
Q5_K_S - K type, quantization with attention to outliers, and mixed precision for some layers, and sparse attention
Q4_K_S - ...
Q4_K_M - ...

## LoRA (Low-Rank Adaptation) and QLoRA (Quantized Low-Rank Adaptation)

### LoRA
Allows to do the fine-tuning way faster.

What are lower-rank matrices?
A rank is a number to tell how different rows or columns of a matrix are.


If you have 2048x2048 matrix, you can approximate it with two smaller matrices of size 2048x4 and 4x2048. This way you only need to train 16k parameters instead of 4 million.

A = [[2, 20, 1], [4, 40, 2], [6, 60, 3]] = [[1], [2], [3]] x [2, 20, 30]

### QLoRA
Mix LoRA with quantization.

You can train your model on PC.

## Catastrophic forgetting

When you fine-tune the model and it forgets the base/original information.
The cause of this is the model's weights being updated during fine-tuning, which makes it forget info.

There are mechanisms to mitigate this, such as freezing certain layers, elastic weight consolidation, and regularization techniques.

Sequential learning is when the model learns multiple tasks sequentially, which can lead to catastrophic forgetting. 

## Examples of fine-tuning:
You have a model trained for general medicine and you want to fine-tune it for some specific field, so you do EWC, freeze some layers.

You monitor which parameters are used the most when running through the general medicine dataset, and then you freeze those parameters during fine-tuning for the specific field. This way you prevent the model from forgetting the general medicine knowledge while learning the specific field.
This way you try to retrain information.