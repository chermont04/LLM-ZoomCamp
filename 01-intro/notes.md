# 📚 Module 1: Introduction to LLMs and RAG

## 🔍 Overview
In this module, we get hands-on with building a simple RAG (Retrieval-Augmented Generation) pipeline using FAQ documents from Zoomcamp courses. We cover indexing, searching, and generating answers with OpenAI API or local LLMs.

---

## 1.1 What are LLMs and RAG?

- **LLM (Large Language Models):** Models like GPT, trained on large text corpora to generate human-like responses.
- **RAG (Retrieval-Augmented Generation):** Enhances LLMs by retrieving relevant documents before generating answers.
- **RAG Architecture Components:**
  - **Retriever:** Finds relevant context from indexed documents.
  - **Generator:** Uses LLMs to generate an answer based on the query and retrieved context.

---

## 1.2 Preparing the Environment

### 🧰 Required Libraries
```bash
pip install tqdm notebook==7.1.2 openai elasticsearch==8.13.0 pandas scikit-learn ipywidgets
pip install minsearch  # Custom search engine used
```

## 1.3 Retrival Phase
- Tool: `minsearch`(custom search engine)
- Steps: 
    - Index the Zoomcamp FAQ documents

    - Perform document search based on the input query

## 1.4 Generation with OpenAI
- Goal: Use OpenAI's GPT to answer the questions using retrieved docs
- Steps:
    - Build a prompt with the user's question + retrieved docs
    - Call OpenAI API
    - Extract and present the answer

## 1.5 Cleaned RAG Flow
- Refactor and modularize code:
    - Separate indexing, retrieval and generation
    - Build reusable functions
    - Improve readability

## 1.6 ElasticSearch Integration
```
docker run -it --rm --name elasticsearch -m 4GB \
  -p 9200:9200 -p 9300:9300 \
  -e "discovery.type=single-node" \
  -e "xpack.security.enabled=false" \
  docker.elastic.co/elasticsearch/elasticsearch:8.4.3
```