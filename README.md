# Snowflake Data Pipeline for Semantic Search

This project implements an end-to-end data pipeline in Snowflake to enable semantic search, empowering users to efficiently retrieve and analyze documents using keywords.

## Overview

The project consists of two main components:
1. **Data Ingestion and Transformation**: Implemented using Snowflake's SQL and Snowpark worksheets for Extract, Load, and Transform (ELT) processes.
2. **Semantic Search**: Utilizes pre-trained language model "all-MiniLM-L6-v2" and Snowflake's native capabilities to provide semantic search functionality.

## Stored Procedures

The `Stored_Procedures` directory contains the stored procedures used in the Snowflake environment.

### LOAD_AND_REFRESH_DATABASE_sub-procedures

This directory contains stored procedures related to loading and refreshing the database.

- `SP1.1_load_to_table_from_stage.txt`: Script to load data into tables from staging area.
- `SP1.2_snowpark_transformations.txt`: Script for Snowpark transformations.
- `SP1.3_chunking_text.txt`: Script for chunking text.
- `SP1.4_embedding_chunks.txt`: Script for embedding chunks.
- `SP1.5_tokenizing_chunks.txt`: Script for tokenizing chunks.
- `SP1.6_embedding_tokens.txt`: Script for embedding tokens.

### RUN_SIMILARITY_SEARCH_sub-procedures

This directory contains stored procedures related to running similarity searches.

- `SP2.1_INSERT_QUERY.txt`: Script to insert queries.
- `SP2.2_GET_SIMILARITY.txt`: Script to get similarity.
- `SP2.3_GET_TOKEN_SIMILARITY.txt`: Script to get token similarity.
- `SP2.4_GET_TOP_5_TOKENS.txt`: Script to get top 5 tokens.

### Main Scripts

- `main_LOAD_AND_REFRESH_DATABASE.txt`: Main script for loading and refreshing the database.
- `main_RUN_SIMILARITY_SEARCH.txt`: Main script for running similarity searches.

## User-Defined Functions

The `User_Defined_Functions` directory contains user-defined functions used in the Snowflake environment.

- `udf_CHUNK_TEXT.txt`: Function to chunk text.
- `udf_MiniLM_L6_v2_embedding.txt`: Function to embed text using MiniLM-L6-v2.
- `udf_py_spacy.txt`: Function using Python's spaCy library for text processing.
- `udf_sklearn_cosine_similarity.txt`: Function to compute cosine similarity using scikit-learn.

## Usage

1. **Set up Environment**: Before executing the scripts, ensure you have access to a Snowflake environment with the necessary permissions.

2. **Execution Steps**:
    - Open Snowflake's SQL or Snowpark worksheet.
    - Copy the contents of each script and execute them sequentially.
