---
tipo: node
status: em-estudo
tags:
  - conceito
  - agentes
  - autonomia
  - seguranca
---

# 🤖 Autonomia

## 📖 Definição

Grau de liberdade concedido a um agente para tomar decisões
e executar ações sem intervenção humana.

---

## 💡 Intuição

Autonomia não é binária.

Um sistema pode possuir diferentes graus de liberdade.

```text
assistir
   ↓
recomendar
   ↓
agir com aprovação
   ↓
agir autonomamente
````

---

## 🎚️ Níveis

### Assistência

O sistema produz informação.

### Recomendação

O sistema sugere uma ação.

### Aprovação humana

O sistema prepara a ação e aguarda autorização.

### Autonomia limitada

O sistema executa ações dentro de regras definidas.

### Autonomia ampla

O sistema pode planejar e executar sequências complexas.

---

## ⚠️ Trade-off

```
mais autonomia
     ↓
mais capacidade
     +
mais risco
     +
mais necessidade de controle
```

---

## 🛡️ Controles possíveis

- permissões;
- limites de passos;
- limites de custo;
- aprovação humana;
- logging;
- validação;
- restrição de ferramentas;
- condições de parada.

---

## 🔑 Menor privilégio

Um agente deve receber apenas as permissões necessárias  
para executar sua tarefa.

---

## 🔗 Relações

### Conceitos anteriores

- [[Agente]]
- [[Não determinismo]]

### Conceitos relacionados

- [[Human-in-the-loop]]
- [[Princípio do Menor Privilégio]]
- [[Tool Calling]]
- [[Observabilidade]]

### Conceitos posteriores

- [[Guardrails]]
- [[Code Execution]]
- [[Multiagent Collaboration]]

---

## 📘 Aulas relacionadas

- [[Aula 01 - Design Patterns e AI Engineering]]