# FAQ Chatbot — Online Payment App

A simple rule-based FAQ chatbot built with **TF-IDF** vectorization and **cosine similarity**. It matches a user's question to the closest FAQ from a predefined knowledge base and returns the corresponding answer.

## Features

- Interactive chat loop (keeps running until the user types `exit`)
- Greeting and farewell messages
- Handles empty or meaningless input gracefully
- 18 sample FAQs covering common online store queries (payments, orders, refunds, shipping, account management, etc.)
- Similarity threshold to avoid answering unrelated questions

## How It Works

1. Each FAQ is cleaned (lowercased, tokenized, stopwords/punctuation removed) using NLTK.
2. The cleaned FAQs are converted into TF-IDF vectors using scikit-learn's `TfidfVectorizer`.
3. When the user asks a question, it goes through the same cleaning pipeline and is vectorized.
4. Cosine similarity is computed between the user's question and all FAQ vectors.
5. If the best match score is above `0.50`, the corresponding answer is returned. Otherwise, the bot asks the user to rephrase.

## Tech Stack

- Python 3
- NLTK (tokenization, stopwords)
- scikit-learn (`TfidfVectorizer`, `cosine_similarity`)
- NumPy

## Getting Started

### 1. Clone the repository

git clone https://github.com/SirajM92Dev/CodeAlpha_Chatbot-for-FAQs.git
cd CodeAlpha_Chatbot-for-FAQs

### 2. Install dependencies

pip install -r requirements.txt

### 3. Run the notebook

Open `Internship_project_1.ipynb` in Jupyter Notebook / JupyterLab and run all cells.

jupyter notebook Internship_project_1.ipynb

The notebook will automatically download the required NLTK data (`punkt`, `stopwords`) on first run.

## Example Interaction

```
Hello! Ask me anything about our online store.
(Type 'exit' to end the chat)

You: Do you support cash on delivery?
Bot: Yes, cash on delivery is available for eligible locations.

You: exit

Bot: Thank you for using the chatbot!
```

## Future Improvements

- Add a web interface (Flask/Streamlit)
- Expand the FAQ dataset
- Use word embeddings (e.g. sentence-transformers) for better semantic matching
- Add spelling correction for user input
