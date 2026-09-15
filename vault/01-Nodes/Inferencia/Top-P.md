---
tipo: node
status: em-estudo
tags:
  - conceito
  - inferencia
  - sampling
  - nucleus-sampling
---

# 🎯 Top-P

## 📖 Definição

Estratégia de sampling que seleciona o menor conjunto de tokens
cuja probabilidade acumulada atinge um limite P.

Também é conhecida como:

[[Nucleus Sampling]]

---

## 💡 Intuição

```text
Tokens ordenados
      ↓
Somar probabilidades
      ↓
Parar quando atingir P
      ↓
Sampling
````

---

## 🧪 Exemplo

```
A → 50%
B → 25%
C → 15%
D → 10%
```

Com:

```
P = 0.75
```

mantemos:

```
A
B
```

pois:

```
50% + 25% = 75%
```

---

## 🆚 Top-P vs Top-K

Top-K:

> quantidade fixa de candidatos.

Top-P:

> quantidade variável baseada na massa acumulada de probabilidade.

---

## ⚠️ Importante

Top-P controla a geração.

Não verifica factualidade.

---

## 🔗 Relações

- [[Top-K]]
- [[Nucleus Sampling]]
- [[Sampling]]
- [[Temperature]]
- [[Softmax]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]