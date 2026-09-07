---
tipo: aula
capitulo: 1
numero: 1
status: em-andamento
tags:
  - aula
  - ai-engineering
  - design-patterns
  - foundation-models
---

# Aula 01 — Design Patterns e AI Engineering

> [!QUESTION] Pergunta central
> Por que utilizar um LLM não é a mesma coisa que construir um sistema de IA?

---

## 🎯 Objetivos

Ao final desta aula, devo ser capaz de:

- explicar o que é AI Engineering;
- diferenciar um protótipo GenAI de uma aplicação em produção;
- explicar por que um foundation model não é a aplicação completa;
- entender por que problemas recorrentes de GenAI exigem soluções de engenharia;
- compreender por que design patterns aparecem como resposta a esses problemas;
- reconhecer limitações como não determinismo e alucinação.

---

## 🗺️ Mapa da aula

```text
Foundation Model
      ↓
AI Engineering
      ↓
Aplicação GenAI
      ↓
Problemas recorrentes
      ↓
Design Patterns
```

---

## 🧩 Conceitos-chave

- [[AI Engineering]]
- [[Design Pattern]]
- [[Foundation Model]]
- [[Aplicação de IA Generativa]]
- [[Não determinismo]]
- [[Alucinação]]

---

# 🧱 Bloco 1 — O que é AI Engineering?

## 💡 Ideia central

> [!NOTE]
> Criar um protótipo utilizando IA generativa pode ser simples.

Uma aplicação mínima pode parecer algo assim:

```python
resposta = llm("Explique árvores binárias")
print(resposta)
```

Se o modelo responder corretamente, já temos uma demonstração funcional.

==Porém, isso ainda não significa que temos um sistema pronto para produção.==

Quando a aplicação passa a atender usuários reais, novas perguntas aparecem:

- a resposta é confiável?
- o modelo pode alucinar?
- ele responde sempre da mesma forma?
- quanto custa cada execução?
- qual é a latência?
- como avaliamos a qualidade da resposta?
- como atualizamos o conhecimento usado pelo sistema?
- como protegemos dados e usuários?
- como observamos o comportamento do sistema em produção?

O problema deixa de ser apenas:

> "Como chamar um modelo?"

E passa a ser:

> "Como construir um sistema confiável em torno de um modelo?"

---

## 📖 Definição de AI Engineering

AI Engineering é a prática de construir aplicações e sistemas utilizando foundation models previamente treinados como componentes centrais.

==A diferença importante é que, em muitos casos, não precisamos treinar um modelo específico do zero.==

Podemos utilizar um modelo geral e construir ao redor dele os componentes necessários para resolver um problema real.

---

## 🧠 Modelo mental

```text
                FOUNDATION MODEL
                       │
                       ▼
                    PROMPT
                       │
                       ▼
                   CONTEXTO
                       │
                       ▼
                  APLICAÇÃO
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
    Avaliação      Segurança     Observabilidade
        │              │              │
        └──────────────┼──────────────┘
                       ▼
                    PRODUÇÃO
```

---

## 🧩 O modelo não é a aplicação

==GPT, Claude, Gemini, Llama ou outro foundation model não representam, sozinhos, o sistema completo.==

O modelo é um componente.

Uma aplicação real pode conter:

```text
Interface
   │
   ▼
Regras da aplicação
   │
   ▼
Contexto / Dados
   │
   ▼
Foundation Model
   │
   ▼
Validação
   │
   ▼
Segurança
   │
   ▼
Observabilidade
   │
   ▼
Usuário
```

Uma forma simples de guardar essa ideia é:

```text
LLM ≠ Aplicação
```

E sim:

```text
LLM ∈ Aplicação
```

---

## 🏭 Protótipo vs Produção

### Protótipo

A pergunta principal costuma ser:

> O modelo conseguiu realizar a tarefa?

Exemplo:

```python
resposta = llm("Resuma este texto.")
```

Se a resposta parecer boa, o protótipo pode ser considerado promissor.

### Produção

A pergunta muda:

> O sistema consegue realizar essa tarefa de forma suficientemente confiável, segura, econômica e avaliável para usuários reais?

Agora precisamos considerar:

- qualidade;
- consistência;
- custo;
- latência;
- segurança;
- privacidade;
- avaliação;
- manutenção;
- mudanças de modelo;
- observabilidade.

---

## 🔄 Mudança de mentalidade

### Mentalidade de demonstração

```text
"O modelo respondeu?"
```

### Mentalidade de engenharia

```text
"O sistema funciona de maneira suficientemente boa,
previsível, econômica, segura e avaliável para o problema?"
```

---

## 🧪 Exemplo

Imagine um sistema educacional que responde perguntas de alunos.

O protótipo pode responder:

> "A derivada de x² é 2x."

Isso parece ótimo.

Mas um AI Engineer ainda pergunta:

- ele acerta outras perguntas?
- ele pode inventar referências?
- como sabemos se a resposta está correta?
- qual modelo produziu essa resposta?
- qual prompt foi utilizado?
- quanto custou?
- qual foi a latência?
- o comportamento muda se o modelo for atualizado?
- o sistema sabe quando não possui informação suficiente?

---

## 🆚 AI Engineering vs treinamento de modelos

Uma forma simplificada de comparar:

### Machine Learning tradicional

```text
Problema
   ↓
Dataset
   ↓
Treinamento
   ↓
Modelo específico
   ↓
Aplicação
```

### AI Engineering

```text
Foundation Model
       ↓
Prompt + Contexto
       ↓
Componentes de engenharia
       ↓
Aplicação
       ↓
Produto
```

Essa comparação é apenas um modelo mental introdutório.

Os dois mundos podem se combinar.

---

## 🧩 Conceitos deste bloco

- [[AI Engineering]]
- [[Foundation Model]]
- [[Aplicação de IA Generativa]]
- [[Não determinismo]]
- [[Alucinação]]

---

## ✍️ Minha compreensão

> TODO: preencher com minhas próprias palavras.

Tente responder:

1. O que diferencia usar um LLM de fazer AI Engineering?
2. Por que o modelo não é a aplicação completa?
3. O que muda quando saímos de um protótipo e vamos para produção?

---

## 🧠 Exemplo com minhas palavras

> TODO: criar um exemplo próprio.

Sugestão: escolher algum sistema que eu conheça e explicar:

```text
modelo
+
dados
+
regras
+
avaliação
+
segurança
=
aplicação
```

---

## ❓ Dúvidas deste bloco

- TODO
- TODO

---

# 🧱 Bloco 2 — O que é um Design Pattern?

## 🎯 Pergunta central

> [!NOTE]
> Se diferentes aplicações de IA encontram repetidamente os mesmos problemas, por que deveríamos inventar uma solução nova todas as vezes?

---

## 💡 Ideia central

> [!NOTE]
> Design patterns são soluções conhecidas e reutilizáveis para problemas recorrentes de engenharia. Eles não representam uma implementação específica. Representam uma forma reconhecida de pensar e resolver determinado tipo de problema.

---

## 🧠 De onde vem essa ideia?

Design patterns não nasceram com Inteligência Artificial.

Na engenharia de software, patterns surgem da identificação de problemas que aparecem repetidamente em sistemas diferentes.

Com o tempo, certas estratégias de solução se mostram úteis em vários contextos.

Essas estratégias recebem nomes e passam a formar um vocabulário comum entre engenheiros.

---

## 🔁 Problemas recorrentes

Imagine diferentes equipes desenvolvendo aplicações com LLMs.

Uma equipe encontra:

```text
"O modelo não retorna o formato esperado."
```

Outra encontra:

```text
"O modelo não conhece nossos documentos internos."
```

Outra:

```text
"O modelo produz informações sem fundamento."
```

Outra:

```text
"O sistema precisa permitir que o modelo consulte uma API."
```

Esses problemas não pertencem apenas a uma aplicação.

Eles reaparecem.

Portanto, podemos começar a pensar:

```text
Sintoma
   ↓
Problema recorrente
   ↓
Pattern conhecido
   ↓
Solução arquitetural
```

---

## 🧩 Pattern não é código pronto

Um design pattern não é simplesmente uma função que copiamos.

Não é:

```python
def resolver_problema():
    ...
```

Um pattern descreve uma estratégia.

A implementação pode mudar completamente.

Exemplo conceitual:

```text
PROBLEMA

O modelo não possui acesso ao conhecimento privado da organização.

        ↓

PATTERN

RAG

        ↓

IMPLEMENTAÇÃO POSSÍVEL

Retriever
+
Base documental
+
Embeddings
+
LLM
```

Podemos implementar o mesmo pattern com tecnologias diferentes.

Exemplo:

```text
RAG
 │
 ├── PostgreSQL + pgvector
 ├── Pinecone
 ├── Weaviate
 ├── outro banco vetorial
 └── outro mecanismo de recuperação
```

O pattern continua sendo RAG.

---

## 🆚 Pattern vs Framework

Essa diferença será fundamental durante todo o curso.

### Design Pattern

É uma estratégia arquitetural para resolver um problema recorrente.

### Framework

É uma ferramenta que pode ajudar a implementar essa estratégia.

Exemplo:

```text
Pattern
   ↓
Tool Calling
```

Pode ser implementado com:

```text
OpenAI SDK
PydanticAI
LangChain
código próprio
outro framework
```

Se uma biblioteca desaparecer amanhã, o problema continua existindo e o pattern continua válido.

---

## 🗣️ Pattern como vocabulário de engenharia

Design patterns também ajudam engenheiros a conversar.

Sem um vocabulário compartilhado, alguém poderia dizer:

> "Vamos pegar a pergunta, buscar documentos semanticamente parecidos, colocar os trechos encontrados no contexto do modelo e pedir a resposta."

Com um vocabulário comum:

> "Vamos utilizar RAG."

O nome do pattern carrega uma grande quantidade de conhecimento arquitetural.

Ao longo desta trilha encontraremos termos como:

- Basic RAG;
- Reflection;
- Tool Calling;
- Prompt Caching;
- Guardrails;
- Multiagent Collaboration.

A meta não é apenas decorar esses nomes.

A meta é reconhecer:

> Qual problema fez esse pattern existir?

---

## 🏗️ Como o livro organiza os patterns

O livro apresenta 32 design patterns.

Eles são agrupados por tipos de problemas encontrados na construção de aplicações GenAI.

A estrutura de cada pattern normalmente parte de:

```text
Problema
   ↓
Solução
   ↓
Exemplo funcional
   ↓
Alternativas
   ↓
Considerações
```

Essa estrutura também será utilizada em nossa trilha.

---

## 🔬 Nosso método para estudar cada pattern

Para cada design pattern, responderemos:

1. Qual é o problema?
2. Por que esse problema acontece?
3. Qual é a solução proposta pelo pattern?
4. Como o pattern funciona?
5. Como podemos implementá-lo?
6. Como testar se ele realmente funcionou?
7. Quais métricas podemos utilizar?
8. Quais são os trade-offs?
9. Quais alternativas existem?
10. Quando NÃO devemos usar esse pattern?

Nosso fluxo será:

```text
Problema
   ↓
Hipótese
   ↓
Pattern
   ↓
Implementação
   ↓
Experimento
   ↓
Métrica
   ↓
Resultado
   ↓
Conclusão
```

---

## ⚖️ Pattern não é regra universal

Um pattern não significa:

> "Sempre utilize esta solução."

Significa:

> "Existe uma solução conhecida para este tipo de problema."

Antes de aplicá-la, precisamos avaliar:

- contexto;
- requisitos;
- custo;
- complexidade;
- riscos;
- alternativas;
- benefícios.

Às vezes a melhor decisão será:

> não utilizar o pattern.

---

## 🚨 O erro da tecnologia procurando problema

Durante esta trilha queremos evitar:

```text
Tecnologia nova
       ↓
"Que legal!"
       ↓
Onde consigo colocar isso?
```

Vamos preferir:

```text
Problema
   ↓
Requisitos
   ↓
Pattern
   ↓
Tecnologia
```

Exemplo ruim:

```text
"Quero usar multiagentes."
```

Pergunta correta:

```text
"Que problema exige múltiplos agentes?"
```

Outro exemplo:

```text
"Quero usar GraphRAG."
```

Pergunta correta:

```text
"Qual limitação do retrieval atual justifica GraphRAG?"
```

---

## 🧠 Regra mental

Antes de escolher qualquer tecnologia:

> Qual problema estamos tentando resolver?

---

## 🧪 Exemplo simples

Imagine que uma API espera:

```json
{
  "nome": "Maria",
  "idade": 24
}
```

Mas o modelo responde:

```text
Claro! Maria possui 24 anos.
```

O problema não é simplesmente:

> "O modelo respondeu errado."

O problema de engenharia é:

> precisamos controlar o formato da saída.

A partir disso podemos procurar patterns adequados para controle de geração.

O raciocínio deve ser:

```text
Sintoma
   ↓
Problema
   ↓
Pattern
   ↓
Implementação
```

E não:

```text
Sintoma
   ↓
Prompt aleatório número 47
```

---

## 🔗 Relação com AI Engineering

```text
AI Engineering
      ↓
Problemas recorrentes
      ↓
Design Patterns
      ↓
Soluções arquiteturais
      ↓
Aplicações mais robustas
```

AI Engineering nos coloca diante dos problemas.

Design patterns nos oferecem uma linguagem para reconhecer e abordar alguns desses problemas.

---

## 🧩 Conceitos deste bloco

- [[Design Pattern]]
- [[AI Engineering]]
- [[Problema Recorrente]]
- [[Framework]]
- [[Trade-off]]
- [[Arquitetura de Software]]

---

# 🧱 Bloco 3 — O que é um Foundation Model?

## 🎯 Pergunta central

O que exatamente estamos chamando de "modelo base" sobre o qual fazemos AI Engineering?

---

## 💡 Ideia central

Um foundation model é um modelo treinado em grandes conjuntos de dados, de maneira geral e não específica para uma única aplicação.

Ele funciona como uma base sobre a qual diferentes tarefas, aplicações e sistemas podem ser construídos.

---

## 🆚 Modelo específico vs Foundation Model

### Modelo específico

```text
Dataset específico
      ↓
Treinamento
      ↓
Modelo específico
      ↓
Uma tarefa
```

A diferença fundamental é:

> Um foundation model não é criado exclusivamente para uma única aplicação.

Ele aprende capacidades gerais que posteriormente podem ser reutilizadas.

---

## 🏗️ Por que isso muda AI Engineering?

Em uma visão simplificada de Machine Learning tradicional:

```text
Nova tarefa
   ↓
Novo dataset
   ↓
Novo treinamento
   ↓
Novo modelo
```

Com foundation models, em muitas situações podemos ter:

```text
Nova tarefa
   ↓
Novo prompt / contexto
   ↓
Mesmo foundation model
```

Isso permite criar várias aplicações sem treinar um novo modelo do zero para cada problema.

---

## 🧠 Pretraining

Uma das etapas fundamentais de criação de um LLM é o pretraining.

Modelo mental:

```text
Dados
  ↓
Tokenização
  ↓
Pretraining
  ↓
Base Model
```

Durante o pretraining, o modelo aprende padrões existentes nos dados.

Um objetivo central dos LLMs é prever o próximo token a partir do contexto anterior.

Exemplo conceitual:

```text
"Hoje o céu está..."
        ↓
      modelo
        ↓
 ┌──────┼───────┐
 azul  nublado  escuro
```

O modelo não produz apenas uma palavra pronta.

Ele trabalha com possibilidades de próximos tokens.

Esse assunto será aprofundado posteriormente quando estudarmos:

- [[Logit]]
- [[Softmax]]
- [[Temperature]]
- [[Top-K]]
- [[Top-P]]

---

## 🔤 Tokens

LLMs trabalham com tokens, e não diretamente com palavras completas.

Modelo simplificado:

```text
Texto
  ↓
Tokenizer
  ↓
Tokens
  ↓
Modelo
```

Na saída:

```text
Modelo
  ↓
Tokens
  ↓
Texto
```

Tokens são importantes porque influenciam:

- tamanho do contexto;
- custo;
- velocidade;
- geração;
- limites da API.

---

## 🧪 Base Model não é necessariamente um Assistant

Depois do pretraining, podemos ter um modelo com capacidades gerais.

Mas isso não significa automaticamente que ele seja bom em:

- seguir instruções;
- conversar;
- produzir respostas úteis;
- seguir preferências humanas.

Por isso podem existir etapas adicionais.

Modelo mental simplificado:

```text
Pretraining
   ↓
Base Model
   ↓
Supervised Fine-Tuning
   ↓
Preference Optimization
   ↓
Modelo orientado a instruções
```

Essas etapas serão estudadas com mais profundidade posteriormente.

---

## 🌐 Foundation Model vs LLM

Os conceitos se relacionam, mas não são exatamente sinônimos.

### LLM

Large Language Model.

Modelo de grande escala especializado em linguagem.

### Foundation Model

Categoria mais ampla de modelos gerais que podem servir como base para diversas aplicações.

Um foundation model pode trabalhar com:

- texto;
- imagem;
- áudio;
- vídeo;
- múltiplas modalidades.

Muitos LLMs modernos são também foundation models.

---

## ⚠️ Foundation Model não significa "modelo que sabe tudo"

Mesmo modelos muito poderosos podem:

- possuir conhecimento desatualizado;
- desconhecer dados privados;
- produzir informações incorretas;
- alucinar;
- apresentar não determinismo;
- falhar em tarefas específicas.

Essas limitações são justamente uma das razões pelas quais precisamos de AI Engineering e Design Patterns.

---

## 🔗 Relação com AI Engineering

Podemos guardar este modelo:

```text
Foundation Model
      =
Capacidade geral

AI Engineering
      =
Transformar essa capacidade
em um sistema utilizável
```

Ou:

```text
Foundation Model
       ↓
Prompt + Contexto
       ↓
Componentes de Engenharia
       ↓
Aplicação
       ↓
Produto
```

---

## 🧩 Conceitos deste bloco

- [[Foundation Model]]
- [[Base Model]]
- [[LLM]]
- [[Pretraining]]
- [[Token]]
- [[Tokenizer]]
- [[Supervised Fine-Tuning]]
- [[Preference Tuning]]

---

## 📚 Referência principal

Lakshmanan, Valliappa; Hapke, Hannes.  
*Generative AI Design Patterns*.  
O'Reilly Media.

Capítulo 1 — Introduction.

---

## 🧪 Laboratório

[[LAB 01 - Primeira chamada LLM]]

---

## ➡️ Próxima aula

[[Aula 02 - Prompts e Contexto]]
