# RAG QnA System with Evaluation

This project demonstrates a **Retrieval-Augmented Generation (RAG)** pipeline for question answering (QA), using **Ollama Llama 3.2** for language generation. It evaluates the pipeline's performance on the **QnA_v2 dataset** using metrics like BERTScore, BLEU, and ROUGE.

## Architecture

Below is the architecture of the RAG pipeline implemented in this project:

![RAG Implementation + Evaluation Workflow](image.png)

### Key Components:
1. **Query from QA Dataset**: Input questions are taken from the QnA_v2 dataset.
2. **Hugging Face Embedder**: Both the query and documents are vectorized using Hugging Face embeddings.
3. **ChromaDB**: The vectorized documents are stored and retrieved using ChromaDB.
4. **Cross-Encoder Reranker**: Retrieved documents are reranked for relevance using a cross-encoder.
5. **Language Model (LLM)**: The response is generated using Ollama's Llama 3.2. (This can be replaced with a Hugging Face model.)
6. **Evaluation with True Answer**: The generated response is evaluated against the true answer using metrics like BERTScore.

---

## Features

- **Customizable LLMs**: Currently integrates **Ollama Llama 3.2**, but can be adapted to any Hugging Face model by updating the `llm` initialization in LangChain.
- **Efficient Retrieval**: Uses **ChromaDB** for fast and scalable document retrieval.
- **Relevance Ranking**: Leverages a cross-encoder to rerank retrieved documents.
- **Evaluation**: Measures QA pipeline performance using multiple metrics:
  - BERTScore
  - BLEU
  - ROUGE

---

## Dataset

The project uses the **QnA_v2 Dataset**, a collection of QA pairs for evaluation. Download it here:
- [QnA_v2 Dataset](https://msmarco.z22.web.core.windows.net/msmarco/dev_v2.1.json.gz)

---