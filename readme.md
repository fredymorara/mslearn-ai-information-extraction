# Knowledge Mining Solution with Azure AI Search

This repository contains the code and documentation for creating a knowledge mining solution using Azure AI Search to index a set of travel brochure documents. The indexing process uses AI skills to extract key information from the documents. A Python client application is provided to search the index.

## Overview

In this lab, the following steps were completed:

1. **Created Azure Resources**:
    - Provisioned an **Azure AI Search** resource.
    - Provisioned an **Azure Storage** account (Blob Storage).
2. **Uploaded Documents**:
    - Downloaded travel brochures and uploaded them to an Azure Blob Storage container (`documents`).
3. **Created and Ran an Indexer**:
    - Imported data from Azure Blob Storage into Azure AI Search.
    - Applied AI enrichments:
        - Extracted phrases.
        - Extracted entities (Persons and Locations).
        - Extracted text from images (generated tags and categorized content).
    - Mapped fields to an index (`margies-index`).
4. **Searched the Index**:
    - Used the Search Explorer in the Azure portal to query the indexed documents and verify AI skill extraction.
5. **Created a Python Search Client**:
    - Used the `azure-search-documents` Python SDK.
    - Queried the index by title, locations, persons, and key phrases.

## Setup Instructions

### Prerequisites
- Python 3.x
- An active Azure subscription with Azure AI Search and Azure Storage accounts set up.

### Environment Setup
1. Navigate to the Python code folder:
   ```bash
   cd Labfiles/04-knowledge-mining
   ```
2. Create a virtual environment and activate it:
   ```bash
   python -m venv labenv
   labenv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Update the `.env` file in the `Labfiles/04-knowledge-mining` directory with your Azure AI Search credentials:
   ```env
   your_search_endpoint=YOUR_SEARCH_ENDPOINT
   your_query_key=YOUR_QUERY_KEY
   your_index_name=margies-index
   ```

### Running the Application
Execute the client application from the terminal:
```bash
python search-app.py
```
You can now enter search queries (e.g., `London`, `flights`) and type `quit` to exit.

## Cleanup
To avoid incurring Azure costs, delete the resource group associated with this lab when you are finished testing.
