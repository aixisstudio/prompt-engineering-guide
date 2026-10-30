# Prompt Engineering Guide

[English](README.md) | **Français** | [Español](README.es.md) | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

Prompt engineering, de zéro aux techniques avancées

Niveau

1. Effacer les instructions
Mauvais : "Écris quelque chose sur les chiens." → Bon : "Écris un paragraphe de 150 mots pour le site d'un vétérinaire rassurant les propriétaires sur l'anesthésie."

Quelques photos
Donnez 2-3 exemples d'entrée/sortie avant votre entrée réelle — le modèle imite le modèle.

3. Persona + contexte
"Vous êtes un SRE senior qui examine un style postmortem..." cadres, profondeur et vocabulaire.

4. Structure et délimiteurs
Utilisez des balises XML-ish (`<context>…</context>`, `<task>…</task>`) — les modèles les analysent de façon fiable.

5. Chaîne de pensée
"Pensez pas à pas" — ou mieux : demandez explicitement à *planifier d'abord, puis répondez*.

6. Sortie forcée
Spécifier le format : schéma JSON, table de marquage, longueur exacte. Vérifier les programmes.

7. Boucle autocritique
"Projet → critiquez votre projet → produire la finale." Une étape supplémentaire, un saut de grande qualité.

8. Utilisation des outils et RAG
Donnez au modèle des fonctions de récupération + au lieu d'espérer qu'il le sait — le plus grand levier de fiabilité.

Modes de défaillance
- **Objectifs Vague** → sortie vague
- **Conflicting instructions** → le modèle choisit silencieusement
- **Assurer la certitude** sur des sujets incertains → hallucinations; préférer "dire quand vous ne savez pas"
- **Injection rapide** — ne jamais concaténer le texte non fiable de l'utilisateur dans les appels système

Références
- Guide rapide anthropique · Livre de cuisine OpenAI · Guide technique rapide
- Pratique: `ai-prompts-hub` (ceci org) — ajouter et parcourir les instructions réelles

Modèles avancés

La chaîne de vérification (CoVe)
1. Projet de réponse → 2. Générer des questions de vérification → 3. Réponse indépendante → 4. Réviser. Cuts hallucination dramatiquement.

L'auto-cohérence
Échantillonner le même CoT prompt 5-10× à la température 0,7, vote la majorité de la réponse. +10-20% sur les repères de raisonnement.

### Réaction (Loi sur la raison + Loi)
Interleave `Thought:` / `Action:` / `Observation:` — l'épine dorsale des agents utilisateurs d'outils.

#### Squelette de Thought
D'abord générer un contour, puis répondre à chaque point *en parallèle*. Plus rapide + plus structuré.

Points de référence à connaître

Tests de référence
|---|---|
MMLU / MMLU-Pro
HumanEval / SWE-bench
Raisonnement
IF-Eval Instruction suivant
L'intelligence émotionnelle

Première injection rapide

- L'entrée de l'utilisateur n'est jamais un contexte de confiance — délimiter + instruire le modèle
- Les outils/RAG peuvent contenir des instructions : traiter le texte récupéré comme non fiable
- Défense en profondeur : validation de sortie > durcissement rapide

---
## Contribuer

Les pull requests sont les bienvenues : ouvre une PR, elle sera relue et fusionnée. Maintenu par [aixisstudio](https://github.com/aixisstudio), auteur de [Snitch](https://github.com/aixisstudio/Snitch), pare-feu applicatif open source.

## Licence: MIT
