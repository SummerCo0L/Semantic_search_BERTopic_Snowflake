# Snowflake Data Pipeline for Semantic Search and Topic Modelling (BERTopic)

This project implements an end-to-end data pipeline in Snowflake to enable semantic search and topic modeling. 
It empowers users to efficiently retrieve and analyze documents using keywords, and to uncover hidden themes and topics within the documents.

## Overview

The project consists of two main components:
1. **Data Ingestion and Transformation**: Implemented using Snowflake's SQL and Snowpark worksheets for Extract, Load, and Transform (ELT) processes.
2. **Semantic Search**: Utilizes pre-trained language model "all-MiniLM-L6-v2" and Snowflake's native capabilities to provide semantic search functionality.
3. **Topic Modelling**: Utilizes the BERTopic framework to identify and extract hidden themes and topics from the document corpus.

## Stored Procedures

The `Stored_Procedures` directory contains the stored procedures used in the Snowflake environment.

### LOAD_AND_REFRESH_DATABASE_sub-procedures

This directory contains stored procedures related to loading and refreshing the database.

- `SP1.1_load_to_table_from_stage.txt`: Script to load data into Snowflake table from staging area.
- `SP1.2_snowpark_transformations.txt`: Script for Snowpark transformations.
- `SP1.3_chunking_text.txt`: Script for chunking text.
- `SP1.4_embedding_chunks.txt`: Script for embedding chunks.
- `SP1.5_tokenizing_chunks.txt`: Script for tokenizing chunks.
- `SP1.6_embedding_tokens.txt`: Script for embedding tokens.

### RUN_SIMILARITY_SEARCH_sub-procedures

This directory contains stored procedures related to running similarity searches.

- `SP2.1_INSERT_QUERY.txt`: Script to insert queries into Snowflake table.
- `SP2.2_GET_SIMILARITY.txt`: Script to get similarity score between query and every chunk.
- `SP2.3_GET_TOKEN_SIMILARITY.txt`: Script to get token similarity score between query and every token.
- `SP2.4_GET_TOP_5_TOKENS.txt`: Script to get top 5 tokens for each chunk.

### Main Scripts

- `main_LOAD_AND_REFRESH_DATABASE.txt`: Main script for running all the 6 sub-procedures sequentially to load and refresh the database
- `main_RUN_SIMILARITY_SEARCH.txt`: Main script for running all the 4 sub-procedures of similarity search

## User-Defined Functions

The `User_Defined_Functions` directory contains user-defined functions used in the Snowflake environment.

- `udf_CHUNK_TEXT.txt`: Function to chunk text into smaller paragraphs/ sentences
- `udf_MiniLM_L6_v2_embedding.txt`: Function to embed text into vectors using MiniLM-L6-v2.
- `udf_py_spacy.txt`: Function using Python's spaCy library for text processing/ tokenizing.
- `udf_sklearn_cosine_similarity.txt`: Function to compute cosine similarity score using scikit-learn.

## Usage

1. **Set up Environment**: Before executing the scripts, ensure you have access to a Snowflake environment with the necessary permissions.

2. **Execution Steps**:
    - Open Snowflake's SQL or Snowpark worksheet.
    - Copy the contents of each script and execute them sequentially.
