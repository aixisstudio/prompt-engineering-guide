# Prompt Engineering Guide

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh-CN.md) | [日本語](README.ja.md) | **Русский**

Промпт-инжиниринг: от нуля до продвинутого

_Подробное содержимое (списки, ссылки, описания) ведётся на английском — разделы ниже помогут сориентироваться._

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

---
## Участие

Pull request'ы приветствуются — открой PR, он будет проверен и принят. Ведёт [aixisstudio](https://github.com/aixisstudio), автор [Snitch](https://github.com/aixisstudio/Snitch) — open-source application firewall.

## Лицензия: MIT
