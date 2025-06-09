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