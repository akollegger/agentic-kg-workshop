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


### 2. Set up Neo4j

#### 2.1 Neo4j Desktop on your local machine

Install Neo4j Desktop:
1. Download and install Neo4j Desktop from https://neo4j.com/download-center/
2. Open Neo4j Desktop and create a new instance (a graph database instance)
    - remember to use the same password you set in the `.env` file!

Install required plugins:
- install "APOC" for standard procedures and functions
- install "GenAI" for AI capabilities


Edit `neo4j.conf` (for older versions of Desktop):
```
dbms.security.procedures.unrestricted=apoc.*
dbms.security.procedures.allowlist=apoc.*,genai.*
```

Check the procedures are available:

```cypher
SHOW PROCEDURES WHERE name CONTAINS "genai.vector"
```

#### 2.2 Neo4j Aura in the cloud

Sign-up for Neo4j Aura:
1. Visit: http://console.neo4j.io
2. Click the "Create instance" button on the "Instances" page
3. Optional: name the instance
4. Click "Create instance" on the bottom of the page
5. Copy the password someplace safe (for use in a `.env` file later)
6. Click "Download and continue"
7. Wait for the instance to be provisioned

### 3. Create a copy of the environment variables file:
```bash
cp .env.template .env
```

Make two changes:
- Replace `NEO4J_PASSWORD` with the password for your database
- Replace `OPENAI_API_KEY` with the OpenAI API key provided for the workshop
- Replace `NEO4J_IMPORT_DIR` with the location of the data directory of the cloned repository




