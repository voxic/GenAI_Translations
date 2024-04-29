# Translations using Semantic Search and GenAI

This project demonstrates how to use MongoDB with the OpenAI API for generating and retrieving text embeddings to facilitate translation retrieval using semantic search. It includes scripts for setting up the environment, generating embeddings from existing translations, and fetching translations based on semantic similarity.

## Setup

### Requirements

- Python 3.8+
- pymongo
- openai

You can install the required libraries using `pip`:

```bash
pip install pymongo openai
```

### Configuration

Update the `MONGO_URI` and `api_key` in the script to match your MongoDB and OpenAI configurations:

```python
MONGO_URI = "mongodb+srv://<user>:<password>@<cluster-url>/"
aiClient = OpenAI(api_key='<your-openai-api-key>')
```

### Database

The script assumes the MongoDB collections are named `TRANSLATIONS` for the source texts and `TRANSLATIONS_embeddings` for the embeddings. Adjust these if your collection names differ.

## Usage

### Generating Embeddings

Run the provided function `process_documents()` to retrieve texts from the `TRANSLATIONS` collection, generate their embeddings, and store these embeddings in the `TRANSLATIONS_embeddings` collection.

### Fetching Similar Translations

Use the script's `search_embedding` function to generate an embedding for a new phrase and retrieve the most semantically similar translations from the database using MongoDB's vector search.
