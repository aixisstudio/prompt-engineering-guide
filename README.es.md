# Prompt Engineering Guide

[English](README.md) | [Français](README.fr.md) | **Español** | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Prompt engineering, de cero a técnicas avanzadas

_El contenido detallado (listas, enlaces, descripciones) está en inglés por mantenibilidad — las secciones siguientes te guían._

## 🎯 Levels

### 1. Clear instructions
Bad: "Write something about dogs." → Good: "Write a 150-word paragraph for a vet's website reassuring owners about anesthesia."

### 2. Few-shot
Give 2-3 input/output examples before your real input — the model mimics the pattern.

### 3. Persona + context
"You are a senior SRE reviewing a postmortem…" frames style, depth and vocabulary.

### 4. Structure & delimiters
Use XML-ish tags (`<context>…</context>`, `<task>…</task>`) — models parse them reliably.

### 5. Chain-of-thought
"Think step by step" — or better: explicitly ask to *plan first, then answer*.

### 6. Constrained output
Specify format: JSON schema, markdown table, exact length. Verify programmatically.

### 7. Self-critique loop
"Draft → critique your draft → produce final." One extra step, big quality jump.

### 8. Tool use & RAG
Give the model retrieval + functions instead of hoping it knows — the single biggest reliability lever.

## ⚠️ Failure modes
- **Vague goals** → vague output
- **Conflicting instructions** → the model picks one silently
- **Asking for certainty** on uncertain topics → hallucinations; prefer "say when you don't know"
- **Prompt injection** — never concatenate untrusted user text into system prompts

## 📚 References
- Anthropic prompt guide · OpenAI cookbook · dair-ai Prompt Engineering Guide
- Practice: `ai-prompts-hub` (this org) — add & browse real prompts

## 🧬 Advanced patterns

### Chain-of-Verification (CoVe)
1. Draft answer → 2. Generate verification questions → 3. Answer them independently → 4. Revise. Cuts hallucination dramatically.

### Self-consistency
Sample the same CoT prompt 5-10× at temperature 0.7, majority-vote the answer. +10-20% on reasoning benchmarks.

### ReAct (Reason + Act)
Interleave `Thought:` / `Action:` / `Observation:` — the backbone of tool-using agents.

### Skeleton-of-Thought
First generate an outline, then answer each point *in parallel*. Faster + more structured.

## 📏 Benchmarks worth knowing

| Benchmark | Tests |
|---|---|
| MMLU / MMLU-Pro | Broad knowledge |
| HumanEval / SWE-bench | Coding |
| GSM8K / MATH | Reasoning |
| IF-Eval | Instruction following |
| EQ-Bench | Emotional intelligence |

## ⚠️ Prompt-injection primer

- User input is never trusted context — delimit + instruct the model
- Tools/RAG content can carry instructions: treat retrieved text as untrusted
- Defense-in-depth: output validation > prompt hardening

---
## Contribuir

Los pull requests son bienvenidos: abre una PR y será revisada y fusionada. Mantenido por [aixisstudio](https://github.com/aixisstudio), autor de [Snitch](https://github.com/aixisstudio/Snitch), firewall de aplicaciones open source.

## Licencia: MIT
