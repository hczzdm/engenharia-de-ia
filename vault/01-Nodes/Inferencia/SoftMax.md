---
tipo: node
status: em-estudo
tags:
  - conceito
  - inferencia
  - probabilidade
---

---

# 📊 Softmax

## 📖 Definição

Função que transforma um conjunto de valores reais em uma distribuição
normalizada de probabilidades.

---

## 🧮 Fórmula

```text
                 e^zi
P(token_i) = ─────────────
              Σ_j e^zj 
```

## 💡 Intuição

```
Logits
   ↓
Softmax
   ↓
Valores positivos
   +
soma aproximadamente 1
```

---

## 🧪 Exemplo

```
Logits:

A → 2
B → 1
C → 0
```

Softmax aproximadamente:

```
A → 0.665
B → 0.245
C → 0.090
```

---

## ⚠️ Importante

A probabilidade calculada representa:

> quão provável é aquele token como continuação segundo o modelo.

Não representa necessariamente:

> probabilidade de a informação ser verdadeira.

---

## 🔗 Relações

- [[Logit]]
- [[Distribuição de Probabilidade]]
- [[Sampling]]
- [[Argmax]]
- [[Temperature]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]