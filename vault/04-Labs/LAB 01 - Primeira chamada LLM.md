
## 🎯 Problema

Uma única resposta de um LLM é suficiente para compreender
o comportamento do sistema?

---

## 🧠 Hipótese

Ao executar repetidamente o mesmo prompt, poderemos observar variação
nas respostas produzidas pelo modelo.

---

## 🔬 Variável independente

Configuração da geração e número da execução.

---

## 📊 Variáveis observadas

- resposta;
- latência;
- tokens de entrada;
- tokens de saída;
- modelo;
- timestamp.

---

## 🧪 Experimento inicial

Executar o mesmo prompt pelo menos 10 vezes.

```text
Prompt fixo
    ↓
Execução 01
Execução 02
Execução 03
...
Execução 10
    ↓
Comparação
````

---

## ❓ Pergunta experimental

As respostas permanecem idênticas?

Se não:

- onde variam?
- quanto variam?
- a informação central permanece?
- o formato permanece? 


# 🧪 Experimento 2 — Efeito da Temperature

## 🎯 Objetivo

Observar como diferentes valores de temperature afetam
a diversidade e a consistência das respostas.

---

## 🔬 Variável independente

Temperature.

Valores inicialmente testados:

```text
0.0
0.3
0.7
1.0
````

Os valores efetivamente suportados dependerão do provider e  
do modelo utilizado.

---

## 🔒 Variáveis controladas

Manter constantes:

- prompt;
- modelo;
- system prompt;
- demais parâmetros de geração.

---

## 📊 Variáveis observadas

- conteúdo;
- diversidade;
- consistência;
- tamanho da resposta;
- aderência ao formato;
- latência;
- tokens.

---

## 🧪 Procedimento

Para cada valor de temperature:

1. executar o mesmo prompt várias vezes;
2. registrar todas as respostas;
3. comparar as respostas entre si;
4. observar mudanças de diversidade;
5. registrar resultados.

---

## 🧠 Hipótese

Temperatures menores deverão produzir respostas mais concentradas  
em continuações de alta probabilidade.

Temperatures maiores deverão aumentar a diversidade das respostas.

---

## ❓ Pergunta experimental

A mudança de temperature altera de forma observável  
a consistência e a diversidade das respostas?

````

Agora nosso LAB 01 começa a ficar bem interessante:

```text
Experimento 1
   ↓
mesmo prompt
múltiplas execuções
   ↓
não determinismo

Experimento 2
   ↓
variar temperature
   ↓
efeito na distribuição
````

---

# 🧠 O QUE PRECISA FICAR NA CABEÇA

A cadeia é:

```
Logit
  ↓
Temperature
  ↓
Softmax
  ↓
Probabilidades
  ↓
Sampling
```

E:

```
Temperature baixa
=
distribuição mais concentrada
```

```
Temperature alta
=
distribuição mais espalhada
``` 


# 🧪 Experimento 3 — Estratégias de Sampling

## 🎯 Objetivo

Investigar como mecanismos de restrição de candidatos alteram
a diversidade das respostas.

---

## 🔬 Parâmetros

Quando suportados pelo modelo/provider:

- Top-K;
- Top-P.

---

## 🔒 Variáveis controladas

Manter constantes:

- prompt;
- modelo;
- system prompt;
- temperature;
- número de execuções.

---

## 🧪 Experimento A — Top-P

Executar o mesmo prompt utilizando diferentes valores de Top-P.

Exemplo inicial:

```text
0.50
0.75
0.90
1.00
````

---

## 🧪 Experimento B — Top-K

Se suportado pelo provider, repetir utilizando diferentes valores de K.

---

## 📊 Observar

- diversidade lexical;
- diferença entre respostas;
- consistência;
- aderência às instruções;
- estrutura;
- tokens;
- latência.

---

## 🧠 Hipótese

Restringir o conjunto de candidatos deverá reduzir o espaço  
de possíveis continuações.

Configurações menos restritivas deverão permitir maior diversidade.

---

## ⚠️ Observação

Top-K e Top-P não serão tratados como parâmetros universais.

Primeiro verificaremos quais controles o modelo e o provider  
realmente disponibilizam.



Agora o LAB 01 já possui uma progressão bonita:

```text
🧪 Experimento 1
Mesmo prompt
→ observar não determinismo

          ↓

🌡️ Experimento 2
Temperature
→ modificar distribuição

          ↓

🎯 Experimento 3
Top-K / Top-P
→ restringir candidatos
````

---

# 🧠 O QUE PRECISA FICAR NA CABEÇA

```
TEMPERATURE
=
muda a forma da distribuição
```

```
TOP-K
=
mantém K candidatos
```

```
TOP-P
=
mantém candidatos suficientes
para atingir P da probabilidade acumulada
```

E juntos:

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
   ↓
Token
``` 

```
# 🔬 Extensão opcional — Decoding e penalidades

Caso o modelo/provider utilizado exponha esses controles,
investigar também:

- Beam Search;
- repetition penalty;
- demais penalidades disponíveis.

Não comparar parâmetros com o mesmo nome entre providers
sem verificar primeiro sua semântica e documentação.
```

Isso evita transformar o LAB 01 em um polvo com quinze braços 🐙.

---

# 🧠 O QUE PRECISA FICAR NA CABEÇA

Agora temos um pequeno mapa do decoding:

```
                    GERAÇÃO
                       │
      ┌────────────────┼────────────────┐
      ↓                ↓                ↓
   Greedy           Sampling        Beam Search
                       │
             ┌─────────┼──────────┐
             ↓         ↓          ↓
        Temperature   Top-K      Top-P
```

E paralelamente:

```
Penalidades
    ↓
modificam preferências
durante a geração
```

Mas todos eles continuam trabalhando essencialmente sobre:

> **como o modelo gera.**

Não garantem:

> **que aquilo que ele gera seja verdadeiro.** 


