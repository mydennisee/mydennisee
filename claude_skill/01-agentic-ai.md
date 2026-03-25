# 01 — Agentic AI & LLM/VLM Systems

## What I Do

Design, fine-tune, and deploy autonomous AI systems — from single-agent tools to multi-agent orchestration pipelines. Work spans the full stack: model selection, dataset curation, fine-tuning, prompt engineering, RAG, and production deployment.

---

## How I Approach It

### Model Selection
- Evaluate open-weight vs. proprietary models against task requirements
- Assess context window, inference cost, latency, and fine-tuning support
- Default to self-hosted for regulated or data-sensitive use cases

### Fine-Tuning (LoRA / QLoRA)
- Curate task-specific datasets — quality over volume
- Apply LoRA adapters to freeze base weights, tune only task-relevant parameters
- QLoRA for GPU memory efficiency on consumer or mid-range hardware
- Benchmark before and after: perplexity, task accuracy, hallucination rate

### Prompt Engineering
- Field-scoped prompts — constrain the model to one task per call
- JSON-only output constraints for structured extraction pipelines
- No-inference constraints where factual extraction is required (e.g., financial docs)
- Context injection from upstream pipeline steps

### RAG (Retrieval-Augmented Generation)
- Chunk, embed, and store source documents in vector stores (pgvector / Chroma)
- Cosine similarity retrieval — tune top-k and similarity threshold per use case
- Dual-write pattern: structured store for direct query + vector store for semantic search

### Multi-Agent Design
- Decompose complex tasks into discrete agent roles with clear input/output contracts
- Orchestrator + worker pattern — orchestrator routes, workers specialize
- Confidence scoring and reconciliation steps between agents

---

## Tools & Stack

| Category | Tools |
|----------|-------|
| Fine-tuning | HuggingFace Transformers, PEFT, LoRA, QLoRA |
| Inference | vLLM, Ollama, self-hosted Qwen |
| RAG | LangChain, pgvector, Chroma |
| GPU | CUDA, RAPIDS, RTX hardware |
| Evaluation | Custom benchmarks, perplexity, task-specific metrics |

---

## Demonstrated Work

- **Agentic AI & GPU Lab** — Autonomous multi-agent architecture with LoRA/QLoRA fine-tuning on RTX 5090 infrastructure. 2–5× inference speed improvement.
- **FinDoc Intelligence Pipeline** — VLM + Qwen hybrid extraction pipeline: visual parse → rule engine → LLM reconciliation → Supabase dual-write → FastAPI.
- **PII Privacy Protector** — LLM-based entity detection and redaction. Presented at AI Board Member Day.

---

## My Standard: What "Done" Looks Like

- Model benchmarked against baseline before declaring improvement
- Prompts versioned and documented with rationale
- Output schema validated — no silent failures
- Confidence or quality score attached to every inference result
- Deployment pathway defined: API endpoint, batch job, or embedded agent
