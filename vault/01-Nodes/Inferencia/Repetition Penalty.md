---
tipo: node
status: em-estudo
tags:
  - conceito
  - inferencia
  - decoding
---

# 🔁 Repetition Penalty

## 📖 Definição

Mecanismo que reduz a preferência por tokens que já apareceram,
com o objetivo de diminuir repetições indesejadas durante a geração.

---

## 💡 Intuição

```text
Token já utilizado
       ↓
aplicar penalidade
       ↓
menor preferência
````

---

## ⚠️ Cuidado

Penalidade excessiva pode fazer o modelo evitar repetições necessárias.

Portanto:

```
mais penalidade
≠
sempre melhor
```

---

## 🔗 Relações

- [[Beam Search]]
- [[Sampling]]
- [[Temperature]]
- [[Top-K]]
- [[Top-P]]
- [[Decoding]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]