---
tipo: node
status: em-estudo
tags:
  - conceito
  - confiabilidade
  - llm
  - alucinacao
---

# 👻 Alucinação

## 📖 Definição

Produção de informação falsa, inventada ou não sustentada apresentada
pelo modelo como parte de uma resposta aparentemente plausível.

---

## 💡 Intuição

Uma resposta pode parecer correta sem ser verdadeira.

```text
Fluência
   ≠
Verdade
````

E:

```
Confiança linguística
   ≠
Confiança factual
```

---

## ⚠️ Exemplos

- fatos inventados;
- referências inexistentes;
- autores incorretos;
- URLs inventadas;
- números não sustentados;
- conclusões não presentes nas evidências.

---

## 🎲 Alucinação vs não determinismo

### Não determinismo

Execuções iguais podem gerar respostas diferentes.

### Alucinação

A resposta contém informação falsa ou não sustentada.

```
Não determinismo
        ≠
Alucinação
```

---

## 🔍 Groundedness

Pergunta central:

> A resposta está sustentada pela evidência disponível?

```
Evidência
   ↓
Afirmações
   ↓
Resposta
```

---

## 🛡️ Mitigação

Possíveis estratégias incluem:

- fornecer contexto confiável;
- recuperar documentos;
- exigir citações;
- validar afirmações;
- permitir abstenção;
- avaliar groundedness;
- utilizar mecanismos de verificação.

Nenhuma dessas estratégias garante, isoladamente, eliminação total  
de alucinações.

---

## 🔗 Relações

### Conceitos anteriores

- [[Foundation Model]]
- [[Não determinismo]]

### Conceitos relacionados

- [[Groundedness]]
- [[Ground Truth]]
- [[Avaliação]]
- [[RAG]]

### Conceitos posteriores

- [[Trustworthy Generation]]
- [[Reflection]]
- [[Self-Check]]
- [[Guardrails]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]

---

## 🧪 Laboratórios relacionados

- [[LAB 01 - Primeira chamada LLM]]