## Visa & Kapital Bank Workshops — Notebooks Overview

This repository contains hands-on notebooks covering performance, governance, validation, data protection, prompt security, bias/fairness, and RAG evaluation for LLM systems. Below is a brief guide to each notebook.

### Day 1

- **day_1_1_1_performance_benchmarking_tracing.ipynb**: Crawl `kapitalbank.az`, build a Chroma vector store, run a simple RAG pipeline, and instrument tracing with LangSmith (including feedback, metadata, and tool use via DuckDuckGo).
- **day_1_1_2_performance_benchmarking_prompts.ipynb**: Prompt engineering with LangSmith prompt management — push/pull/version prompts and load them inside a traced RAG flow.
- **day_1_1_3_performance_benchmarking_evals.ipynb**: Build datasets (manual and from prior runs), define custom precision grader, and evaluate baseline RAG (with/without web search) using LangSmith.
- **day_1_2_1_governance_langchain_agent.ipynb**: Rebuild an agent in LangChain with a retriever tool and DuckDuckGo search, drive it with a managed system prompt, and produce traced answers.
- **day_1_2_2_governance_tracing_and_prompts.ipynb**: Manage prompts and tracing with Langfuse; create an agent using production-labeled prompts; add sessioned conversations and multi-user chat flows with tracing.
- **day_1_3_1_validation_datasets.ipynb**: Generate synthetic Q&A (OpenAI), create and upload datasets to Langfuse, generate a RAG test set with RAGAS, and push items; also demo DeepEval-based synthetic data upload.
- **day_1_3_2_validation_evals.ipynb**: Run agent experiments on Langfuse datasets and print formatted experiment results (with trace IDs per item).
- **day_1_4_data_protection.ipynb**: Compliance-focused agent runs with rich metadata (jurisdiction, consent, retention, transfer mechanisms) recorded in Langfuse; shows safe agent foundation over Chroma.

### Day 2

- **day_2_1_prompt_injection.ipynb**: Demonstrates prompt injection and mitigation with `llm-guard` — topic banning, prompt injection detection, PII anonymization/de-anonymization, and output scanning (NoRefusal, Relevance, Sensitive).
- **day_2_2_bias_and_fairness.ipynb**: Red-team style evaluation using `langfair` — toxicity, stereotypes, and counterfactual bias; includes hard-coded test cases and metric reporting.
- **day_2_3_rag_and_data_security.ipynb**: RAG evaluation walkthrough — simple agent with KB tool, manual evaluation setup, generate Q&A pairs, build an evaluation dataset, and run RAGAS metrics.
- **day_2_4_chroma_benchmark.ipynb**: End-to-end Chroma benchmarking: chunking/ingestion (with optional PII masking), latency vs. concurrency, quality metrics (SelfRecall/URLHit), ACL leakage checks, plots, and an LLM-authored benchmark report.
- **day_2_5_vector_db_analysis.ipynb**: Embedding bias analysis with WEFE — compute WEAT effect sizes and p-values using OpenAI embeddings (and optional gensim baselines), with simple caching utilities.

### Prerequisites & Notes

- Most notebooks expect `OPENAI_API_KEY` (and, where used, LangSmith/Langfuse environment variables) to be set within the notebook or environment.
- Vector DB examples persist to `chroma_kapitalbank/` and may emit deprecation warnings if using newer `langchain-chroma`.
- Some cells download models or datasets on first run (RAGAS, detoxify, NER, etc.).

### Quick Start

1) Open any notebook in this directory.
2) Set the required environment variables in the first cells.
3) Run cells top-to-bottom and inspect the produced artifacts (datasets, traces, reports, plots).


