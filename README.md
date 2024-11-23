# OCR-to-RAG-A-Pipeline-for-Text-Embeddings-and-Retrieval

This project implements a Retrieval-Augmented Generation (RAG) workflow to analyze multimodal data related to the Apollo 11 mission. By leveraging Optical Character Recognition (OCR), text embeddings, and vector databases, this notebook enables efficient retrieval of relevant information from a diverse dataset. Using Gemini and Chroma DB, we combine structured information retrieval with a generation system to answer queries about the Apollo 11 mission

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Workflow Steps](#workflow-steps)
  - [1. Data Preparation](#1-data-preparation)
  - [2. Data Extraction and Summarization](#2-data-extraction-and-summarization)
  - [3. Embedding Generation](#3-embedding-generation)
  - [4. Creating a Vector Database](#4-creating-a-vector-database)
  - [5. Querying the RAG System](#5-querying-the-rag-system)
- [Example Queries](#example-queries)
- [Contributing](#contributing)
- [License](#license)

## Overview

This notebook project focuses on building a scalable RAG system to summarize and retrieve data across multiple formats:
- **Text**: NASA post-mission reports.
- **Video**: Apollo 11 moonwalk footage.
- **Audio**: Communication highlights from the mission.

Using **Gemini** for embeddings and **Chroma DB** for storage and retrieval, the pipeline allows users to search and retrieve relevant files, generate summaries, and provide contextual responses.

## Features

- **Optical Character Recognition (OCR)** for text extraction from images.
- **Gemini-based Summarization** for concise summaries optimized for retrieval.
- **Text Embedding Generation** with Gemini’s embedding model.
- **Vector Database with Chroma DB** for efficient similarity search and retrieval.
- **Retrieval-Augmented Generation (RAG)** to answer queries based on retrieved documents.

## Setup and Installation

1. Install required libraries by running the following commands:
    ```bash
    !apt install tesseract-ocr libtesseract-dev
    !pip install -q -U google-generativeai chromadb pytesseract
    ```

2. Download the resources needed for the exercise:
    ```bash
    !wget -O resources.zip "https://video.udacity-data.com/topher/2024/June/66744e79_resources/resources.zip"
    !unzip resources.zip
    ```

## Usage

Open the notebook in Google Colab or Jupyter and follow the steps outlined to run the RAG pipeline. Start by uploading the required API key for Google Generative AI in the environment.

## Workflow Steps

### 1. Data Preparation
Prepare and unzip the dataset, which includes text, video, and audio files from the Apollo 11 mission archive.

### 2. Data Extraction and Summarization
- **Text Data**: Uses OCR with Tesseract to extract text from images.
- **Summarization**: Employs a Gemini-based prompt to create concise summaries optimized for retrieval.

### 3. Embedding Generation
Generate embeddings for the summarized text using Gemini’s text embedding model, transforming the data into high-dimensional vectors for similarity searches.

### 4. Creating a Vector Database
Store embeddings in Chroma DB, a vector database, to enable efficient retrieval of relevant documents based on query embeddings.

### 5. Querying the RAG System
Using a sample query, the RAG system retrieves relevant files and provides a generated response. For example, you can query “Apollo 11 Flight Plan” and receive information on the specific documents and summaries related to the mission plan.

## Example Queries

- **“Apollo 11 Flight Plan”**: Retrieve and summarize relevant text related to the mission timeline.
- **“Describe communication with Mission Control”**: Return audio summaries with descriptions of interactions between the astronauts and mission control.
- **“Explain what happened during Apollo 11”**: Generate a comprehensive response using text, audio, and video summaries.

