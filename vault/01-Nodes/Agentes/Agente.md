---
tipo: node
status: em-estudo
tags:
  - conceito
  - agentes
  - agentic-ai
---

# 🤖 Agente

## 📖 Definição

Sistema orientado a objetivos capaz de ==perceber informações==,
==tomar decisões== e executar ações ==sobre um ambiente==.

---

## 💡 Intuição

Um LLM responde.

Um agente pode usar um LLM para decidir o que fazer a seguir.

```text
Objetivo
   ↓
Percepção
   ↓
Decisão
   ↓
Ação
   ↓
Feedback
````

---

## 🧩 Componentes

Um agente pode possuir:

- objetivo;
- modelo;
- contexto;
- estado;
- ferramentas;
- memória;
- mecanismos de planejamento;
- mecanismos de controle.

---

## 🔄 Loop agêntico

```
Observar
   ↓
Planejar
   ↓
Agir
   ↓
Observar
   ↺
```

---

## 🆚 Agente vs LLM

### LLM

```
entrada
  ↓
modelo
  ↓
saída
```

### Agente

```
objetivo
   ↓
LLM
   ↓
decisão
   ↓
ferramenta
   ↓
resultado
   ↓
nova decisão
```

---

## ⚠️ Autonomia

==Um agente pode possuir diferentes níveis de autonomia.==

Ações sensíveis podem exigir:

[[Human-in-the-loop]]

---

## 🔗 Relações

### Conceitos anteriores

- [[Foundation Model]]
- [[Aplicação de IA Generativa]]
- [[Não determinismo]]

### Conceitos relacionados

- [[Planejamento]]
- [[Tool Calling]]
- [[Estado]]
- [[Memória]]
- [[Autonomia]]

### Conceitos posteriores

- [[Aplicação Agêntica]]
- [[Code Execution]]
- [[Multiagent Collaboration]]
- [[Long-Term Memory]]
- [[Guardrails]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]