# GraphRAG: Graph-based Retrieval-Augmented Generation

This repository contains an implementation of the **GraphRAG** (Graph-based Retrieval-Augmented Generation) framework for query-focused summarization. The approach is based on the research paper _"From Local to Global: A GraphRAG Approach to Query-Focused Summarization"_ by Darren Edge et al.

GraphRAG leverages a graph-based text index and a Large Language Model (LLM) to generate comprehensive and diverse answers to global questions over large text corpora.

---

## Table of Contents

1. [Overview](#overview)
2. [Pipeline](#pipeline)
3. [Dependencies](#dependencies)
4. [Usage](#usage)
5. [Key Functions](#key-functions)
6. [Questions Addressed](#questions-addressed)
7. [Results](#results)
8. [References](#references)

---

## Overview

GraphRAG addresses the limitations of traditional Retrieval-Augmented Generation (RAG) and Query-Focused Summarization (QFS) methods by introducing a graph-based approach. It is designed to:

- Handle large corpora by overcoming the context window limitations of LLMs.
- Generate structured, query-focused summaries by leveraging graph-based community detection algorithms.
- Provide a modular pipeline for processing, indexing, and querying text data.

---

## Pipeline

The GraphRAG pipeline consists of the following steps:

1. **Text Chunks → Element Instances**:
   - Extract entities and relationships from text chunks using an LLM (e.g., Qwen or GPT-based models).
   - Store the extracted entities and relationships in a structured format.

2. **Element Instances → Element Summaries**:
   - Summarize the extracted entities and relationships into a structured format.

3. **Element Summaries → Graph Communities**:
   - Build a graph from the element summaries.
   - Detect communities in the graph using the Leiden algorithm.

4. **Graph Communities → Community Summaries**:
   - Summarize each detected community based on its entities and relationships.

5. **Community Summaries → Community Answers → Global Answer**:
   - Generate answers to user queries based on community summaries.
   - Combine community-based answers into a final global answer.

---

## Dependencies

The following Python libraries are required to run the notebook:

- `networkx`
- `leidenalg`
- `cdlib`
- `python-igraph`
- `pypdf`
- `langchain`
- `transformers`
- `tqdm`
- `matplotlib`
- `pandas`

To install the dependencies, run:

```bash
!pip install -q networkx leidenalg cdlib python-igraph pypdf langchain transformers tqdm matplotlib pandas
```
---

## Usage

1. Clone this repository and open the `GraphRAG.ipynb` notebook in Jupyter Notebook or Google Colab.
2. Follow the steps in the notebook to:
   - Process a text corpus (e.g., a PDF document).
   - Extract entities and relationships.
   - Build a graph and detect communities.
   - Generate query-focused summaries and answers.

3. Example query:
   ```python
   query = "What role do community detection algorithms (e.g., Leiden or Louvain) play in the Graph RAG framework?"
   final_answer = generate_final_answer(community_summaries, query)
   print("Answer: ", final_answer)
   ```

---

## Key Functions

### 1. `extract_element_Instances(chunks)`
Extracts named entities and relationships from text chunks using an LLM.

### 2. `summarize_element_Instances(elements)`
Summarizes extracted entities and relationships into a structured format.

### 3. `graph_building(summaries)`
Builds a graph from the summarized entities and relationships.

### 4. `communities_detection(graph)`
Detects communities in the graph using the Leiden algorithm.

### 5. `communities_summerization(communities, graph)`
Summarizes each detected community based on its entities and relationships.

### 6. `generate_final_answer(community_summaries, query)`
Generates a final answer to a query by synthesizing community-based answers.

---

## Questions Addressed

The notebook addresses the following research questions:

1. What problem does GraphRAG aim to solve that traditional RAG and QFS methods cannot?
2. How does the GraphRAG architecture overcome the limitations of LLM context windows?
3. What are the key steps in the GraphRAG pipeline, and how are they distributed between indexing time and query time?
4. How does GraphRAG differ from previous QFS or graph-based retrieval approaches?
5. What role do community detection algorithms (e.g., Leiden or Louvain) play in the GraphRAG framework?
6. How does the performance of GraphRAG scale with increasing corpus size (e.g., 1M tokens)?
7. What kind of summaries are generated during each stage of the GraphRAG pipeline, and how are they used?
8. Why is the distinction between ‘local’ and ‘global’ queries important in the design of GraphRAG?
9. How does entity extraction using GPT-4-turbo vary with chunk sizes in the HotPotQA dataset, as shown in Figure 2?
10. Why do the authors claim that query-focused abstractive summarization is more appropriate than retrieval-based generation for global questions?
11. In what ways does the modularity of graphs enable better summarization in the context of large corpora?
12. How does GraphRAG contribute to the broader goal of sensemaking in domains like scientific discovery or intelligence analysis?

---

## Results

- **Graph Construction**: The graph is built from extracted entities and relationships, with nodes representing entities and edges representing relationships.
- **Community Detection**: Communities are detected using the Leiden algorithm, enabling modular summarization.
- **Query Answering**: The framework generates concise, query-focused answers by synthesizing information from community summaries.

---

## References

- Darren Edge et al., _"From Local to Global: A GraphRAG Approach to Query-Focused Summarization"_
- [Leiden Algorithm](https://en.wikipedia.org/wiki/Leiden_algorithm)
- [LangChain Documentation](https://docs.langchain.com/)
- [Transformers Library](https://huggingface.co/transformers/)

