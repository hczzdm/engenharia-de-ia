# Engenharia de IA Generativa

Trilha aberta e prática em português brasileiro sobre Engenharia de IA
Generativa, Design Patterns e Sistemas Agênticos.

O projeto combina teoria, experimentação e construção de sistemas reais.

Princípio:

> Conceito → Implementação → Experimento → Avaliação → Aplicação

---

## Objetivos

- Construir entendimento conceitual sólido antes de escrever código.
- Transformar cada conceito em um experimento reproduzível.
- Avaliar sistemas de IA generativa com critérios explícitos, não com impressão.
- Documentar o caminho inteiro em português brasileiro.
- Produzir artefatos reais de portfólio, não exercícios descartáveis.

Temas cobertos ao longo da trilha:

- Engenharia de IA Generativa e AI Engineering
- Generative AI Design Patterns
- Prompts, contexto e context engineering
- RAG (Retrieval-Augmented Generation)
- Reasoning
- Avaliação de LLMs e benchmarks
- Sistemas agênticos
- Guardrails
- Engenharia de produção para GenAI

---

## Organização do repositório

```
engenharia-de-ia/
├── src/engenharia_ia/   # pacote Python do projeto (src-layout)
├── capitulos/           # material executável por capítulo
├── dados/               # datasets utilizados nos laboratórios
├── projetos/            # projetos maiores e artefatos de portfólio
├── scripts/             # utilitários de apoio
├── vault/               # Vault Obsidian com o conhecimento autoral
├── .env.exemplo         # modelo de variáveis de ambiente (sem valores reais)
└── pyproject.toml       # empacotamento e ferramentas
```

---

## Vault Obsidian

O diretório `vault/` é um Vault Obsidian independente. Ele deve ser aberto
diretamente no Obsidian — não o repositório inteiro.

```
vault/
├── HOME.md
├── 00-Atlas/       # mapas amplos de um domínio
├── 01-Nodes/       # conceitos atômicos e reutilizáveis
├── 02-Jornadas/    # fluxos que conectam vários conceitos
├── 03-Aulas/       # narrativas didáticas estruturadas
├── 04-Labs/        # experimentos reproduzíveis
├── 05-Projetos/    # aplicações maiores
├── 06-Biblioteca/  # referências e fichamentos
├── 07-Pesquisa/    # investigações abertas
├── 08-Mapas/       # mapas visuais
└── 99-Templates/   # templates de Node, Aula e Lab
```

Para usar os templates: `Settings → Core plugins → Templates →
Template folder location → 99-Templates`.

Apenas plugins nativos são utilizados. Nenhum plugin comunitário é necessário.

---

## Capítulos

### Capítulo 1 — Fundamentos de Engenharia de IA Generativa

1. Design Patterns e AI Engineering
2. Prompts e Contexto
3. APIs de Modelos

Os capítulos seguintes serão adicionados conforme a trilha avança.

---

## Laboratórios

Cada laboratório parte de uma hipótese explícita e registra problema, conceitos
envolvidos, ambiente, procedimento, métricas, resultados, interpretação e
limitações.

Um laboratório só é considerado concluído quando outra pessoa consegue
reproduzi-lo a partir do que está documentado.

---

## Projetos

Aplicações maiores que integram vários conceitos da trilha e servem como
artefatos de portfólio. Ficam em `projetos/` e são documentados no Vault.

---

## Metodologia

O ciclo aplicado a cada tema:

1. **Conceito** — entender e escrever o conceito com palavras próprias.
2. **Implementação** — traduzir o conceito em código mínimo.
3. **Experimento** — variar parâmetros e observar o comportamento.
4. **Avaliação** — medir com critérios definidos antes do experimento.
5. **Aplicação** — integrar o que foi aprendido em algo utilizável.

---

## Idioma

O conteúdo é escrito em português brasileiro.

Termos técnicos consagrados em inglês são mantidos no original quando a
tradução prejudicaria a clareza (por exemplo: *prompt*, *token*, *embedding*,
*fine-tuning*).

---

## Referências

As referências bibliográficas da trilha estão em [REFERENCIAS.md](REFERENCIAS.md).

Entre elas está *Generative AI Design Patterns*, de Valliappa Lakshmanan e
Hannes Hapke (O'Reilly Media), utilizado como referência de estudo.

Este repositório é independente e autoral. Ele **não** redistribui livros,
capítulos, figuras ou qualquer conteúdo integral protegido por direitos
autorais.

---

## Licenças

Este projeto usa licenciamento duplo:

- **Código-fonte original** → [MIT License](LICENSE)
- **Aulas, notas, diagramas e documentação autoral** → [CC BY 4.0](LICENSE-CONTENT.md)

Materiais de terceiros permanecem sob suas respectivas licenças e não são
cobertos pelas licenças deste repositório.

---

## Status

**Capítulo 1 — Fundamentos de Engenharia de IA Generativa**

Primeiras aulas:

1. Design Patterns e AI Engineering
2. Prompts e Contexto
3. APIs de Modelos

Em construção. A estrutura do Vault e a infraestrutura Python estão prontas;
o conteúdo das aulas está em desenvolvimento.

---

## Contribuindo

Veja [CONTRIBUTING.md](CONTRIBUTING.md) e a política em [SECURITY.md](SECURITY.md).
