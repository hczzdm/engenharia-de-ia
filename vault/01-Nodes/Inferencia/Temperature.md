---
tipo: node
status: em-estudo
tags:
  - conceito
  - inferencia
  - llm
  - sampling
---

# 🌡️ Temperature

## 📖 Definição

Parâmetro utilizado durante a geração para modificar a distribuição
de probabilidades dos possíveis próximos tokens.

---

## 💡 Intuição

```text
Temperature baixa
        ↓
distribuição mais concentrada
        ↓
menor diversidade
````

```
Temperature alta
        ↓
distribuição mais espalhada
        ↓
maior diversidade
```

---

## 🧮 Relação com Softmax

Modelo simplificado:

```
                    e^(zi / T)
P(token_i) = ─────────────────────────
              Σ_j e^(zj / T)
```

Onde:

```
zi = logit
T  = temperature
```

---

## ⚠️ Importante

```
Temperature baixa
≠
verdade factual
```

Temperature altera diversidade e comportamento da geração.

Ela não verifica fatos.

---

## 🎯 Uso depende da tarefa

### Menor diversidade

Pode ser desejável em:

- classificação;
- extração;
- geração estruturada;
- tarefas com formato rígido.

### Maior diversidade

Pode ser útil em:

- brainstorming;
- ideação;
- exploração;
- escrita criativa.

---

## 🔬 Avaliação

Temperature deve ser tratada como uma variável experimental.

```
Temperature
    ↓
Execuções
    ↓
Métricas
    ↓
Comparação
```

---

## 🔗 Relações

### Conceitos anteriores

- [[Logit]]
- [[Softmax]]

### Conceitos relacionados

- [[Sampling]]
- [[Não determinismo]]
- [[Distribuição de Probabilidade]]

### Conceitos posteriores

- [[Top-K]]
- [[Top-P]]
- [[Beam Search]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]

---

## 🧪 Laboratórios relacionados

- [[LAB 01 - Primeira chamada LLM]]