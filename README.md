# README

## Overview
This script demonstrates the process of loading and processing textual data for training a Word2Vec model. It tokenizes a given text corpus, removes punctuation, and attempts to test a pre-trained Word2Vec model by retrieving word embeddings and finding similar words.

## Requirements
Ensure you have the following dependencies installed before running the script:

- **Python 3.x**
- **NLTK (Natural Language Toolkit)**
- **Gensim**
- **NumPy**

You can install the necessary packages using:

```sh
pip install nltk gensim numpy
```

## Steps in the Script
### 1. Download Required NLTK Data
The script downloads the 'punkt' tokenizer model used for word tokenization.

### 2. Create a Sample Corpus
A list of predefined sentences is used as a sample corpus.

### 3. Tokenization and Preprocessing
- Tokenizes each sentence into words.
- Converts text to lowercase.
- Removes punctuation marks.

### 4. Testing the Word2Vec Model
- Attempts to load a pre-trained Word2Vec model (`word2vec.model`).
- Retrieves the vector representation of the word **"machine"**.
- Finds the top 3 most similar words to **"machine"**.

## Notes
- The script assumes that a pre-trained `word2vec.model` exists in the working directory.
- If the model file does not exist, the script will raise an error. To train a new Word2Vec model, consider adding the following training step:

  ```python
  model = Word2Vec(sentences=tokenized_corpus, vector_size=100, window=5, min_count=1, workers=4)
  model.save("word2vec.model")
  ```

- The script contains a duplicate section where the model is loaded and tested twice; consider removing redundancy to optimize execution.

## Running the Script
To execute the script, run:

```sh
python script.py
```

Ensure that `word2vec.model` is available in the directory.

## Output Example
If the model exists, the output will display:

```
Vector representation of 'machine':
 [0.12345 ... ]

Words similar to 'machine': [('learning', 0.98), ('deep', 0.95), ('AI', 0.93)]
```

If the model is missing, an error message will appear.

## Future Improvements
- Add a model training section if `word2vec.model` does not exist.
- Remove redundant model testing.
- Handle missing model errors gracefully with try-except blocks.

## Author
**Your Name** (Replace with your actual name)

