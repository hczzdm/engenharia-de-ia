---
tipo: node
status: em-estudo
tags:
  - conceito
  - inferencia
  - llm
  - nao-determinismo
---
# 🎲 Não determinismo 
## 📖 Definição 
Característica de um sistema no qual execuções aparentemente iguais podem produzir saídas diferentes. --- 
## 💡 Intuição 
Um LLM não escolhe necessariamente uma única resposta fixa. Durante a geração, ele trabalha com distribuições de possíveis próximos tokens. 
```text 
Contexto 
↓ 
Modelo 
↓ 
Possíveis tokens 
↓ 
Seleção 
↓ 
Novo contexto
```

## ⚙️ Como acontece?

Modelo mental simplificado:

```
Prompt
  ↓
Logits
  ↓
Probabilidades
  ↓
Sampling
  ↓
Token
  ↓
Novo contexto
  ↓
Repetir
```

---

## 🆚 Determinístico vs não determinístico

### Determinístico

```
mesma entrada
     ↓
mesma saída
```

### Não determinístico

```
mesma entrada
     ↓
distribuição de possibilidades
     ↓
saídas potencialmente diferentes
```

---

## 🎲 Não significa aleatoriedade total

Os tokens não possuem necessariamente a mesma probabilidade.

Exemplo:

```
A → 70%
B → 20%
C → 8%
D → 2%
```

Portanto:

```
não determinismo
≠
todas as respostas são igualmente prováveis
```

---

## ⚠️ Por que importa?

Pode afetar:

- consistência;
- avaliação;
- automações;
- APIs;
- geração estruturada;
- testes;
- agentes;
- reprodutibilidade.

---

## 🧪 Como avaliar?

Executar o mesmo caso várias vezes:

```
Prompt
   ↓
R1
R2
R3
R4
R5
   ↓
comparação
```

E medir:

- consistência;
- formato;
- conteúdo;
- erros;
- latência;
- tokens.

---

## 🔗 Relações

### Conceitos anteriores

- [[Foundation Model]]
- [[Aplicação de IA Generativa]]

### Conceitos relacionados

- [[Logit]]
- [[Softmax]]
- [[Sampling]]
- [[Temperature]]
- [[Token]]

### Conceitos posteriores

- [[Top-K]]
- [[Top-P]]
- [[Avaliação]]
- [[Alucinação]]
- [[Structured Output]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]

---

## 🧪 Laboratórios relacionados

- [[LAB 01 - Primeira chamada LLM]]