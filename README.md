# Agentic Knowledge Graph Workshop

This workshop will cover the basics of knowledge graph (KG) construction
using a multi-agent workflow.

## Prerequisites

- Python 3.12

## Setup

### 1. Install python libraries in a local virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 2. Create a copy of the environment variables file:
```bash
cp .env.template .env
```

Make two changes:
- Replace `NEO4J_PASSWORD` with a password of your choosing, to be used later when you create a Neo4j database
- Replace `OPENAI_API_KEY` with the OpenAI API key provided for the workshop


### 3. Set up locally managed Neo4j

Install Neo4j Desktop:
1. Download and install Neo4j Desktop from https://neo4j.com/download-center/
2. Open Neo4j Desktop and create a new instance (a graph database instance)
    - remember to use the same password you set in the `.env` file!

Install required plugins:
- install "APOC" for standard procedures and functions
- install "GenAI" for AI capabilities


Edit `neo4j.con` (for older versions of Desktop):
```
dbms.security.procedures.unrestricted=apoc.*
dbms.security.procedures.allowlist=apoc.*,genai.*
```

Check the procedures are available:

```cypher
SHOW PROCEDURES WHERE name CONTAINS "genai.vector"
```


Click on the folder icon next to "Path" to open the database directory:
- Copy all the content of `data` to the `import` sub-directory
- for example, I would do:
    `cp -r data/* '/Users/akollegger/Library/Application Support/Neo4j Desktop/Application/relate-data/dbmss/dbms-e9a4b9cc-ba2d-4fb8-8c19-ab29ef8fb08f/import'`







