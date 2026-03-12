# LLM Training

## Preparing and Splitting Dataset

- Training dataset - to train the model.
- Validation dataset - to tune hyperparameters and evaluate the model during training.
- Test dataset - to evaluate the final model's performance on unseen data.

Usually choosen randomly. Most common split is 80% for training, 10% for validation, and 10% for testing.

## Training vs Test error

**Overfitting** - instead of finding patterns, the model memorizes.
**Underfitting** - the model is too simple to capture the underlying patterns in the data.

- Training error - always is going down
- Validation/Test error - goes down at the beginning, but then starts going up (overfitting)

The art is finding the point between underfitting and overfitting.


## Neural Networks

- Weights
- Biases
- Activation functions (ReLU, Sigmoid, Tanh)
- Final output

Activation function introduces non-linearity into the model. Without it its just a linear regression.

- Loss function
- Backpropagation
- Epochs
- Batch size

## Training pipeline

Dataset -> Preprocessing -> Pre-training -> Post-training -> Optimization

| Preprocessing | Pre-training | Post-training | 
| --- | --- | --- |
| Filtering | Q&A format | Supervised fine-tuning |
| Synthetic data | Long context stage | Reinforcement learning with human feedback (RLHF) |
| Mixing |  Continued pre-training |  Knowledge distillation |
| | High quality stage | Online/offline learning |
| | Knowledge distillation |  Direct preference optimization (DPO) |

## Transformers

- Encoder - get input text
- Decoder - generate output text

### Variants of Transformers
- Encoder-only - output is not text, only classification
- Decoder-only - only generate text, no input

Examples of encoder-only: BERT, RoBERTa, DistilBERT

Examples of decoder-only: GPT-3, GPT-4, LLaMA, Claude, CTRL

Examples of encoder-decoder: T5, BART, mBART


### Benefits of decoder-only models
- Simpler architecture
- Memory efficient
- Faster inference
- Scalability
- Excellent for generative tasks

## Training from scratch
- Full control
- Resource intensive
- Lots of data required
- Lack of generalization

## Training cost
A lot.

## Types of Prediction
- Next word prediction - predicting the next word in a sentence
- Masked word prediction - predicting a missing word in a sentence

## Dataset diversity

From LLaMa 3 SFT training dataset:
- General english text 52.66 %
- Code 14.86 %
- Multilingual text 3.01 %
- Exam like 8.14 %
- Reasoning and tools 21.19 %
- Long content 0.14 %

## Parallelism and Distributed Training
- One computer, several GPUs:
    - TensorFlow
    - PyTorch
    - Keras
    - Horovod

### Distributed training techniques:
- Data parallelism - each GPU gets a different batch of data, but the same model.
    - Weights are periodically synchronized across GPUs after several epoch, you average the weights.
- Model parallelism - the model is split across multiple GPUs, each GPU is responsible for a different part of the model.

## Data
- Text, websites, books, code, etc.
- Collect data, clean it, augment it.
- Paraphrasing, synonym replacement, back-translation, noise addition, etc.

Data sources:
- Common Crawl (allowed to use, robot.txt)
- Books
- GitHub
- Other sources - social media, academic papers.
- Illegal sources

### Web crawling vs scraping
- Web crawling - automated process of systematically browsing the web to collect data. It follows links and gathers information from multiple pages.
- Web scraping - extracting specific data from a website, often using tools or scripts to parse the HTML content of a page.

### LLMs training LLMs
- copying from one model answers to another
- issue of data quality - more content on internet is LLM generated, so it can be low quality.

## Multi-Pass Processing
- Asking LLM to review and refine its own output.
- Chain of thought prompting - breaking down complex problems into smaller steps and asking the model to solve each step sequentially.

GPT-o1 - thinking model