# 🛒 Semantic Product Search Engine

This project is a **semantic product search engine** tailored for a quick commerce platform (e.g., Zepto). It enhances traditional keyword-based search using a hybrid approach combining **LLM-generated keyword expansion**, **BM25 ranking**, and **Sentence Transformer embeddings** to deliver highly relevant product matches for natural language queries.
![image](https://github.com/user-attachments/assets/a8ad3e71-82bd-4d55-a5cc-5471949e9f6a)

## 🔍 Features

- **Natural Language Search**: Accepts queries like `"oval yellow fruit"` and maps them to relevant product embeddings.
- **Hybrid Retrieval**: Combines BM25 lexical matching with dense vector similarity.
- **LLM-Powered Expansion** *(optional)*: Enhances recall by generating alternate phrasings using a language model.
- **Gradio UI**: Instant visual feedback of top retrieved products with product images and similarity scores.
- **Pluggable Corpus**: Easily update the dataset with new products or embedding models.

---

## 🚀 Demo

> Try out sample queries like:
- `"yellow citrus fruit"`
- `"Indian staple grain"`
- `"energy drink can"`

![Demo UI Screenshot](demo/screenshot.png)

---

## 🧠 Tech Stack

- **Python**, **Pandas**
- **SentenceTransformers** for dense embeddings
- **Rank-BM25** for sparse ranking
- **Gradio** for interactive UI
- **Torch**, **NumPy**
- *(Optional)* OpenAI LLM for query expansion
- **Jupyter Notebooks** for experimentation

---

## 🗂️ Project Structure
```
semantic-product-search/
│
├── app.py                     # Gradio app and main search logic
├── semantic_search.py         # Core search function with BM25 + cosine sim
├── product_data.csv           # Product metadata and embeddings
├── embedding_generator.ipynb  # Generate embeddings for product descriptions
├── demo/                      # Screenshots, sample queries
├── README.md
```
---

## ⚙️ How to Run

1. **Install dependencies**:

```bash
pip install -r requirements.txt

python app.py
```

## 📦 Input Format

Your `product_data.csv` file should have the following structure:

```csv
product,product_disc,product_url,combined,embedding
"100% Whole Wheat Chakki Atta","Whole Wheat Chakki Atta, Smart One, Vegetarian...","https://cdn.zeptonow.com/...","product 100 whole wheat chakki atta productdisc...","[0.0087, -0.0813, 0.0481, ...]"
...
