# Retrieval Augmented Generation - RAG

RAG is system which allows to add additional info to LLM, it works by creating
DB with additional info, and everytime you query the model, its given the
context from the DB based on the query.

Options:
1. Prompt
2. Prompt and context
3. Prompt and DB - third cheapest option
4. Finetuning
5. Full retraining

## Vectorization
take text and create a vector that represents the text (carries the meaning of text).

- One-Hot Encoding - take all words in vocabulary, add one or zero
- TF-IDF - Term Frequency-Inverse Document Frequency, similar to previous but has some extra specific meaning for frequency
- Bag of Words (BoW)
- Image pixel flattening

## What are embeddings
word or the whole text to vector. or images or audio.
later we can perform semantic search and its quick.

vectors can be 1000 to 2000 dimmensions.
image processing works similarry with llms, it is converted to vector and then llm can understand the meaning of vector

**text-embedding-ada-002**
creates 1536 dimmension vector, lets say tennis article, get its meaning

Then you create a JSON entry, with all the data

Legal doc examples:
create a chatbot that would reference the docs. you have to search all tax laws and commentaries.

**text-embedding-3-large**

3072 dimmension vector

more clever and precise but slower.

1. generate vector
2. search db
3. retrieve
4. give to LLM

## Word2Vec

Two neural networks:
- One for encoding the words, which then propares some kind of projection, and then lets say from 20000 vector we produce 2d vector.
- Second one takes 2d vector and decodes it back to the output.

You get words that are close one to another in 2d space.
You can even do arithmetic, like subtracting and adding words.

## Semantic Search
Searching the meaning of the word or sentance, rather than exact words.

* Cosine similarity - the angle similarity
* Euclidian distance - isnt the best way for searching similarities
- Manhattan distance - absolute distance between different words. Going either up-down or left-right

## Vector databases
DB for storing vectors/embedings

Searching vectors is not common in relational DBs.

These are special DBs with various indexing/searching mechanisms to search these
large vectors efficiently. There is also metadata, to specify date of release,
source of data, etc.
The data has to be indexed, hast tables or other types.

**Advantages**:
- Speed and performance
- Scalability - massive amount of data
- Flexibility - videos, images, voice and other data vectorizing



### Searching algorithms
| | FLAT | HNSW (hierarchable navigatable small wordl) | MFPQ (Inverted file with product quantization)
Retrieval speed | low
indexing speed | fast
storage | low
db size | low
accuracty|  high
dimensionality | low
memory | low
volume | low

HNSW - creates tree like structure layers for searching. required more memory
MFPQ - create groups of centroids, where neighbors are located, first find centroid, then within it search for actual vector. uses less memory, works well with big db, not as accurate as previous methods

### Examples of DBs
chroma sth sth

### What is chunking?
Break down the text into smaller peaces and then generate the vectors for those.
Used in NLP to process large documents.

Take big doc and create chunks with overlap, like sliding window. Create vectors from those chunks, then search DB.

Chunking methods:
- By every 500 tokens.
- By sentence.
- By paragraph.
- By sematic section.
- By sliding window approach. (its great for context)

Examples:

Article -> Paragraphs -> Sumaries -> One sumup
Data stream -> Chunks based on time intervals -> analyze for trend and sentiment -> Agrevate


## RAG Architectures

1. Retrieval module
2. Generation module


Query + Documents -> Docs to embeding model which then searched DB -> retrieved stuff from db + query to LLM _> Output to user


### Types of Retrievers
- Sparce Retrievewrs: TF-IDF BM25 - keyword matching
- Dense Retriewers: vector based

Process:
When you search DB, you find several examples, you select top five or other count closest to your vector.

#### TF-IDF vectorization
TF-IDF calculates how often the word repeats.

### Types of generation
- Seq2Seq
- GPT

You dont need to fine-tune, just add info to DB.

one important thing of RAG, is how to work with datasources, you have to have
engine for converting all the formats and editing.


## RagFLow

## Sentence Transformers (SBERT)

Bi-encoder

A B inputs -> A B encoding -> A B vectors -> cosine similarity

Cross Encoder

A B input -> Bert -> Classifier -> Output


## Cosine
1 - similar
-1 - opposite
0 - not similar


## Microsoft RAG
start quickly and run into boundaries

## Vertex AI Search by Google
same thing basically.

# Evaluating RAGs

YOu need evaluation dataset

- Groundfulness or Faithfulness - does the answer corespond to the docs in DB
- Context relevence - is the answer relevent
- Diversity
- User Feedback
- Ground truth based metrics
- Answer relevence
- QA correctness
- Hallucinations
- Toxicity

## RAGAS framework
scoring RAG performance

Dense Passage Retrieval
Memory-Augmented Models
FID - Fussion in decoder
Adaptive retrieval - retrieve multiple times from DB