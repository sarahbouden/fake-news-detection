# Fake News Detection
## Project Introduction
fake-news-detection is a robust multi-agent system designed to automatically identify and analyze fake news claims across digital content. The project aims to improve the reliability of online information by leveraging state-of-the-art natural language processing (NLP), large language models (LLMs), and fact-checking APIs. Use cases include news aggregation platforms, social media monitoring, and research tools for misinformation analysis.

## Workflow / Architecture Overview
### Workflow:

**1.Input:** User provides text/news articles/claims.

**2.Processing Pipeline:**

  * Ingestion Agent extracts and preprocesses claims.

  * Claim Detection Agent identifies potential suspicious statements.

  * Evidence Retrieval Agent gathers factual evidence from web sources.

  * Fact-Checking Agents (Google Fact Check, Snopes Agent) interface with external APIs.

  * Claim Embedding Agent encodes claims semantically for comparison.

  * LLM Stance Agent classifies stance (SUPPORTS/REFUTES/NEUTRAL) using zero-shot Groq API.

  * Aggregation Agent compiles evidence and verdicts.

  * Explainability Agent generates human-readable explanations.

**3.Output:** Verdicts (fake/real/uncertain), confidence scores, evidence summaries, explanations.

**Architecture:**

Input → [Ingest] → [Claim Detection] → [Evidence Retrieval & Fact-Checking] → [Embedding & LLM Stance] → [Aggregation] → [Explainability] → Output

Multi-agent, modular, extensible design enabling parallel evaluation and transparent verdict generation.

## Components Explanation
  */outputs/: Stores model outputs, verdicts, and explanations.​

  */scripts/: Contains utility scripts like app.py (main app), config.py (settings), nltk_download.py, and test scripts.​

  */src/: Main source code containing agents, orchestration modules, LLM integrations, API schemas, config files, and unit tests.​

    * agents/: Specialized agents (ingest_agent, claim_detection_agent, evidence_retrieval_agent, verdict_agent, aggregation_agent, explainability_agent, google_fact_check_agent, snopes_agent, claim_embedding_agent, llm_stance_agent).

    * orchestration/: workflow.py defines pipeline workflow, nodes.py & state_graph.py manage pipeline states and transitions.

    * llm/: LLM wrapper for Groq API, prompt management.

    * api/: Schema definitions for API communication.

  * /templates/: Contains templates for setup and configuration files (app.py, config.py, requirements.txt).​

  * requirements.txt / requirements-deployment.txt: Lists Python package dependencies for development and deployment.

## Technologies Used
Python: Base language for all components.

Flask / FastAPI (if applicable): Web application framework for serving the model.

NLTK: Used for natural language preprocessing.

Groq API: Large Language Model-based classification and reasoning.

External Fact Checking APIs:

Google Fact Check

Snopes API

Loguru: Logging and monitoring.

JSON / YAML: Configuration and data interchange formats.

Testing Tools: Unit test modules for robust validation.

