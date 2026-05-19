# AI-Assisted Power BI Pipeline using Claude MCP

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python)
![SQL Server](https://img.shields.io/badge/MS%20SQL%20Server-Database-red?style=flat-square&logo=microsoftsqlserver)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?style=flat-square&logo=powerbi)
![Claude AI](https://img.shields.io/badge/Claude%20AI-MCP%20Integration-purple?style=flat-square)

> An end-to-end Business Intelligence pipeline that integrates **Claude AI via Model Context Protocol (MCP)** into a real Power BI workflow — from raw data cleaning to AI-assisted dashboard development.

---

## Dashboard Preview

![Dashboard Screenshot](<Retail Customer Insights Dashboard Screenshot.png>)

---

## Overview

This project demonstrates a complete, production-style BI pipeline where Claude AI acts as an active collaborator — not just a chatbot — helping build DAX measures, answer business questions, validate data, and create visuals directly within Power BI.

---

## Pipeline — Step by Step

### 1. Data Cleaning (Python + Pandas)
- Ingested raw data and performed cleaning using Python and Pandas
- Handled null values, standardised field names, and validated record integrity
- Ensured data was analysis-ready before loading to the database

### 2. Database Layer (MS SQL Server)
- Established a Python-to-SQL Server connection using `pyodbc` / `sqlalchemy`
- Pushed the cleaned dataset into a structured SQL Server table
- Created a reliable, queryable single source of truth for downstream reporting

### 3. Power BI Connection
- Connected Power BI directly to the SQL Server table
- Loaded the clean dataset into the data model for reporting and visualisation

### 4. Claude MCP Integration
- Downloaded and configured the **Claude MCP server**
- Established a live AI-to-Power BI bridge
- Enabled Claude to interact directly with the Power BI data model

### 5. AI-Assisted Analysis & Development
With the MCP integration active, Claude was used to:
- Write and validate **DAX measures** for business KPIs
- Answer **business questions in natural language** (counts, aggregations, trends)
- Audit data quality — verifying total record counts and identifying anomalies
- **Rename and standardise field labels** for business-friendly reporting
- Recommend and generate appropriate **visuals** for each metric
  
---

## Features

- AI-assisted Power BI development using Claude MCP
- Natural language querying against BI datasets
- Automated DAX measure generation
- SQL Server integration pipeline
- Python-based data cleaning and validation
- AI-assisted visual recommendation workflow
- Production-style BI architecture

## Example AI Queries

With Claude MCP connected to Power BI, the assistant can respond to prompts such as:

```text
- "Create a DAX measure for YoY sales growth"
- "Which customer segment generated the highest revenue?"
- "Recommend the best visual for monthly sales trends"
- "Validate total order counts against the SQL source table"
- "Show the top 5 products by profit margin"
```

## Tech Stack

| Layer | Technology |
|---|---|
| Data cleaning | Python 3.x, Pandas |
| Database | Microsoft SQL Server |
| BI & Visualisation | Power BI |
| AI Integration | Claude AI, MCP Server |
| Query & Measures | DAX, SQL |

---

## Architecture Flow

```text
Raw CSV Data
    ↓
Python + Pandas Cleaning
    ↓
SQL Server Database
    ↓
Power BI Data Model
    ↓
Claude MCP Integration
    ↓
AI-Assisted Analytics & DAX Generation
```

## Project Structure

```text
powerbi-claude-mcp-pipeline/
├── README.md
├── data/
│   └── sample_data.csv          # Anonymised sample dataset
├── python/
│   ├── data_cleaning.py         # Data cleaning and transformation
│   └── sql_upload.py            # SQL Server connection and data upload
├── powerbi/
│   └── dashboard_screenshot.png # Final dashboard preview
├── mcp/
│   └── mcp_config.json          # MCP server config (credentials removed)
├── .env.example                 # Environment variable template
├── requirements.txt             # Python dependencies
└── .gitignore
```

---

## Getting Started

### Prerequisites
- Python 3.x
- Microsoft SQL Server (local or remote)
- Power BI Desktop
- Anthropic API key ([get one here](https://console.anthropic.com))
- Claude MCP server

### Installation

```bash
# Clone the repository
git clone https://github.com/aakshadha/powerbi-claude-mcp-pipeline.git
cd powerbi-claude-mcp-pipeline

# Install Python dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your SQL Server credentials and Anthropic API key
```

### Running the Pipeline

```bash
# Step 1: Clean the data
python python/data_cleaning.py

# Step 2: Upload to SQL Server
python python/sql_upload.py

# Step 3: Open Power BI Desktop and connect to your SQL Server table
# Step 4: Configure the MCP server (see mcp/mcp_config.json)
# Step 5: Connect Claude and start querying your data
```

---

## Key Learnings

- **MCP enables Claude to act as a BI collaborator** — it understands the data model and contributes directly to report development, not just answers generic questions
- Combining a clean data pipeline with AI assistance dramatically reduces the time from raw data to business insight
- DAX measure creation, which typically requires specialist knowledge, can be accelerated significantly with Claude's assistance

---

## Security Notes

- Never commit real credentials — use `.env` files and environment variables
- The `mcp_config.json` file in this repository contains placeholder API keys only
- Sample data has been anonymized — do not upload real business or personal data

---

## Author

**Anjali Akshadha Singh**  
BI Engineer | Power BI · Snowflake · SQL | AI-augmented analytics  
[LinkedIn](https://www.linkedin.com/in/anjali-akshadha-singh-874787131/)

---

## License

MIT License — feel free to use and adapt this project.
