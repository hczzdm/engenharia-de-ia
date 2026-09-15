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

# 🧱 Bloco 4 — Protótipo vs Produção em GenAI 
## 🎯 Pergunta central 
==Por que uma demonstração impressionante com um LLM ainda pode ser um sistema ruim para usuários reais?== 
## 💡 Ideia central
Em aplicações GenAI existe uma diferença importante entre: > conseguir fazer o modelo executar uma tarefa e: > construir um sistema capaz de executar essa tarefa de maneira confiável > em condições reais. 

Um protótipo demonstra possibilidade. ==Um sistema de produção precisa demonstrar comportamento aceitável.==
## 🧪 O protótipo 
Imagine: 
```
python resposta = llm( "Explique o que é regressão linear para um estudante iniciante." ) print(resposta)
```

A resposta parece excelente.

Podemos concluir:

> O modelo consegue executar essa tarefa.

Isso é uma evidência útil.

Mas ainda é apenas uma evidência sobre uma execução.

---

## 🔬 O problema de uma única execução

Imagine que executamos o mesmo sistema novamente:

```
Execução 01 → excelente
Execução 02 → boa
Execução 03 → incompleta
Execução 04 → contém uma informação errada
Execução 05 → excelente novamente
```

Agora aparece uma pergunta diferente:

> Qual é o comportamento real do sistema?

Uma única resposta boa não caracteriza todo o sistema.

---

## 🏭 Produção muda a unidade de análise

No protótipo podemos olhar para:

```
uma entrada
    ↓
uma resposta
```

Em produção precisamos olhar para:

```
muitas entradas
     ↓
muitas execuções
     ↓
muitos usuários
     ↓
distribuição de comportamentos
```

Portanto:

```
Protótipo
   ↓
"Funcionou?"
```

enquanto:

```
Produção
   ↓
"Com que frequência funciona?"
```

---

## 📊 De resposta para distribuição

Essa mudança é fundamental para sistemas probabilísticos.

Não queremos apenas saber:

> A resposta ficou boa?

Queremos saber:

```
Em 1.000 execuções:

quantas foram corretas?
quantas foram incompletas?
quantas alucinaram?
quantas excederam a latência esperada?
quantas quebraram o formato exigido?
quanto custaram?
```

A engenharia começa a sair da análise de uma resposta individual e  
passa para a análise de comportamento agregado.

---

## ⚠️ Novos problemas aparecem em produção

### 1. Qualidade

O sistema responde corretamente?

### 2. Consistência

Execuções semelhantes produzem resultados suficientemente consistentes?

### 3. Alucinação

O modelo produz informações não sustentadas?

### 4. Latência

Quanto tempo uma resposta leva?

### 5. Custo

Quanto custa operar o sistema em escala?

### 6. Segurança

O usuário consegue induzir comportamentos indesejados?

### 7. Privacidade

Quais dados estão sendo enviados ao modelo?

### 8. Observabilidade

Conseguimos investigar por que determinada resposta ocorreu?

### 9. Dependência do modelo

O que acontece quando:

- o provider muda;
- o modelo é atualizado;
- uma versão é descontinuada;
- os preços mudam?

### 10. Avaliação

Como sabemos objetivamente se uma nova versão ficou melhor?

---

## 🧠 Mudança de pergunta

### Desenvolvimento exploratório

```
O modelo consegue fazer isso?
```

### Engenharia de produção

```
Qual é a taxa de sucesso?

Qual é a taxa de falha?

Quais são os tipos de falha?

Quanto custa?

Quanto demora?

Como detectamos regressões?

Como mitigamos erros?
```

---

## 🧮 Exemplo: assistente acadêmico

Imagine um assistente que responde dúvidas sobre Ciência da Computação.

No protótipo:

```
Pergunta
   ↓
LLM
   ↓
Resposta aparentemente correta
```

Sucesso.

Em produção:

```
10.000 perguntas
      ↓
LLM
      ↓
┌──────────────┬───────────────┬─────────────┐
│ corretas     │ incompletas   │ incorretas  │
├──────────────┼───────────────┼─────────────┤
│ ?            │ ?             │ ?           │
└──────────────┴───────────────┴─────────────┘
```

Agora precisamos medir.

---

## 🔁 Mudança de escala

Outra diferença aparece quando aumentamos o número de usuários.

```
10 chamadas
```

podem parecer irrelevantes.

Mas:

```
100.000 chamadas por dia
```

transformam pequenas ineficiências em problemas reais.

Por exemplo:

```
R$ 0,01 por chamada
        ×
100.000 chamadas
        =
R$ 1.000 por dia
```

O mesmo acontece com latência, erros e falhas.

Uma taxa de erro aparentemente pequena pode se tornar importante em escala.

---

## 🎯 Protótipo prova capacidade

Podemos pensar:

```
Protótipo
   =
prova de capacidade
```

Ele responde:

> É possível fazer isso?

---

## 🏗️ Produção prova engenharia

```
Produção
   =
capacidade
+
confiabilidade
+
avaliação
+
controle
+
operação
```

Ela responde:

> Conseguimos sustentar esse comportamento em condições reais?

---

## 🧩 Onde entram os Design Patterns?

Os problemas começam a se repetir:

```
preciso controlar a saída
        ↓
pattern

preciso adicionar conhecimento
        ↓
pattern

preciso melhorar recuperação
        ↓
pattern

preciso avaliar respostas
        ↓
pattern

preciso permitir ações
        ↓
pattern

preciso reduzir custo
        ↓
pattern

preciso adicionar segurança
        ↓
pattern
```

É por isso que os design patterns se tornam importantes.

==Eles atacam problemas que surgem quando deixamos de tratar o LLM==  
==como uma demonstração isolada e começamos a construir sistemas reais.==

---

## 🧠 Modelo mental

```
Foundation Model
       ↓
Protótipo
       ↓
"Consegue fazer?"
       ↓
Experimentos
       ↓
Problemas recorrentes
       ↓
Design Patterns
       ↓
Avaliação
       ↓
Sistema de produção
```

---

## 🧩 Conceitos deste bloco

- [[Aplicação de IA Generativa]]
- [[AI Engineering]]
- [[Não determinismo]]
- [[Alucinação]]
- [[Avaliação]]
- [[Latência]]
- [[Custo de Inferência]]
- [[Observabilidade]] 

### Bloco 5 — Não determinismo

Pergunta central:

> Por que podemos fornecer a mesma entrada para um LLM e receber  
> respostas diferentes? 

## 🎯 Pergunta central
Por que podemos fornecer a mesma entrada para um LLM e receber respostas diferentes? --- 
## 💡 Ideia central
Em software tradicional, muitas funções são construídas para produzir sempre a mesma saída quando recebem exatamente a mesma entrada. Exemplo: 
```
python def dobro(x): return x * 2
````

Se executarmos:

```
dobro(10)
```

esperamos sempre:

```
20
```

Podemos representar:

```
mesma entrada
     ↓
mesma função
     ↓
mesma saída
```

Em aplicações com LLMs, essa expectativa nem sempre é válida.

Podemos ter:

```
mesmo prompt
     ↓
mesmo modelo
     ↓
execução 1 → resposta A
execução 2 → resposta B
execução 3 → resposta C
```

Esse comportamento é uma das razões pelas quais aplicações GenAI  
precisam ser avaliadas de maneira diferente do software determinístico  
tradicional.

---

## 🆚 Determinístico vs não determinístico

### Sistema determinístico

Para uma mesma entrada e um mesmo estado:

```
f(x) = y
```

Sempre esperamos:

```
x
↓
f
↓
y
```

### Sistema generativo

Em uma representação simplificada:

```
Prompt
   ↓
Modelo
   ↓
Distribuição de possibilidades
   ↓
Processo de seleção
   ↓
Resposta
```

A saída não precisa ser uma única sequência inevitável.

---

## 🧠 O modelo não escolhe uma frase inteira de uma vez

Um LLM gera texto progressivamente.

De forma simplificada:

```
contexto atual
      ↓
modelo
      ↓
possíveis próximos tokens
      ↓
seleção de um token
      ↓
novo contexto
      ↓
repetir
```

Exemplo:

```
"A capital do Brasil é"
```

O modelo calcula diferentes possibilidades para o próximo token.

Conceitualmente:

```
Brasília      → probabilidade alta
São           → probabilidade menor
Rio           → probabilidade menor
...
```

A geração acontece token por token.

---

## 🔢 Logits

Antes de termos probabilidades, o modelo produz valores numéricos  
chamados logits.

Modelo mental:

```
Contexto
   ↓
Modelo
   ↓
Logits
```

Exemplo conceitual:

```
Brasília → 8.3
Rio      → 2.1
São      → 1.7
Curitiba → 0.4
```

==Esses valores ainda não são probabilidades.==

==Eles representam pontuações produzidas pelo modelo para possíveis==  
==próximos tokens.==

---

## 📊 Softmax

Uma função como softmax pode transformar logits em uma distribuição  
de probabilidades.

```
Logits
   ↓
Softmax
   ↓
Distribuição de probabilidades
```

Exemplo conceitual:

```
Brasília → 0.92
Rio      → 0.04
São      → 0.03
Curitiba → 0.01
```

A soma das probabilidades é aproximadamente:

```
1.0
```

---

## 🎲 Onde aparece a variabilidade?

Se o sistema sempre escolhesse exclusivamente o token de maior  
probabilidade, teríamos um comportamento muito mais determinístico.

Mas mecanismos de geração podem realizar amostragem a partir da  
distribuição.

Imagine:

```
Token A → 60%
Token B → 25%
Token C → 10%
Token D → 5%
```

Em uma execução:

```
Token A
```

Em outra:

```
Token B
```

Depois desse token, o contexto muda.

E isso altera as probabilidades dos próximos tokens.

---

## 🦋 Pequena diferença, resposta inteira diferente

Imagine:

```
Prompt
   ↓
Token 1
   ↓
Token 2
   ↓
Token 3
   ↓
Token 4
```

Se na primeira execução ocorrer:

```
Token 2 = A
```

e na segunda:

```
Token 2 = B
```

os contextos já ficaram diferentes.

Então:

```
Execução 1
A → C → D → F → ...
```

pode divergir de:

```
Execução 2
B → E → G → H → ...
```

Uma pequena diferença inicial pode produzir respostas bastante  
diferentes algumas dezenas de tokens depois.

---

## 🌡️ Temperature

==A temperature controla como a distribuição dos próximos tokens é utilizada==  
==durante a geração.==

Modelo mental simplificado:

### Temperature baixa

```
distribuição mais concentrada
        ↓
tokens mais prováveis dominam
        ↓
menor diversidade
```

### Temperature alta

```
distribuição mais espalhada
        ↓
tokens menos prováveis ganham espaço
        ↓
maior diversidade
```

Podemos pensar:

```
Temperature ↓
   ↓
mais conservador
mais previsível
```

e:

```
Temperature ↑
   ↓
mais variado
mais criativo
```

==Isso não significa que temperature baixa garanta verdade ou correção.==

Ela altera principalmente o comportamento da geração.

---

## 🎯 Um cuidado importante

Não determinismo não significa:

> "o modelo responde qualquer coisa aleatoriamente."

Existe uma distribuição aprendida.

Algumas continuações são muito mais prováveis do que outras.

Portanto:

```
não determinismo
≠
caos completo
```

Uma representação melhor é:

```
distribuição probabilística
        +
processo de seleção
        ↓
variabilidade controlável
```

---

## 🧪 Exemplo prático

Prompt:

> Explique recursão utilizando uma analogia.

Execução 1:

```
Uma função chama a si mesma até atingir uma condição de parada...
```

Execução 2:

```
Imagine caixas dentro de caixas, onde cada caixa contém uma versão
menor do mesmo problema...
```

Execução 3:

```
Recursão pode ser entendida como resolver um problema dividindo-o
em versões menores do próprio problema...
```

As três respostas podem estar corretas.

Mas são diferentes.

---

## ⚠️ Por que isso importa em produção?

Imagine que o LLM precisa retornar:

```
{
  "aprovado": true,
  "motivo": "documentação válida"
}
```

Se o modelo produzir ocasionalmente:

```
O candidato parece aprovado porque a documentação está válida.
```

temos um problema.

Não necessariamente porque o conteúdo está errado.

Mas porque:

```
o sistema esperava uma estrutura específica
```

Isso pode quebrar:

- APIs;
- pipelines;
- bancos de dados;
- agentes;
- automações;
- integrações externas.

---

## 🧠 Engenharia muda novamente a pergunta

Não perguntamos apenas:

> O modelo consegue produzir a resposta correta?

Precisamos perguntar:

> Qual é a distribuição dos comportamentos possíveis?

E:

> Quais comportamentos são aceitáveis?

---

## 📊 Avaliar repetidamente

Uma execução:

```
Prompt
  ↓
Resposta
```

é pouca evidência.

Um experimento melhor:

```
Mesmo Prompt
     ↓
┌────┼────┬────┬────┐
↓    ↓    ↓    ↓    ↓
R1   R2   R3   R4   R5
     ↓
Comparação
```

Podemos analisar:

- conteúdo;
- formato;
- consistência;
- tamanho;
- latência;
- número de tokens;
- presença de erros.

---

## 🔬 Relação com experimentação

Em sistemas determinísticos, muitas vezes testamos:

```
entrada
  ↓
saída esperada
```

Em sistemas generativos, frequentemente precisamos pensar também em:

```
entrada
  ↓
múltiplas execuções
  ↓
distribuição de resultados
  ↓
métricas
```

Essa diferença será central quando estudarmos avaliação de LLMs.

---

## 🔗 Relação com Design Patterns

O não determinismo contribui para vários problemas recorrentes:

```
saída inconsistente
      ↓
controle de geração

resposta difícil de avaliar
      ↓
evaluation patterns

modelo não percebe o próprio erro
      ↓
reflection / self-check

formato precisa ser garantido
      ↓
structured generation / grammar
```

Portanto, vários patterns do livro existem justamente porque aplicações  
baseadas em modelos probabilísticos precisam de mecanismos de controle.

---

## 🧠 Modelo mental

```
Prompt
  ↓
Foundation Model
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
  ↓
Resposta
```

---

## 🧩 Conceitos deste bloco

- [[Não determinismo]]
- [[Logit]]
- [[Softmax]]
- [[Token]]
- [[Sampling]]
- [[Temperature]]
- [[Top-K]]
- [[Top-P]]

---

## ✍️ Minha compreensão

> TODO: explicar por que o mesmo prompt pode produzir respostas diferentes.

---

## 🎯 Minha definição em uma frase

> TODO

---

## 🧪 Meu exemplo

> TODO: escolher um prompt e imaginar três respostas diferentes,  
> mas ainda aceitáveis.

---

## ❓ Perguntas de revisão

1. O que significa dizer que uma aplicação é não determinística?
2. O modelo escolhe uma resposta inteira ou gera token por token?
3. O que são logits?
4. Qual é a função da softmax?
5. Por que pequenas diferenças nos primeiros tokens podem produzir  
    respostas muito diferentes?
6. Temperature baixa garante que a resposta esteja correta?
7. Por que uma única execução não é suficiente para avaliar um LLM?
---

## 🧪 Laboratórios relacionados

- [[LAB 01 - Primeira chamada LLM]] 
-


# 🧱 Bloco 6 — Alucinação em LLMs

## 🎯 Pergunta central

Como um modelo pode produzir uma resposta linguisticamente convincente
e, ainda assim, estar factualmente errado ou sem sustentação?

---

## 💡 Ideia central

Um LLM pode produzir uma resposta:

- gramaticalmente correta;
- bem estruturada;
- convincente;
- detalhada;

e ainda assim incluir informações:

- falsas;
- inventadas;
- não verificadas;
- não sustentadas pelas fontes disponíveis.

Esse fenômeno é normalmente chamado de:

> alucinação.

---

## ⚠️ Fluência não implica verdade

Esse é um dos erros mais perigosos ao utilizar LLMs.

Podemos observar:

```text
Resposta bem escrita
        ≠
Resposta verdadeira
````

Também:

```
Alta confiança linguística
        ≠
Alta confiança factual
```

Um modelo pode produzir uma resposta com tom extremamente seguro  
mesmo quando alguma informação está incorreta. 

## 🧠 Expansão didática — por que isso pode acontecer?

Um modelo de linguagem é treinado para produzir continuações plausíveis  
a partir de um contexto.

Modelo mental:

```
Contexto
   ↓
Modelo
   ↓
Possíveis próximos tokens
   ↓
Geração
   ↓
Resposta
```

O mecanismo de geração não equivale automaticamente a:

```
buscar fato
   ↓
verificar fato
   ↓
provar fato
   ↓
responder
```

Por isso devemos separar duas capacidades:

```
gerar linguagem plausível
```

e:

```
garantir verdade factual
```

Elas não são a mesma coisa.

---

## 👻 Exemplo simples

Pergunta:

> Qual artigo de 2024 introduziu o algoritmo XYZ-Transformer?

Imagine que o modelo não possua informação confiável sobre isso.

Ainda assim, ele poderia produzir algo como:

```
"O algoritmo XYZ-Transformer foi introduzido por Silva et al.
no artigo 'Efficient Transformer Architectures for...',
publicado na conferência..."
```

A resposta parece acadêmica.

Tem:

- autores;
- título;
- ano;
- conferência;
- linguagem técnica.

Mas todos esses elementos podem ter sido inventados.

Esse tipo de resposta é especialmente perigoso porque:

> parece verificável antes mesmo de ser verificada.

---

## 🧩 Formas de alucinação

Para nossa trilha, vamos usar uma classificação didática.

### 1. Fato inventado

```
"O algoritmo foi criado em 2019."
```

quando isso não é verdade.

---

### 2. Referência inventada

O modelo produz:

- artigo inexistente;
- DOI inexistente;
- livro inexistente;
- URL inventada;
- autor incorreto.

---

### 3. Atribuição incorreta

A informação existe, mas é atribuída à pessoa, artigo ou organização errada.

```
Fato verdadeiro
+
fonte errada
=
resposta problemática
```

---

### 4. Informação não sustentada pelo contexto

Imagine um sistema RAG.

Os documentos recuperados dizem apenas:

```
"O produto foi lançado em março."
```

Mas o modelo responde:

```
"O produto foi lançado em março e teve 2 milhões de usuários
na primeira semana."
```

A segunda parte não veio da evidência fornecida.

---

### 5. Preenchimento de lacunas

Quando não possui determinada informação, o modelo pode produzir uma  
continuação plausível em vez de declarar:

> não sei.

Esse comportamento é especialmente importante em sistemas que trabalham  
com informação incompleta. 

.

---

## 🔍 Alucinação vs erro comum

Nem todo erro precisa ser chamado de alucinação.

Por exemplo:

```
2 + 2 = 5
```

pode ser simplesmente uma resposta incorreta.

==O termo "alucinação" é particularmente útil quando o modelo produz==  
==conteúdo aparentemente plausível, mas sem base factual ou sem sustentação==  
==na evidência utilizada pelo sistema.==

---

## 🎲 Relação com não determinismo

Não determinismo e alucinação são conceitos diferentes.

### Não determinismo

```
mesma entrada
     ↓
respostas diferentes
```

### Alucinação

```
resposta
   ↓
informação falsa ou não sustentada
```

Podemos ter:

```
resposta diferente
+
todas corretas
```

Nesse caso temos variabilidade, mas não necessariamente alucinação.

Também podemos ter:

```
resposta sempre igual
+
informação falsa
```

Nesse caso o comportamento pode ser consistente e ainda assim estar errado.

Portanto:

```
Não determinismo ≠ Alucinação
```

---

## 🏭 Por que isso é um problema de produção?

Imagine um sistema utilizado para:

- suporte técnico;
- educação;
- pesquisa;
- análise documental;
- atendimento empresarial.

Uma alucinação pode produzir:

```
informação falsa
        ↓
usuário acredita
        ↓
decisão baseada nela
        ↓
impacto real
```

Por isso não podemos avaliar apenas:

> A resposta parece boa?

Precisamos perguntar:

> A resposta está sustentada?

---

## 🔬 Verificação muda a arquitetura

Uma arquitetura ingênua:

```
Usuário
   ↓
LLM
   ↓
Resposta
```

Uma arquitetura mais robusta pode precisar de:

```
Usuário
   ↓
Contexto / Evidências
   ↓
LLM
   ↓
Resposta
   ↓
Validação
   ↓
Usuário
```

Ou:

```
Pergunta
   ↓
Recuperação
   ↓
Fontes
   ↓
Geração
   ↓
Verificação
   ↓
Resposta
```

Esses mecanismos aparecerão posteriormente em vários patterns do curso.

---

## 📚 Relação com RAG

Uma das razões para utilizarmos RAG é fornecer conhecimento externo ao modelo.

```
Pergunta
   ↓
Retriever
   ↓
Documentos relevantes
   ↓
Contexto
   ↓
LLM
```

Mas atenção:

> ==RAG não elimina automaticamente alucinações.==

Ainda precisamos avaliar se a resposta:

- utilizou os documentos recuperados;
- permaneceu fiel às evidências;
- inventou informações adicionais;
- citou corretamente as fontes.

---

## 🧠 Groundedness

Um conceito importante para nossa trilha será:

> groundedness.

Pergunta:

> A resposta está sustentada pela evidência disponível?

Modelo mental:

```
Fonte
  ↓
Evidência
  ↓
Resposta
```

Queremos que:

```
afirmações da resposta
        ⊆
evidências suportadas
```

Esse tema ficará muito importante quando estudarmos RAG e avaliação.

---

## 📊 Como avaliar alucinação?

Não basta executar:

```
Prompt
  ↓
Resposta
```

e perguntar:

> parece correta?

Precisamos comparar a resposta com alguma referência.

Exemplo:

```
Pergunta
   ↓
LLM
   ↓
Resposta
   ↓
Comparação
   │
   ├── fonte confiável
   ├── ground truth
   ├── documentos recuperados
   └── avaliador
```

---

## 🧪 Exemplo com contexto fechado

Documento fornecido:

```
A empresa Quasar foi fundada em 2018.
Sua sede fica em Recife.
```

Pergunta:

> Onde a empresa foi fundada e quantos funcionários possui?

Resposta segura:

```
A sede fica em Recife. O texto fornecido não informa
quantos funcionários a empresa possui.
```

Resposta problemática:

```
A empresa fica em Recife e possui aproximadamente 450 funcionários.
```

O número:

```
450
```

não possui suporte no contexto.

Esse é exatamente o tipo de comportamento que queremos detectar.

---

## 🛡️ Uma habilidade importante: saber não responder

Em alguns sistemas, uma boa resposta pode ser:

> Não há informação suficiente para responder.

==Isso pode ser muito mais valioso do que uma resposta detalhada inventada.==

Portanto, em determinadas aplicações:

```
abstenção correta
        >
resposta inventada
```

---

## 🔗 Relação com Design Patterns

O problema da alucinação aparecerá novamente quando estudarmos patterns  
relacionados a:

```
recuperação de conhecimento
        ↓
RAG

confiabilidade
        ↓
Reflection / avaliação

grounding
        ↓
Trustworthy Generation

verificação
        ↓
Self-Check

proteções
        ↓
Guardrails
```

Não devemos tratar cada pattern como uma solução mágica.

Cada um ataca uma parte diferente do problema.

---

## 🧠 Modelo mental

```
LLM
 ↓
Resposta plausível
 ↓
          ┌─────────────────┐
          │                 │
          ▼                 ▼
      sustentada        não sustentada
          │                 │
          ▼                 ▼
       aceitável        potencial
                       alucinação
```

---

## 🧩 Conceitos deste bloco

- [[Alucinação]]
- [[Groundedness]]
- [[Ground Truth]]
- [[RAG]]
- [[Não determinismo]]
- [[Avaliação]]
- [[Trustworthy Generation]]
- [[Self-Check]]

---

## ✍️ Minha compreensão

> TODO: explicar por que uma resposta bem escrita não pode ser considerada  
> automaticamente uma resposta verdadeira.

---

## 🎯 Minha definição em uma frase

> TODO

---

## 🧪 Meu exemplo

> TODO: inventar um cenário em que um LLM poderia produzir uma resposta  
> convincente, porém sem sustentação.

---

## ❓ Perguntas de revisão

1. Por que fluência linguística não implica verdade factual?
2. Qual é a diferença entre não determinismo e alucinação?
3. Um modelo pode produzir sempre a mesma resposta e ainda assim alucinar?
4. Por que referências acadêmicas inventadas são particularmente perigosas?
5. O que significa uma resposta estar grounded?
6. RAG elimina completamente alucinações?
7. Por que dizer "não sei" pode ser uma resposta melhor? 



# 🧱 Bloco 7 — Agentes e aplicações agênticas

## 🎯 Pergunta central

Qual é a diferença entre um LLM que responde a uma pergunta e um sistema
que utiliza o modelo para perseguir um objetivo e executar ações?

---

## 💡 Ideia central

Um LLM isolado normalmente recebe uma entrada e produz uma saída.

```text
Prompt
  ↓
LLM
  ↓
Resposta
````

Um agente pode participar de um ciclo mais amplo:

```
Objetivo
   ↓
Percepção
   ↓
Raciocínio / Planejamento
   ↓
Ação
   ↓
Novo estado do ambiente
   ↓
Nova percepção
   ↓
...
```

==A diferença fundamental é que o modelo deixa de ser apenas um gerador==  
==de respostas e passa a fazer parte de um sistema que toma decisões==  
==orientadas a um objetivo.==

---

## 🆚 LLM vs Agente

### LLM

Modelo mental simplificado:

```
Entrada
  ↓
Modelo
  ↓
Saída
```

Exemplo:

> "Qual é a previsão do tempo para amanhã?"

O modelo responde com texto.

---

### Agente

Modelo mental:

```
Objetivo
   ↓
Modelo
   ↓
Decisão
   ↓
Ferramenta
   ↓
Resultado
   ↓
Modelo
   ↓
Próxima decisão
```

Exemplo:

> "Organize minha viagem para Recife."

Um sistema agêntico poderia precisar:

1. identificar datas;
2. consultar voos;
3. consultar hotéis;
4. comparar alternativas;
5. verificar restrições;
6. apresentar um plano;
7. eventualmente executar alguma ação autorizada.

---

## 🎯 Objetivo

Um agente normalmente opera em direção a algum objetivo.

Exemplo:

```
Objetivo:
"Encontrar o melhor horário para uma reunião."
```

A partir desse objetivo, o sistema pode precisar decidir:

```
Qual informação preciso?
      ↓
Qual ferramenta consultar?
      ↓
O resultado resolve o problema?
      ↓
Preciso executar outra ação?
```

O objetivo fornece direção para o comportamento do agente.

---

## 👁️ Percepção

==O agente precisa receber informações sobre o ambiente.==

Essas informações podem vir de:

- mensagens do usuário;
- APIs;
- bancos de dados;
- arquivos;
- sensores;
- resultados de ferramentas;
- estado interno da aplicação.

Modelo mental:

```
Ambiente
   ↓
Observações
   ↓
Agente
```

---

## 🧠 Planejamento

Diante de um objetivo, ==o agente pode precisar decompor o problema.==

Exemplo:

```
Objetivo:
"Gerar um relatório sobre vendas do mês."
```

Possível decomposição:

```
1. localizar dados
2. carregar dados
3. calcular métricas
4. identificar anomalias
5. gerar resumo
6. produzir relatório
```

Essa decomposição representa uma forma de planejamento.

---

## 🛠️ Ação

Uma ==diferença importante entre um chatbot simples e um agente é==  
==a possibilidade de agir sobre o ambiente.==

Exemplos:

```
consultar API
executar função
buscar documento
consultar banco
executar código
enviar mensagem
alterar um sistema
```

Modelo:

```
LLM
 ↓
decisão
 ↓
Tool
 ↓
ação
```

Esse assunto será aprofundado posteriormente no pattern:

[[Tool Calling]]

---

## 🔁 Loop agêntico

Uma característica importante é o ciclo.

```
Objetivo
   ↓
Observar
   ↓
Pensar / Planejar
   ↓
Agir
   ↓
Observar resultado
   ↓
Decidir próximo passo
   ↺
```

O sistema não precisa produzir a solução inteira em apenas uma inferência.

Ele pode executar uma sequência de passos.

---

## 🧠 Exemplo: agente de estoque

Imagine o objetivo:

> verificar se algum produto precisa ser reposto.

Um chatbot poderia receber dados e responder:

> "O produto A precisa ser reposto."

Um agente poderia:

```
Consultar estoque
      ↓
Comparar com estoque mínimo
      ↓
Consultar histórico de vendas
      ↓
Calcular necessidade
      ↓
Gerar recomendação
      ↓
Criar solicitação de reposição
```

Dependendo das permissões, poderia existir uma ação real no último passo.

---

## 🧩 Características de um agente

Para nossa trilha, vamos guardar cinco características centrais:

### 🎯 1. Objetivo

Existe algo que o sistema tenta alcançar.

### 👁️ 2. Percepção

O sistema recebe informações sobre o ambiente.

### 🧠 3. Planejamento

Decide quais passos podem levar ao objetivo.

### 🛠️ 4. Ação

Interage com ferramentas ou com o ambiente.

### 🔄 5. Adaptação

Usa o resultado das ações para decidir o próximo passo.

Modelo mental:

```
Objetivo
   ↓
Percepção
   ↓
Planejamento
   ↓
Ação
   ↓
Feedback
   ↓
Adaptação
```

---

## ⚠️ Autonomia não significa ausência de controle

Um agente pode possuir diferentes graus de autonomia.

Por exemplo:

### Baixa autonomia

```
Agente recomenda ação
        ↓
Humano aprova
        ↓
Ação ocorre
```

### Maior autonomia

```
Agente decide
     ↓
Ferramenta
     ↓
Ação ocorre
```

Portanto, autonomia é uma decisão arquitetural.

Não é obrigatório permitir que o agente execute tudo automaticamente.

---

## 🛡️ Human-in-the-loop

Para ações sensíveis, podemos inserir aprovação humana.

```
Agente
  ↓
Propõe ação
  ↓
Humano
  ↓
Aprova?
 ┌─────┴─────┐
 ↓           ↓
Sim         Não
 ↓
Executa
```

Isso será importante posteriormente quando estudarmos:

- segurança;
- guardrails;
- autorização;
- confiabilidade;
- ações externas.

---

## ⚠️ O problema do não determinismo em agentes

O não determinismo se torna ainda mais importante quando o modelo  
não está apenas escrevendo texto.

Compare:

```
Resposta diferente
```

com:

```
Ação diferente
```

Quando um ==LLM está ligado a ferramentas, uma decisão incorreta pode==  
==produzir efeitos externos.==

Modelo:

```
LLM incorreto
     ↓
decisão incorreta
     ↓
tool call
     ↓
efeito real
```

==Por isso aplicações agênticas exigem ainda mais engenharia.==

---

## 🧱 LLM é componente do agente

Não devemos confundir:

```
LLM = Agente
```

Uma representação melhor é:

```
             AGENTE
                │
      ┌─────────┼─────────┐
      ▼         ▼         ▼
     LLM      Estado    Ferramentas
      │         │         │
      └─────────┼─────────┘
                ▼
              Ações
```

O LLM pode funcionar como mecanismo de raciocínio ou decisão.

Mas o agente é o sistema completo.

---

## 🌐 Aplicação agêntica

Também podemos ter uma aplicação composta por:

```
Interface
   ↓
Orquestração
   ↓
Agente
   ├── LLM
   ├── memória
   ├── ferramentas
   ├── contexto
   └── estado
   ↓
Serviços externos
```

Portanto:

```
Foundation Model
      ↓
Agente
      ↓
Aplicação agêntica
```

são níveis diferentes da arquitetura.

---

## 🤝 Um agente não significa multiagentes

Outro cuidado:

```
Agente
≠
Sistema multiagente
```

Podemos construir:

```
1 agente
+
várias ferramentas
```

sem precisar de:

```
5 agentes conversando entre si
```

==Multiagent Collaboration é um pattern específico que estudaremos depois.==

A pergunta continua sendo:

> Qual problema justifica múltiplos agentes?

---

## 🔗 Relação com Design Patterns

Vários patterns posteriores surgem quando começamos a construir  
sistemas agênticos.

Exemplos:

```
preciso acessar sistemas externos
        ↓
Tool Calling

preciso executar código
        ↓
Code Execution

preciso dividir responsabilidades
        ↓
Multiagent Collaboration

preciso lembrar informações
        ↓
Long-Term Memory

preciso controlar comportamento
        ↓
Guardrails
```

---

## 🧠 Modelo mental final

```
                OBJETIVO
                   ↓
               ┌ AGENTE ┐
               │        │
          percepção     │
               ↓        │
              LLM       │
               ↓        │
          planejamento  │
               ↓        │
          ferramentas   │
               ↓        │
              ação      │
               ↓        │
             feedback ──┘
```

---

## 🧩 Conceitos deste bloco

- [[Agente]]
- [[Aplicação Agêntica]]
- [[Objetivo]]
- [[Planejamento]]
- [[Tool Calling]]
- [[Human-in-the-loop]]
- [[Autonomia]]
- [[Estado]]
- [[Memória]]

---


---

## ❓ Perguntas de revisão

1. Qual é a diferença entre um LLM e um agente?
2. Por que um objetivo é importante para um agente?
3. O que significa o agente perceber o ambiente?
4. Qual é a função das ferramentas?
5. Por que um agente pode precisar executar vários passos?
6. Qual é a diferença entre agente e aplicação agêntica?
7. Um agente precisa obrigatoriamente possuir autonomia total?
8. Por que não determinismo torna-se mais crítico quando existem ações?
9. Todo agente precisa fazer parte de um sistema multiagente? 


# 🧱 Bloco 8 — Limitações e riscos dos sistemas agênticos

## 🎯 Pergunta central

==O que muda quando um sistema probabilístico deixa de apenas gerar texto==
==e passa a tomar decisões e executar ações?==

---

## 💡 Ideia central

Em um chatbot simples, uma falha pode resultar em uma resposta ruim.

Em um sistema agêntico, uma falha pode resultar em:

```text
interpretação incorreta
        ↓
decisão incorreta
        ↓
ação incorreta
        ↓
mudança no ambiente
````

Portanto, ==quanto maior a capacidade de ação do sistema,==  
==maior precisa ser a preocupação com controle.==

---

## 🆚 Erro de resposta vs erro de ação

Considere dois sistemas.

### Sistema A — Chatbot

```
Usuário
   ↓
LLM
   ↓
Resposta incorreta
```

Consequência:

```
texto ruim
```

---

### Sistema B — Agente

```
Usuário
   ↓
Agente
   ↓
Decisão
   ↓
Ferramenta
   ↓
Ação incorreta
```

Consequência:

```
efeito externo
```

Isso pode significar:

- alterar um registro;
- executar código;
- enviar uma mensagem;
- chamar uma API;
- criar ou remover um recurso;
- iniciar algum processo externo.

---

## 🎲 Não determinismo + ação

No bloco anterior vimos:

```
mesma entrada
     ↓
respostas diferentes
```

Em agentes podemos ter:

```
mesmo objetivo
     ↓
planos diferentes
     ↓
ações diferentes
```

Isso torna a avaliação mais difícil.

Não precisamos apenas verificar:

> A resposta final ficou boa?

Precisamos verificar também:

- quais decisões foram tomadas;
- quais ferramentas foram escolhidas;
- em qual ordem;
- quais parâmetros foram enviados;
- quais efeitos aconteceram.

---

## 🔗 Propagação de erro

Uma pequena falha pode afetar etapas seguintes.

Exemplo:

```
Percepção incorreta
        ↓
Plano incorreto
        ↓
Tool Call incorreto
        ↓
Resultado inesperado
        ↓
Nova decisão baseada em resultado errado
```

Esse fenômeno pode produzir uma cadeia de erros.

Modelo mental:

```
erro pequeno
   ↓
erro intermediário
   ↓
novo contexto incorreto
   ↓
novo erro
   ↓
efeito maior
```

---

## 🧠 Erro composto

Imagine um agente realizando cinco decisões consecutivas.

==Mesmo que cada etapa tenha alta taxa de acerto,==  
==o sistema completo ainda pode acumular falhas==.

Exemplo conceitual:

```
Etapa 1 → correta
Etapa 2 → correta
Etapa 3 → incorreta
Etapa 4 → baseada na etapa 3
Etapa 5 → baseada na etapa 4
```

A etapa 3 contaminou o restante do processo.

Por isso não basta avaliar apenas a resposta final.

---

## 🔍 Precisamos observar o caminho

Em aplicações agênticas, queremos registrar:

```
Objetivo
   ↓
Observações
   ↓
Decisões
   ↓
Tool Calls
   ↓
Resultados
   ↓
Resposta final
```

Isso permite responder depois:

> Por que o agente fez isso?

---

## 📜 Traço de execução

Um sistema agêntico bem instrumentado pode registrar algo como:

```
Objetivo:
"Gerar relatório de vendas"

Passo 1:
consultar banco de dados

Passo 2:
carregar vendas do mês

Passo 3:
calcular métricas

Passo 4:
gerar resumo

Passo 5:
salvar relatório
```

Esse histórico de execução ajuda em:

- depuração;
- auditoria;
- avaliação;
- investigação de falhas;
- comparação entre versões.

---

## 🚧 Permissões

Um agente não deveria necessariamente poder fazer tudo.

Podemos limitar:

```
Agente
   ↓
Conjunto permitido de ferramentas
```

Por exemplo:

```
Pode:
- consultar dados
- gerar relatório

Não pode:
- excluir registros
- transferir dinheiro
- alterar permissões
```

Isso reduz a superfície de risco.

---

## 🔑 Princípio do menor privilégio

Uma regra importante de engenharia é:

> conceder apenas as permissões necessárias para executar a tarefa.

Modelo:

```
capacidade necessária
        =
permissão concedida
```

e não:

```
"Talvez precise depois"
        ↓
dar acesso a tudo
```

---

## 🛑 Ações reversíveis vs irreversíveis

Outra distinção útil:

### Ação reversível

```
gerar rascunho
```

### Ação potencialmente irreversível

```
apagar arquivo
enviar pagamento
publicar conteúdo
cancelar recurso
```

==Quanto maior o impacto da ação,==  
==maior deve ser o nível de controle.==

---

## 👤 Human-in-the-loop

Para determinadas ações podemos inserir aprovação humana.

```
Agente propõe ação
        ↓
Humano revisa
        ↓
Aprova?
   ┌────┴────┐
   ↓         ↓
  Sim       Não
   ↓
Executa
```

Isso é especialmente útil em ações:

- financeiras;
- administrativas;
- destrutivas;
- sensíveis;
- difíceis de reverter.

---

## 🎯 Autonomia deve ser graduada

Autonomia não é:

```
ligada / desligada
```

Podemos pensar em níveis.

### Nível 0 — Assistente

```
gera informação
```

### Nível 1 — Recomendação

```
propõe ação
```

### Nível 2 — Ação com aprovação

```
propõe
  ↓
humano aprova
  ↓
executa
```

### Nível 3 — Ação autônoma limitada

```
executa dentro de regras
```

### Nível 4 — Autonomia ampla

```
planeja
decide
executa
reavalia
```

Quanto maior o nível:

```
mais capacidade
      +
mais responsabilidade de engenharia
```

---

## ⚠️ Mais autonomia não significa sistema melhor

Essa é uma regra importante.

```
mais agentes
+
mais ferramentas
+
mais autonomia
```

não significa automaticamente:

```
melhor sistema
```

Pode significar:

```
mais complexidade
+
mais custo
+
mais estados possíveis
+
mais formas de falhar
```

---

## 🧠 Complexidade comportamental

Compare:

```
Prompt
  ↓
LLM
  ↓
Resposta
```

com:

```
Objetivo
  ↓
LLM
  ↓
Tool A
  ↓
LLM
  ↓
Tool B
  ↓
LLM
  ↓
Tool C
  ↓
Resposta
```

O segundo sistema possui muito mais caminhos possíveis.

Portanto:

> ==quanto maior o número de decisões, ferramentas e loops,==  
> ==maior o espaço de comportamento que precisamos avaliar.==

---

## 🔁 Loops

Um agente pode continuar executando ações sem chegar a uma solução.

Exemplo:

```
buscar informação
      ↓
resultado insuficiente
      ↓
buscar novamente
      ↓
resultado insuficiente
      ↓
buscar novamente
      ↓
...
```

Precisamos de mecanismos como:

- limite de passos;
- limite de custo;
- limite de tempo;
- condições de parada.

---

## 💰 Custo acumulado

Um chatbot pode fazer:

```
1 chamada de modelo
```

Um agente pode fazer:

```
10 chamadas de modelo
+
5 chamadas de API
+
3 buscas
+
execução de código
```

Portanto, o custo de uma única tarefa pode crescer rapidamente.

Modelo:

```
custo por passo
      ×
número de passos
      =
custo da tarefa
```

---

## ⏱️ Latência acumulada

O mesmo vale para tempo.

```
LLM
 ↓
API
 ↓
LLM
 ↓
Busca
 ↓
LLM
```

Cada etapa adiciona latência.

Um sistema intelectualmente sofisticado pode acabar sendo  
operacionalmente insuportável.

---

## 🛡️ Falhas de ferramentas

O agente não controla tudo.

Uma ferramenta pode retornar:

- timeout;
- erro HTTP;
- dado ausente;
- resposta inesperada;
- indisponibilidade;
- resultado parcial.

Portanto:

```
Tool Call
   ↓
pode falhar
```

O agente precisa saber lidar com falhas externas.

---

## 🔬 Avaliar agentes é mais difícil

Para um chatbot podemos medir:

```
entrada
   ↓
resposta
```

Para um agente podemos precisar medir:

```
objetivo
   ↓
plano
   ↓
ações
   ↓
tool calls
   ↓
resultados intermediários
   ↓
resultado final
```

Algumas métricas possíveis:

- sucesso da tarefa;
- número de passos;
- número de tool calls;
- custo;
- latência;
- taxa de ações inválidas;
- taxa de intervenção humana;
- falhas por ferramenta.

---

## 🧱 Três camadas de controle

Um modelo mental útil:

```
┌─────────────────────────────┐
│ 1. Controle do modelo       │
│ prompts, contexto, geração  │
├─────────────────────────────┤
│ 2. Controle do agente       │
│ tools, loops, estado        │
├─────────────────────────────┤
│ 3. Controle do ambiente     │
│ permissões, aprovação       │
└─────────────────────────────┘
```

Quanto mais perto chegamos do ambiente real,  
maior deve ser a proteção.

---

## 🔗 Relação com os patterns do livro

Essas limitações ajudam a explicar por que encontraremos patterns como:

```
Tool Calling
Code Execution
Multiagent Collaboration
Long-Term Memory
Self-Check
Guardrails
```

Cada pattern trata uma parte diferente da construção de sistemas  
mais capazes e mais controláveis.

---

## 🧠 Modelo mental final

```
                 OBJETIVO
                    ↓
                  AGENTE
                    ↓
        ┌───────────┼───────────┐
        ↓           ↓           ↓
     decisão      estado      ferramentas
        ↓                       ↓
        └───────────┬───────────┘
                    ↓
                   AÇÃO
                    ↓
                 AMBIENTE
                    ↓
                 FEEDBACK
                    ↓
                  AGENTE
                    ↺
```

Mas precisamos envolver esse loop com:

```
permissões
limites
avaliação
observabilidade
segurança
aprovação
```

---

## 🧩 Conceitos deste bloco

- [[Autonomia]]
- [[Human-in-the-loop]]
- [[Princípio do Menor Privilégio]]
- [[Observabilidade]]
- [[Tool Calling]]
- [[Limite de Passos]]
- [[Estado]]
- [[Guardrails]]


---

## ❓ Perguntas de revisão

1. Por que uma falha em um agente pode ser mais grave que uma  
    resposta ruim de chatbot?
2. O que significa propagação de erro?
3. Por que precisamos registrar os passos intermediários do agente?
4. O que significa princípio do menor privilégio?
5. Por que ações irreversíveis merecem controles adicionais?
6. Mais autonomia significa necessariamente um sistema melhor?
7. Como loops podem aumentar custo e latência?
8. Por que avaliar agentes é mais difícil do que avaliar  
    uma única resposta de LLM? 

# 🧱 Bloco 9 — Logits e Softmax

## 🎯 Pergunta central

==De onde vêm as probabilidades utilizadas por um LLM para decidir==
==quais tokens podem ser gerados em seguida?==

---

## 💡 Ideia central

Durante a geração, ==o modelo precisa decidir qual token deve vir depois.==

Para isso, ele produz uma pontuação para cada possível token
do vocabulário.

Essas pontuações são chamadas de:

> logits.

Depois, podemos ==transformar esses logits em probabilidades== utilizando
uma função chamada:

> softmax.

Modelo mental:

```text
Contexto
   ↓
LLM
   ↓
Logits
   ↓
Softmax
   ↓
Probabilidades
   ↓
Seleção do próximo token
````
## 🔤 Primeiro: o vocabulário

Um modelo possui um vocabulário de tokens possíveis.

Exemplo extremamente simplificado:

```
Vocabulário:

"Brasília"
"Rio"
"São"
"Recife"
"Curitiba"
...
```

Imagine o contexto:

```
"A capital do Brasil é"
```

O modelo precisa atribuir algum valor aos possíveis próximos tokens.

---

## 🔢 Logits

Os logits são valores numéricos produzidos pelo modelo antes  
da conversão para probabilidades.

Exemplo conceitual:

```
Token       Logit

Brasília     8.3
Rio          2.1
São          1.8
Recife       0.9
Curitiba     0.3
```

==Quanto maior o logit, maior a preferência relativa do modelo==  
==por aquele token.==

Mas atenção:

```
8.3
```

não significa:

```
83%
```

==Logits não são probabilidades.== 

## 🧠 O que significa um logit?

Podemos pensar no logit como uma pontuação interna de preferência.

```
Token A → pontuação alta
Token B → pontuação média
Token C → pontuação baixa
```

O modelo ainda precisa transformar essas pontuações em algo  
que possa ser interpretado como distribuição de probabilidades.

É aí que entra a softmax.

---

## 📊 Softmax

A softmax transforma um conjunto de valores reais em valores positivos  
que somam aproximadamente 1.

Modelo mental:

```
Logits
   ↓
Softmax
   ↓
Probabilidades
```

Exemplo:

```
Logits:

Brasília → 8.3
Rio      → 2.1
São      → 1.8
```

Depois da softmax, poderíamos obter algo conceitualmente semelhante a:

```
Brasília → 0.995
Rio      → 0.002
São      → 0.003
```

Os números acima são apenas ilustrativos.

O importante é:

```
P(token 1)
+
P(token 2)
+
P(token 3)
+
...
≈ 1
```



# 🧱 Bloco 10 — Temperature

## 🎯 Pergunta central

Como podemos tornar a geração de um LLM mais conservadora ou mais diversa?

---

## 💡 Ideia central

Depois que o modelo produz logits, podemos modificar a distribuição
antes de aplicar a softmax.

Uma das formas de fazer isso é utilizando:

> temperature

Modelo mental:

```text
Contexto
   ↓
Modelo
   ↓
Logits
   ↓
Temperature
   ↓
Softmax
   ↓
Probabilidades
   ↓
Seleção do token
````

---

## 🧮 Onde entra a Temperature?

No bloco anterior vimos:

```
softmax(zᵢ)
```

Com temperature `T`, podemos pensar em:

```
softmax(zᵢ / T)
```

Ou:

```
                    e^(zi / T)
P(token_i) = ─────────────────────────
              Σ_j e^(zj / T)
```

A temperature modifica os logits antes da normalização.

---

## 🌡️ Temperature baixa

Quando:

```
T < 1
```

as diferenças entre os logits ficam mais pronunciadas.

Exemplo:

```
Logits:

A → 3
B → 2
C → 1
```

Com temperature baixa:

```
A → muito dominante
B → bem menor
C → quase descartado
```

A distribuição fica mais concentrada.

Modelo mental:

```
Temperature ↓
      ↓
distribuição mais concentrada
      ↓
tokens mais prováveis dominam
      ↓
menor diversidade
```

---

## 🔥 Temperature alta

Quando:

```
T > 1
```

as diferenças entre logits ficam menos pronunciadas.

Exemplo:

```
A → 3
B → 2
C → 1
```

Com temperature alta:

```
A → ainda provável
B → ganha espaço
C → ganha espaço
```

A distribuição fica mais espalhada.

Modelo mental:

```
Temperature ↑
      ↓
distribuição mais plana
      ↓
tokens menos prováveis ganham espaço
      ↓
maior diversidade
```

---

## 🧠 Intuição

Podemos pensar assim:

```
Temperature baixa
=
o modelo tende a explorar menos alternativas
```

```
Temperature alta
=
o modelo aceita mais alternativas da distribuição
```

Isso afeta a diversidade da geração.

---

## 🆚 Exemplo conceitual

Imagine:

```
Prompt:
"Crie um título para um artigo sobre recursão."
```

### Temperature baixa

Possíveis respostas:

```
"Introdução à Recursão"
"Recursão em Programação"
"Entendendo Recursão"
```

As respostas tendem a ficar mais próximas das continuações mais prováveis.

### Temperature alta

Podemos começar a observar:

```
"Recursão: Funções que Conversam com Elas Mesmas"
"Do Espelho ao Stack: Entendendo Recursão"
"Recursão sem Labirintos"
```

A diversidade tende a aumentar.

---

## ⚠️ Temperature não controla verdade

Esse ponto é fundamental.

```
Temperature baixa
≠
resposta verdadeira
```

Também:

```
Temperature alta
≠
resposta errada
```

Temperature modifica principalmente a distribuição utilizada durante  
a geração.

Ela não é um mecanismo de verificação factual.

---

## 👻 Relação com alucinação

Pode parecer tentador pensar:

```
temperature = 0
        ↓
sem alucinação
```

Isso está errado.

Um modelo pode produzir uma continuação incorreta com alta probabilidade.

Por exemplo:

```
token incorreto
+
logit muito alto
=
resposta incorreta produzida com alta confiança
```

Portanto:

> reduzir a temperature pode reduzir diversidade,  
> mas não garante factualidade.

---

## 🎲 Relação com não determinismo

Quando há sampling:

```
Temperature
     ↓
modifica distribuição
     ↓
sampling
     ↓
token selecionado
```

Temperature influencia o espaço de possíveis resultados.

De maneira geral:

```
Temperature baixa
     ↓
menor variabilidade
```

```
Temperature alta
     ↓
maior variabilidade
```

Mas o comportamento exato também depende do mecanismo de decoding  
e das configurações utilizadas pelo provider.

---

## 🧪 Exemplo numérico intuitivo

Imagine inicialmente:

```
A → 70%
B → 20%
C → 10%
```

Com uma configuração mais conservadora, poderíamos obter algo semelhante a:

```
A → 90%
B → 8%
C → 2%
```

Com uma configuração mais diversa:

```
A → 50%
B → 30%
C → 20%
```

Os valores acima são apenas ilustrativos.

A ideia é visualizar como a distribuição pode ficar:

```
mais concentrada
```

ou:

```
mais espalhada
```

---

## 🎯 Temperature depende da tarefa

Não existe uma única temperature "correta".

Depende do comportamento desejado.

### Tarefas que podem favorecer menor diversidade

Exemplos:

- extração estruturada;
- classificação;
- geração de JSON;
- transformação de formato;
- respostas técnicas mais consistentes.

### Tarefas que podem tolerar ou buscar maior diversidade

Exemplos:

- brainstorming;
- geração de ideias;
- títulos;
- escrita criativa;
- exploração de alternativas.

---

## 🧠 Decisão de engenharia

A pergunta não deve ser:

> Qual é a melhor temperature?

A pergunta deve ser:

> Qual comportamento queremos para esta tarefa?

Depois:

```
Requisito
   ↓
Configuração
   ↓
Experimento
   ↓
Métrica
   ↓
Decisão
```

---

## 🧪 Não escolher no chute

Em AI Engineering, não queremos:

```
temperature = 0.7
```

apenas porque alguém disse que `0.7` é bom.

Queremos testar.

Exemplo:

```
temperature 0.0
temperature 0.3
temperature 0.7
temperature 1.0
```

Depois comparar:

- consistência;
- diversidade;
- formato;
- qualidade;
- latência;
- taxa de erro.

---

## 📊 Temperature como variável experimental

Podemos tratá-la como:

```
Variável independente:
temperature
```

e observar:

```
Variáveis dependentes:

- diversidade
- consistência
- tamanho da resposta
- aderência ao formato
- qualidade
```

Isso transforma uma configuração de API em um experimento.

---

## 🔬 Exemplo de experimento

Prompt fixo:

```
"Explique recursão em no máximo 3 frases."
```

Executar:

```
T = 0.0 → 10 execuções
T = 0.3 → 10 execuções
T = 0.7 → 10 execuções
T = 1.0 → 10 execuções
```

Depois comparar:

```
consistência
diversidade
aderência ao limite
conteúdo
```

---

## 🧠 Modelo mental

```
Logits
   ↓
Temperature
   ↓
Distribuição modificada
   ↓
Softmax
   ↓
Probabilidades
   ↓
Sampling
   ↓
Token
```

---

## 🔗 Relação com os próximos parâmetros

Temperature não é o único mecanismo utilizado para controlar geração.

Depois veremos:

- [[Top-K]]
- [[Top-P]]
- [[Beam Search]]
- [[Frequency Penalty]]
- [[Presence Penalty]]

Cada mecanismo interfere de uma forma diferente no processo de geração.

---

## 🧩 Conceitos deste bloco

- [[Temperature]]
- [[Logit]]
- [[Softmax]]
- [[Sampling]]
- [[Não determinismo]]
- [[Distribuição de Probabilidade]]
- [[Top-K]]
- [[Top-P]]

## ❓ Perguntas de revisão

1. Em qual ponto do processo de geração entra a temperature?
2. O que acontece com a distribuição quando a temperature diminui?
3. O que acontece quando a temperature aumenta?
4. Temperature baixa garante uma resposta verdadeira?
5. Por que não existe uma única temperature ideal?
6. Como podemos escolher uma temperature de maneira experimental?
7. Qual é a relação entre temperature e não determinismo?

# 🧱 Bloco 11 — Top-K e Top-P

## 🎯 Pergunta central

Além de modificar a distribuição com temperature, como podemos limitar
quais tokens realmente participam do processo de seleção?

---

## 💡 Ideia central

Depois que o modelo produz uma distribuição de probabilidades, podemos
reduzir o conjunto de tokens candidatos antes de realizar o sampling.

Duas estratégias importantes são:

- Top-K;
- Top-P.

Modelo mental:

Contexto
   ↓
Modelo
   ↓
Logits
   ↓
Temperature
   ↓
Softmax
   ↓
Probabilidades
   ↓
Top-K / Top-P
   ↓
Sampling
   ↓
Próximo token 

# 🎯 Top-K

## Ideia

Top-K mantém apenas os `K` tokens de maior probabilidade.

Todos os outros são descartados antes do sampling.

Exemplo:

```
Token A → 40%
Token B → 25%
Token C → 15%
Token D → 10%
Token E → 6%
Token F → 4%
```

Se:

```
K = 3
```

mantemos apenas:

```
A → 40%
B → 25%
C → 15%
```

Os demais tokens deixam de participar da seleção.

---

## 🧠 Modelo mental do Top-K

```
Distribuição completa
        ↓
Ordenar por probabilidade
        ↓
Selecionar K maiores
        ↓
Renormalizar
        ↓
Sampling
```

---

## 🧪 Exemplo

Distribuição original:

```
A → 40%
B → 25%
C → 15%
D → 10%
E → 6%
F → 4%
```

Com:

```
Top-K = 3
```

mantemos:

```
A
B
C
```

A probabilidade total desses três é:

```
40 + 25 + 15 = 80%
```

Depois da renormalização:

```
A → 40 / 80 = 50%
B → 25 / 80 = 31,25%
C → 15 / 80 = 18,75%
```

Agora o sampling acontece apenas dentro desse conjunto.

---

## ⚠️ Limitação do Top-K

Top-K utiliza um número fixo de candidatos.

Isso significa que:

```
K = 10
```

sempre permite até 10 candidatos, independentemente da forma da distribuição.

Mas distribuições diferentes podem ter estruturas muito diferentes.

---

## 📊 Exemplo de distribuição concentrada

```
A → 90%
B → 3%
C → 2%
D → 1%
...
```

Mesmo que A domine completamente, um Top-K grande ainda pode manter  
vários tokens pouco prováveis.

---

## 📊 Exemplo de distribuição espalhada

```
A → 15%
B → 14%
C → 13%
D → 12%
E → 11%
...
```

Agora poucos tokens podem não representar bem a distribuição.

Essa limitação motiva uma estratégia adaptativa:

> Top-P.

---

# 🎯 Top-P

Top-P também é chamado de:

> nucleus sampling.

Em vez de escolher uma quantidade fixa de tokens, Top-P mantém o menor  
conjunto de tokens cuja probabilidade acumulada atinge um determinado limite.

---

## 🧠 Exemplo

Temos:

```
A → 40%
B → 25%
C → 15%
D → 10%
E → 6%
F → 4%
```

Se:

```
Top-P = 0.80
```

somamos:

```
A = 40%
A + B = 65%
A + B + C = 80%
```

Portanto, o conjunto utilizado será:

```
A
B
C
```

Os demais são removidos.

---

## 🔄 Top-P é adaptativo

Essa é a diferença fundamental.

### Top-K

```
"Quero os K tokens mais prováveis."
```

### Top-P

```
"Quero tokens suficientes para representar P da massa
de probabilidade."
```

---

## 🆚 Top-K vs Top-P

### Top-K

Controla:

```
quantidade de tokens candidatos
```

Exemplo:

```
K = 5
```

Sempre consideramos até os cinco tokens mais prováveis.

---

### Top-P

Controla:

```
massa acumulada de probabilidade
```

Exemplo:

```
P = 0.90
```

Consideramos tokens até acumular aproximadamente 90% da distribuição.

---

## 📊 Exemplo comparativo

Distribuição:

```
A → 55%
B → 20%
C → 10%
D → 7%
E → 5%
F → 3%
```

### Top-K = 3

Selecionamos:

```
A
B
C
```

---

### Top-P = 0.75

Somamos:

```
A = 55%
A + B = 75%
```

Selecionamos apenas:

```
A
B
```

Portanto:

```
Top-K = 3
```

e:

```
Top-P = 0.75
```

não precisam produzir o mesmo conjunto de candidatos.

---

## 🌡️ Relação com Temperature

Temperature e Top-K/Top-P atuam em partes diferentes do processo.

### Temperature

Modifica a forma da distribuição.

```
Logits
   ↓
Temperature
   ↓
Distribuição mais concentrada ou espalhada
```

### Top-K / Top-P

Restringem quais tokens continuam elegíveis.

```
Distribuição
   ↓
Filtro de candidatos
```

Podemos visualizar:

```
Logits
   ↓
Temperature
   ↓
Softmax
   ↓
Probabilidades
   ↓
Top-K / Top-P
   ↓
Sampling
```

---

## 🧠 Analogia mental

Imagine uma eleição.

### Temperature

Muda o quanto os candidatos favoritos dominam a disputa.

### Top-K

Diz:

> apenas os K candidatos mais votados continuam.

### Top-P

Diz:

> continuem candidatos suficientes para representar P% dos votos.

Essa analogia é apenas um modelo mental.

---

## 🎲 Relação com diversidade

Quanto mais restritivo o conjunto:

```
menos candidatos
      ↓
menor espaço de geração
```

Quanto mais amplo:

```
mais candidatos
      ↓
maior diversidade potencial
```

Mas isso não significa automaticamente:

```
mais diversidade = melhor
```

ou:

```
menos diversidade = melhor
```

Depende da tarefa.

---

## ⚠️ Top-K e Top-P não verificam fatos

Assim como temperature:

```
Top-K
Top-P
```

não são mecanismos de verificação factual.

Eles controlam:

> quais tokens participam da geração.

Não controlam:

> se a afirmação resultante é verdadeira.

Portanto:

```
controle de sampling
        ≠
controle de factualidade
```

---

## 🧪 Exemplo de tarefa estruturada

Imagine uma tarefa:

> Classifique o sentimento como POSITIVO, NEGATIVO ou NEUTRO.

Nesse caso queremos pouca liberdade.

A aplicação provavelmente deve utilizar mecanismos ainda mais fortes  
de controle de saída.

Já em uma tarefa como:

> Gere dez ideias de nomes para uma startup de astronomia.

uma distribuição mais ampla pode ser desejável.

---

## 🧠 Não existe configuração universal

Não devemos pensar:

```
Top-P = 0.9
é sempre melhor
```

ou:

```
Top-K = 40
é sempre ideal
```

A escolha depende:

- da tarefa;
- do modelo;
- do provider;
- das demais configurações;
- do comportamento desejado.

---

## 🔬 Configuração é hipótese

Nossa mentalidade será:

```
Requisito
   ↓
Hipótese
   ↓
Configuração
   ↓
Experimento
   ↓
Métrica
   ↓
Decisão
```

Não:

```
copiei parâmetros de um tutorial
        ↓
produção
```

---

## 🔗 Relação com não determinismo

Agora podemos abrir ainda mais nosso pipeline:

```
Prompt
   ↓
Modelo
   ↓
Logits
   ↓
Temperature
   ↓
Softmax
   ↓
Distribuição
   ↓
Top-K / Top-P
   ↓
Sampling
   ↓
Token
   ↓
Novo contexto
   ↓
Repetir
```

Esse conjunto de mecanismos ajuda a explicar por que a geração pode produzir  
respostas diferentes.

---

## 🧩 Conceitos deste bloco

- [[Top-K]]
- [[Top-P]]
- [[Nucleus Sampling]]
- [[Temperature]]
- [[Sampling]]
- [[Softmax]]
- [[Distribuição de Probabilidade]]
- [[Não determinismo]] 

## 🧪 Meu exemplo

Considere:

```
A → 50%
B → 20%
C → 15%
D → 10%
E → 5%
```

Responda:

1. Quais tokens permanecem com Top-K = 3?
2. Quais tokens permanecem com Top-P = 0.70?
3. Quais permanecem com Top-P = 0.90?

---

## ❓ Perguntas de revisão

1. O que Top-K controla?
2. O que Top-P controla?
3. Qual dos dois utiliza uma quantidade fixa de candidatos?
4. Qual deles se adapta à forma da distribuição?
5. O que significa nucleus sampling?
6. Qual é a diferença entre Temperature e Top-P?
7. Top-P baixo garante factualidade?
8. Por que os parâmetros devem ser tratados experimentalmente? 

## 🧪 Meu exemplo

Escolha uma tarefa.

### Zero-shot

```
TODO
```

### Few-shot

```
TODO
```

Explique qual diferença espera observar.

---

## ❓ Perguntas de revisão

1. O que é In-context Learning?
2. Os pesos do modelo mudam durante ICL?
3. O que caracteriza uma tarefa zero-shot?
4. O que caracteriza few-shot?
5. Que tipos de informação podem ser transmitidos pelos exemplos?
6. Por que few-shot consome contexto?
7. Mais exemplos sempre significam resultado melhor?
8. Qual é a diferença fundamental entre ICL e fine-tuning?
9. Por que exemplos ruins podem prejudicar o comportamento?
10. Como escolher entre zero-shot, few-shot e fine-tuning?

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
