
# EthioMart - Named Entity Recognition for Amharic E-commerce Data

## Overview

EthioMart, a growing hub for Telegram-based e-commerce in Ethiopia, aims to consolidate multiple independent e-commerce channels into a single centralized platform. With the increasing use of Telegram for business transactions, customers and vendors are currently spread across various channels, leading to challenges in product discovery, communication, and order management. 

This project focuses on building an **Amharic Named Entity Recognition (NER) system** to extract important business entities—such as product names, prices, and locations—from the messages shared in these Telegram channels. The extracted data will be used to populate EthioMart's centralized database, providing a seamless and organized shopping experience for customers and a unified platform for vendors.

## Key Objectives

1. **Real-time Data Extraction**: Fetch data from various Ethiopian Telegram e-commerce channels.
2. **Fine-tuning Large Language Models (LLMs)**: Adapt existing LLMs to accurately extract business entities like product names, prices, and locations from Amharic text.

## Tasks Breakdown

### Task 1: Data Ingestion and Data Preprocessing

This task involves building a system that collects messages from multiple Ethiopian Telegram e-commerce channels, processes them, and prepares the data for entity extraction.

#### Steps:

1. **Identify and Connect to Relevant Telegram Channels**:
   - Develop a custom scraper to fetch real-time data from selected Telegram e-commerce channels.
   - List of relevant channels will be identified for data collection.

2. **Ingest Messages**:
   - Collect text messages, images, and documents from these channels.
   - Ensure real-time collection of data as they are posted.

3. **Preprocess Text Data**:
   - Tokenize and normalize Amharic text.
   - Handle Amharic-specific linguistic features such as script and morphology.
   - Structure the data into a unified format, including metadata (sender, timestamp) and message content.

4. **Data Storage**:
   - Store preprocessed data in a structured database for further analysis and model training.

### Task 2: Label a Subset of the Dataset in CoNLL Format

For fine-tuning the Named Entity Recognition (NER) model, a subset of the dataset will be manually labeled in the CoNLL format. The goal is to identify entities such as **Product**, **Price**, and **Location** from the Amharic text messages.

#### Steps:

1. **Label Entities**:
   - Each word (token) in a message is labeled with the appropriate entity tag: 
     - `B-Product`: Beginning of a product entity (e.g., "Baby bottle").
     - `I-Product`: Inside a product entity (e.g., "bottle" in "Baby bottle").
     - `B-LOC`: Beginning of a location entity (e.g., "Addis Abeba").
     - `I-LOC`: Inside a location entity (e.g., "Abeba" in "Addis Abeba").
     - `B-PRICE`: Beginning of a price entity (e.g., "ዋጋ 1000 ብር").
     - `I-PRICE`: Inside a price entity (e.g., "1000" in "ዋጋ 1000 ብር").
     - `O`: Outside of any entity.
     
2. **Format Data in CoNLL Format**:
   - Each token is labeled on its own line, followed by its entity tag.
   - Blank lines separate individual messages.
   - The labeled dataset will be saved in plain text files, ensuring compatibility with machine learning frameworks.

## Task 3, 4, 5: Named Entity Recognition (NER) using Transformer Models

This project aims to train and evaluate transformer-based models for Named Entity Recognition (NER) using the Hugging Face library. The task involves token classification for product-related entities such as `Product`, `Price`, and `Location`.




