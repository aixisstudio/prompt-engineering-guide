# Prompt Engineering Guide

[English](README.md) | [Français](README.fr.md) | **Español** | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Prompt engineering, de cero a técnicas avanzadas

## 🎯 Levels

#### 1. Instrucciones claras
Malo: "Escribe algo sobre los perros." → Bien: "Escribe un párrafo de 150 palabras para el sitio web de un veterinario tranquilizar a los propietarios sobre la anestesia".

### 2. Pocos disparos
Dar 2-3 ejemplos de entrada / salida antes de su entrada real - el modelo imita el patrón.

### 3. Persona + contexto
"Usted es un SRE senior revisando un postmortem..." marcos estilo, profundidad y vocabulario.

### 4. Estructura &quot; delimitadores
Utilice etiquetas XML-ish (`<context>…</context>`, `<task>…</task>`) — los modelos los analizan de forma fiable.

### 5. Chain-of-thought
"Piensa paso a paso" —o mejor: explícitamente pregunte a *plan primero, luego responda*.

#### 6. Salida cons capacitadas
Especifique el formato: esquema JSON, tabla de marcado, longitud exacta. Verifica programáticamente.

### 7. Loop autocrítica
"Draft → critica tu proyecto → producir final." Un paso extra, salto de gran calidad.

### 8. Uso de herramientas
Dar la recuperación modelo + funciones en lugar de esperar que lo sepa, la palanca de confiabilidad más grande.

## ⋅ Failure Modes
- **Objetivos vagos**
- **Conflicting instructions** → el modelo elige una silenciosa
- **Buscar certeza** sobre temas inciertos → alucinaciones; prefiera "hablar cuando no lo sepas"
- **Inyección rápida** - nunca concatenar texto de usuario no confiable en los impulsos del sistema

## 📚 Referencias
- Guía de ingeniería antropópica · OpenAI cookbook · dair-ai Prompt Engineering Guide
- Práctica: `ai-prompts-hub` (esta org) - añadir &amp; navegar por los impulsos reales

## 🧬 Patrones avanzados

## Chain-of-Verification (CoVe)
1. Proyecto de respuesta → 2. Generar preguntas de verificación → 3. Responderlos independientemente → 4. Revise. Corta la alucinación dramáticamente.

### Self-consistency
Muestra el mismo impulso CoT 5-10× a temperatura 0.7, la mayoría-vote la respuesta. +10-20% en referencias de razonamiento.

### React (Reason + Act)
Interleave `Thought:` / `Action:` / `Observation:` — la columna vertebral de los agentes de uso de herramientas.

## Skeleton-of-Thought
Primero generar un esquema, luego responder cada punto *en paralelo*. Más rápido + más estructurado.

## 📏 Parámetros vale la pena saber

← Tests sobre la vida
|---|---|
← MMLU / MMLU-Pro
Silencio HumanEval / SWE-bench
Silencio GSM8K / MATH ANTE Reasoning
Silencio IF-Eval
Silencio EQ-Bench

## ⋅ Prompt-injection primer

- La entrada de usuario nunca es un contexto de confianza - delimitar + instruir el modelo
- El contenido de Herramientas/RAG puede llevar instrucciones: tratar el texto recuperado como no confiado
- Defensa en profundidad: validación de salidas

---
## Contribuir

Los pull requests son bienvenidos: abre una PR y será revisada y fusionada. Mantenido por [aixisstudio](https://github.com/aixisstudio), autor de [Snitch](https://github.com/aixisstudio/Snitch), firewall de aplicaciones open source.

## Licencia: MIT
