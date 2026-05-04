# Cortex Analyst Semantic View UI

A Streamlit-based user interface for interacting with **Snowflake Cortex Analyst** using natural language queries.

This project provides a playground-style chat interface where users can:

* Ask questions in plain English
* Query structured business data using Cortex Analyst
* Use deployed semantic models stored in Snowflake stages
* View generated SQL from Cortex Analyst
* Maintain chat history during the session

## Features

Chat-based UI similar to Cortex Analyst Playground
Semantic model selection
Natural language → SQL generation
Streamlit UI deployed inside Snowflake
Session-based conversation history
Easy integration with Snowflake Cortex Analyst API


## Tech Stack

* Python
* Streamlit
* Snowflake Snowpark
* Snowflake Cortex Analyst API


## Project Structure

```bash
.
├── streamlit_app.py
├── environment.yml
├── README.md
```

---

## Prerequisites

Before running this application, ensure you have:

* A Snowflake account with Cortex enabled
* Cortex Analyst access
* A deployed semantic model (`.yaml`)
* The semantic model uploaded to a Snowflake stage

Example semantic model path:

```text
@DATABASE.SCHEMA.MODELS/retail_model.yaml
```

---

## Create Snowflake Stage

Run the following in Snowflake:

```sql
CREATE STAGE MODELS;
```

Upload your semantic model:

```sql
PUT file://retail_model.yaml @MODELS AUTO_COMPRESS=FALSE; 
```

Verify:

```sql
LIST @MODELS;
```

---

## Installation

Clone the repository:

```bash
git clone <your-repo-url>
cd <repo-name>
```

Install dependencies:

```bash
pip install streamlit snowflake-snowpark-python
```

---

## Run the Application

```bash
streamlit run streamlit_app.py
```

---

## Configuration

Update the semantic model path inside the app:

```python
@YOUR_DATABASE.YOUR_SCHEMA.MODELS/retail_model.yaml
```

---

## Example Questions

Try asking:

* Who has placed the most orders?
* Show top customers by revenue
* Which city generated highest sales?
* Top selling products this month
* Average order value by customer

---

## Example UI Flow

1. Launch the Streamlit app
2. Enter semantic model path
3. Ask a business question
4. Cortex Analyst generates:

   * Natural language answer
   * SQL query

---

## Future Enhancements

* Multiple semantic model support
* Query history export
* Chart visualization
* SQL execution preview
* Authentication & role-based access

---
