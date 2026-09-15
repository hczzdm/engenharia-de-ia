---
tipo: node
status: em-estudo
tags:
  - conceito
  - aplicacao-genai
  - ai-engineering
---
# 🧩 Aplicação de IA Generativa
## 📖 Definição 
Sistema de software que utiliza um modelo generativo como um de seus componentes para executar uma ou mais tarefas. --- 
## 💡 Intuição 
Uma aplicação GenAI não é apenas um LLM. 
```text 
Modelo + Dados + Contexto + Regras + Avaliação + Segurança + Infraestrutura = Aplicação GenAI
```

## 🧠 Modelo mental

```
Usuário
   ↓
Aplicação
   │
   ├── regras
   ├── contexto
   ├── dados
   ├── ferramentas
   │
   ▼
Foundation Model
   │
   ▼
Validação
   │
   ▼
Resposta
```

---

## 🆚 Protótipo vs Produção

### Protótipo

Busca demonstrar:

> o modelo possui capacidade para realizar determinada tarefa?

### Produção

Precisa considerar também:

- confiabilidade;
- consistência;
- custo;
- latência;
- avaliação;
- segurança;
- observabilidade;
- manutenção.

---

## ⚠️ Limitações

Aplicações construídas sobre foundation models herdam características  
e limitações desses modelos.

Entre elas:

- não determinismo;
- alucinação;
- conhecimento incompleto;
- limitações de contexto;
- custo de inferência;
- latência.

---

## 🔗 Relações

### Conceitos anteriores

- [[Foundation Model]]
- [[AI Engineering]]

### Conceitos relacionados

- [[Design Pattern]]
- [[Não determinismo]]
- [[Alucinação]]
- [[Avaliação]]
- [[Observabilidade]]

### Conceitos posteriores

- [[RAG]]
- [[Tool Calling]]
- [[Agente]]
- [[Guardrails]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]
