# Multi-Agent-RAG-Research-Assistant

## Live Application Links
[![codelab](https://img.shields.io/badge/codelabs-4285F4?style=for-the-badge&logo=codelabs&logoColor=white)](https://codelabs-preview.appspot.com/?file_id=10JxYB2VVfDPeJeyB4UOgK0hLkW-VULxwzqYZYmiYE_g#0)
* Streamlit App(not live): http://134.209.221.147:8501
* FastAPI Docs(not live): http://134.209.221.147:8000/docs

## Technologies Used
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white)](https://streamlit.io/)
[![FastAPI](https://img.shields.io/badge/fastapi-109989?style=for-the-badge&logo=FASTAPI&logoColor=white)](https://fastapi.tiangolo.com/)
[![LangGraph](https://img.shields.io/badge/LangGraph-000000?style=for-the-badge&logo=langchain&logoColor=white)](https://github.com/langchain-ai/langgraph)
[![Tavily](https://img.shields.io/badge/Tavily-007ACC?style=for-the-badge&logo=internetexplorer&logoColor=white)](https://www.tavily.com/)
[![Amazon AWS](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)](https://openai.com/)
[![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Pinecone](https://img.shields.io/badge/Pinecone-6A4CBB?style=for-the-badge&logo=pinecone&logoColor=white)](https://www.pinecone.io/)
[![MistralAI](https://img.shields.io/badge/MistralAI-4C75A3?style=for-the-badge&logo=mistralai&logoColor=white)](https://www.mistral.ai/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-000000?style=for-the-badge&logo=matplotlib&logoColor=white)](https://matplotlib.org/)
[![Pydantic](https://img.shields.io/badge/Pydantic-008000?style=for-the-badge&logo=python&logoColor=white)](https://docs.pydantic.dev/)
[![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)](https://www.selenium.dev/)
[![DigitalOcean](https://img.shields.io/badge/DigitalOcean-0080FF?style=for-the-badge&logo=digitalocean&logoColor=white)](https://www.digitalocean.com/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)
[![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://www.python.org/)

## Overview

This project builds a multi-agent Retrieval-Augmented Generation (RAG) system to provide deep financial insights on NVIDIA by combining structured valuation data, unstructured quarterly reports, and real-time web content. It integrates LangGraph-based orchestration with Snowflake, Pinecone, Tavily, FastAPI, and Streamlit, all containerized with Docker and deployed on DigitalOcean.

## Problem Statement

Analyzing a company’s financial position requires synthesizing structured metrics, detailed reports, and live market updates—often spread across disparate sources. This project addresses the challenge by creating an intelligent, multi-agent research assistant that unifies Snowflake-based structured data, Pinecone-powered unstructured document retrieval, and Tavily-driven real-time news to deliver precise, context-rich answers about NVIDIA's financials.

## Project Goals

* Build a multi-agent RAG system capable of answering financial research queries on NVIDIA
* Use Snowflake to store and query structured valuation metrics like P/E ratios and profit margins
* Process unstructured quarterly reports into vector embeddings with metadata filters using Pinecone
* Integrate real-time market sentiment using Tavily web search API
* Orchestrate agent workflows with LangGraph for modular, explainable reasoning paths
* Provide a seamless user interface via Streamlit and robust API access through FastAPI
* Containerize all components using Docker and deploy on DigitalOcean for public accessibility

## Architecture Diagram

![Ass5_arch](https://github.com/user-attachments/assets/2ca37cfa-e372-4182-8824-0bd4117819d3)

## Directory Structure
```
Multi-Agent-RAG-Research-Assistant/  
│  
├── README.md  
├── docker-compose.yml  
├── requirements.txt  
├── .gitignore  
├── enterprise_multiples_bar.png  
├── market_value_line.png  
├── peg_ratio_bar.png  
│  
├── docker/  
│   ├── Dockerfile.backend  
│   └── Dockerfile.frontend  
│  
├── frontend/  
│   ├── app.py  
│   └── requirements.txt  
│  
├── backend/  
│   ├── app.py  
│   ├── requirements.txt  
│   │  
│   ├── agents/  
│   │   ├── __init__.py  
│   │   ├── rag_agent.py  
│   │   ├── snowflake_agent.py  
│   │   └── websearch_agent.py  
│   │  
│   ├── langgraph/  
│   │   ├── __init__.py  
│   │   └── orchestrator.py  
│   │  
│   └── utils/  
│       ├── __init__.py  
│       ├── conn_snowflake.py  
│       ├── data_fetech.py  
│       ├── pinecone_index.py  
│       ├── nvidia_historical_financials.csv  
│       ├── nvidia_pivoted_cleaned_data.csv  
│       └── nvidia_real_time_financials.csv  
│  
├── agents/  
│   ├── __init__.py  
│   ├── controller.py  
│   │  
│   ├── rag_agent/  
│   │   ├── __init__.py  
│   │   ├── rag_tool.py  
│   │   ├── pinecone_utils.py  
│   │   ├── dump_vector_ids.py  
│   │   ├── test_rag_tool.py  
│   │   ├── temp_script.py  
│   │   └── vector_id_map.json  
│   │  
│   ├── snowflake_agent/  
│   │   ├── __init__.py  
│   │   ├── extract.py  
│   │   ├── snowflake_rag.py  
│   │   ├── snowflake_tool.py  
│   │   └── nvdia_valuation_quarters.csv  
│   │  
│   └── web_agent/  
│       └── web_tool.py
```

## Application UI
![multi](https://github.com/user-attachments/assets/9d9ede4c-246f-449d-a437-3bf48f436b6c)


## Application Workflow

1. Open the application: Access the Streamlit frontend using this link.

2. Use filters: On the sidebar, select the Year and Quarter to refine your query based on metadata filters powered by Pinecone. This ensures only relevant report chunks are retrieved by the RAG agent.
   
3. Ask your research question: On the homepage, enter any question related to NVIDIA’s financial performance, valuation metrics, or recent trends.

4. Choose the agent(s):  
  * Select whether you want:
      * Only RAG Agent results (historical report analysis)
      * Only Snowflake Agent results (structured valuation data with visualizations)
      * Only Web Search Agent results (real-time news from API like Tavily)
      * Or a Combined Response using all three agents
   
## Prerequisites

- Python: Ensure Python is installed on your system. Python 3.8+ is recommended.
- Docker: Ensure Docker Desktop is installed and running.
- Docker Resources: Allocate at least 4 CPUs and 8 GB RAM for smooth execution of Streamlit, FastAPI, and other containers.
- API Keys: Add your OpenAI, Pinecone, and Tavily keys to a .env file in the root directory.
- Streamlit Knowledge: Familiarity with Streamlit will help in understanding and customizing the financial assistant UI.
- FastAPI Knowledge: Understanding FastAPI will assist in debugging backend agent routes and API validation logic.
- LangGraph Orchestration: Basic understanding of how LangGraph handles multi-agent workflows will help in extending the system.
- Vector Database Concepts: Knowledge of semantic search, embeddings, and metadata filtering will be useful when working with Pinecone.
- Snowflake Basics: Knowing how to query structured data from Snowflake will help in modifying or scaling the financial metrics pipeline.
- Git: Required for cloning and managing version control of the repository.
- Open Ports:
  - 8501 for the Streamlit UI
  - 8000 for the FastAPI backend
 
## How to run this Application locally

1. Clone the Repository
```
git clone https://github.com/your-username/Multi-Agent-RAG-Research-Assistant.git
cd Multi-Agent-RAG-Research-Assistant
```

2. Set Up Environment Configuration:
```
AWS_BUCKET_NAME=your_bucket_name
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_REGION=your_aws_region
OPENAI_API_KEY=your_openai_key
PINECONE_API_KEY=your_pinecone_key
PINECONE_INDEX=your_pinecone_index
TAVILY_API_KEY=your_tavily_key
SNOWFLAKE_USER=your_snowflake_user
SNOWFLAKE_PASSWORD=your_snowflake_password
SNOWFLAKE_ACCOUNT=your_snowflake_account
SNOWFLAKE_REGION=your_snowflake_region
SNOWFLAKE_ROLE=your_snowflake_role
SNOWFLAKE_DATABASE=your_snowflake_database
SNOWFLAKE_SCHEMA=your_snowflake_schema
SNOWFLAKE_WAREHOUSE=your_snowflake_warehouse
SNOWFLAKE_STAGE=your_snowflake_stage
```

3. Create and Activate a Virtual Environment
```
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```
4. Install Required Packages
```
pip install -r backend/requirements.txt
pip install -r frontend/requirements.txt
```

5. Build and Start All Services: Make sure Docker is running, then execute:
```
docker-compose up --build
```
This starts:
  - Streamlit Frontend → http://localhost:8501
  - FastAPI Backend → http://localhost:8000/docs

6. Use the Application
- Access the frontend at localhost:8501
- Apply Year and Quarter filters from the sidebar
- Enter your financial research question on NVIDIA
- Select agents (RAG / Snowflake / Web Search / All)
- Receive a comprehensive, context-rich research report


## REFERENCES

- https://langchain-ai.github.io/langgraph/
- https://colab.research.google.com/github/pinecone-io/examples/blob/master/learn/generation/langchain/langgraph/01-gpt-4o-research-agent.ipynb
- https://docs.pinecone.io/  
- https://docs.pinecone.io/docs/metadata-filtering
- https://docs.snowflake.com/  
- https://docs.snowflake.com/en/user-guide/python-connector  
- https://quickstarts.snowflake.com/
- https://tavily.com/
- https://fastapi.tiangolo.com/](https://fastapi.tiangolo.com/
- https://fastapi.tiangolo.com/tutorial/sql-databases/](https://fastapi.tiangolo.com/tutorial/sql-databases/
- https://docs.streamlit.io/](https://docs.streamlit.io/
- https://docs.docker.com
- https://docs.github.com/en](https://docs.github.com/en
