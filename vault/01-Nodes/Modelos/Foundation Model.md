---
tipo: node
status: em-estudo
tags:
  - conceito
  - arquitetura
  - design-patterns
---

# 🧩 Foundation Model 
## 📖 Definição 
Modelo treinado em grandes conjuntos de dados gerais e capaz de servir como base para diferentes tarefas, aplicações e adaptações. 
---
## 💡 Intuição
Um foundation model funciona como uma fundação. Em vez de criar um novo modelo para cada tarefa, utilizamos uma base geral e construímos diferentes aplicações sobre ela. 

## ⚙️ Como funciona?

Modelo mental simplificado:

```
Dados
  ↓
Tokenização
  ↓
Pretraining
  ↓
Base Model
```

==No caso dos LLMs, durante o pretraining o modelo aprende padrões existentes==  
==nos dados e desenvolve a capacidade de prever próximos tokens a partir==  
==de um contexto.==

---

## 🎯 Por que existe?

Treinar um modelo do zero para cada aplicação pode ser extremamente caro,  
demorado e exigir grandes quantidades de dados.

Foundation models permitem reutilizar capacidades gerais previamente  
aprendidas.

---

## 🆚 Foundation Model vs modelo específico

### Modelo específico

```
Modelo
  ↓
Tarefa delimitada
```

### Foundation Model

```
Foundation Model
       │
       ├── Tarefa A
       ├── Tarefa B
       ├── Tarefa C
       └── Tarefa D
```

---

## ⚠️ Limitações

Foundation models podem:

- possuir conhecimento desatualizado;
- desconhecer dados privados;
- produzir respostas incorretas;
- apresentar não determinismo;
- alucinar;
- possuir limitações específicas.

---

## 🔗 Relações

### Conceitos anteriores

- [[AI Engineering]]

### Conceitos relacionados

- [[LLM]]
- [[Base Model]]
- [[Pretraining]]
- [[Token]]
- [[Tokenizer]]

### Conceitos posteriores

- [[Prompt]]
- [[In-context Learning]]
- [[Post-training]]
- [[RAG]]
- [[Agente]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]