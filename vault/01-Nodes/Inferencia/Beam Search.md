---
tipo: node
status: em-estudo
tags:
  - conceito
  - inferencia
  - decoding
---

# 🔦 Beam Search

## 📖 Definição

Estratégia de decoding que mantém várias sequências candidatas
simultaneamente e expande os caminhos mais promissores.

---

## 💡 Intuição

Em vez de:

```text
escolher um caminho
        ↓
seguir até o fim
````

fazemos:

```
manter vários caminhos
        ↓
comparar
        ↓
expandir melhores
        ↓
repetir
```

---

## 🔢 Beam Width

Representa quantas sequências candidatas são mantidas.

```
beam width = K
```

significa:

> manter até K candidatos principais em cada etapa.

---

## 🆚 Greedy Search

Greedy:

```
melhor token agora
```

Beam Search:

```
melhores sequências candidatas
```

---

## ⚠️ Trade-off

Beam maior pode aumentar exploração, mas também aumenta:

- computação;
- memória;
- latência;
- custo.

---

## 🔗 Relações

- [[Greedy Search]]
- [[Sampling]]
- [[Beam Width]]
- [[Top-K]]
- [[Top-P]]
- [[Decoding]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]