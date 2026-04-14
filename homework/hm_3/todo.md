3.1

use the tensor library to load the weight and then save, but the quentization we have to do it manually, there are various types, experiment

Q, K, S, M, L types, read about it, dig deeper into this, do sth interesting,
different types of quantization for matrixes? hm, lobotomy? add random noise, have fun




3.2

use library for vecorization because we cant do that by hand, use your own code for other bullet points.


simple coding exercise without ai - perform chunking of the text. (by number of words or full stop)
and sth else extra will be given related to the 3.1 or 3.2 or quantization, like generate real numbers and quantize them in some manner.



# HW3
## Homework #3 deadline 2026-04-16
Simple coding exercise without AI.
+ Perform chunking of the text
+ Will be given later
### Homework #3.1 - perform quantization Implement without framework. Use numpy and pandas for that
+ Load a pre-trained Large Language Model (LLM) locally.
+ Extract and analyze the model's coefficients/weights/tensors/activations (all parameters)
+ Create a visual representation of the weight values' distribution (it was in the lecture).
+ Quantize the model parameters effectively and visualize. Explain.
+ Run model with original weights and with quantized weights and compare results
+ If you do only above points, you will get 80%.
+ Expand beyond the basic requirements for a deeper analysis and improved outcomes (remaining 20%).
    + Stop using GPT and think for yourself for once.
### Homework #3.2 - Vectorisation, Vector Databases, and Chunking. Implement without framework. Use numpy and pandas for that
**Instructions:**
To receive full credit, please follow the instructions precisely. Use Python for all tasks unless stated otherwise.
**Tasks:**
 1. **Text Selection**: Find a text containing at least 10 paragraphs. New line-separated paragraphs are acceptable, and you may source this text manually. Paragraph should be 
 2. **Chunking**: Divide the text into at least 10 chunks.
 3. **Vectorization and Storage**: Vectorize each chunk of text. Store each vector along with its corresponding text chunk in a Pandas DataFrame (u can use lib here)
    + Do not use 'all-MiniLM-L6-v2', use other models.
 4. **New Paragraphs**: Write or obtain 3 new paragraphs related to the original text. This can also be done manually.
 5. **Vectorization of New Paragraphs**: Vectorize these 3 new paragraphs.
 6. **Similarity Matching**: For each new paragraph, identify and match it with the most similar chunk from the DataFrame based on vector similarity.
    + Investigate various similarity metrics 
    + Be ready to elaborate on this topic
 7. **Output**: Display each pair (each new paragraph alongside its most similar original chunk) on the screen.
 8. **During evaluation**, you will be asked to write code related to the homework. 
**Note**: If you used all deepinfra credits, register using new email account to get more free credit.
 