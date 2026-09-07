# Como contribuir

Obrigado pelo interesse no projeto.

## Objetivo do projeto

Construir uma trilha aberta, prática e em português brasileiro sobre
Engenharia de IA Generativa, Design Patterns e Sistemas Agênticos.

O princípio que guia todo o material:

> Conceito → Implementação → Experimento → Avaliação → Aplicação

Contribuições são bem-vindas quando reforçam esse princípio: explicações mais
claras, experimentos reproduzíveis, correções técnicas e avaliações honestas.

---

## Antes de contribuir

Leia:

- [README.md](README.md) — visão geral e organização
- [REFERENCIAS.md](REFERENCIAS.md) — regras de citação de fontes
- [SECURITY.md](SECURITY.md) — política de segurança
- [LICENSE](LICENSE) e [LICENSE-CONTENT.md](LICENSE-CONTENT.md) — licenciamento

Ao contribuir, você concorda em licenciar sua contribuição sob MIT (código) e
CC BY 4.0 (conteúdo).

---

## Como abrir issues

Use os templates disponíveis:

- **Bug** — algo não funciona como documentado.
- **Melhoria** — proposta de aprimoramento de conteúdo, código ou estrutura.
- **Novo laboratório** — proposta de experimento reproduzível.

Ao abrir uma issue:

1. Verifique se já não existe uma issue equivalente.
2. Seja específico: um problema por issue.
3. Inclua contexto suficiente para reprodução.
4. Escreva em português brasileiro sempre que possível.

Não abra issue pública para vulnerabilidades ou exposição de credenciais —
siga o [SECURITY.md](SECURITY.md).

---

## Padrão de branch

Crie uma branch a partir de `main`:

```
<tipo>/<descricao-curta-em-kebab-case>
```

Tipos aceitos:

| Tipo    | Uso                                    |
|---------|----------------------------------------|
| `aula`  | conteúdo de aula                       |
| `node`  | conceito no Vault                      |
| `lab`   | laboratório ou experimento             |
| `docs`  | documentação do repositório            |
| `fix`   | correção                               |
| `infra` | ambiente, empacotamento, ferramentas   |

Exemplos:

```
lab/temperature-e-diversidade
node/foundation-model
fix/link-quebrado-no-atlas
```

---

## Padrão de commit

Mensagens **curtas, em português brasileiro, no imperativo**.

Sem prefixos, sem ponto final, primeira letra minúscula.

Exemplos:

```
adiciona experimento de temperature
documenta conceito de foundation model
corrige configuração do ambiente
```

Evite:

```
Adicionado experimento de temperature     (não está no imperativo)
feat: add temperature experiment          (não é PT-BR, usa prefixo)
updates                                   (vago demais)
```

Um commit deve conter uma mudança coerente. Prefira vários commits pequenos a
um commit grande e misturado.

---

## Padrão de pull request

1. Abra o PR contra `main`.
2. Preencha o template de PR por completo.
3. Descreva **o que** mudou, **por quê** e **como validar**.
4. Relacione a issue correspondente, quando houver.
5. Mantenha o PR focado — um assunto por PR.
6. Garanta que o repositório continua reproduzível após a mudança.

---

## Citação de fontes

Toda contribuição que parta de material externo **deve citar a fonte**.

Regras:

1. Cite a fonte de onde o conceito veio.
2. Reescreva a explicação com suas próprias palavras.
3. Não cole trechos longos de material protegido por direitos autorais.
4. Não reproduza figuras, tabelas ou diagramas de obras protegidas.

O formato de citação está em [REFERENCIAS.md](REFERENCIAS.md).

---

## Material protegido e segredos

**Nunca** envie para este repositório:

- livros, PDFs ou capítulos de obras protegidas;
- figuras ou diagramas copiados de obras protegidas;
- chaves de API, tokens ou credenciais;
- arquivos `.env` com valores reais;
- datasets com dados pessoais ou de uso restrito.

Contribuições que contenham qualquer um desses itens serão recusadas.

Se você expuser uma credencial por acidente, **revogue-a imediatamente** e
avise conforme o [SECURITY.md](SECURITY.md).

---

## Idioma

A preferência é por **português brasileiro** em textos, comentários, commits,
issues e PRs.

Termos técnicos consagrados em inglês podem ser mantidos no original quando a
tradução prejudicar a clareza (*prompt*, *token*, *embedding*, *fine-tuning*).

---

## Reprodutibilidade

Código e experimentos devem ser reproduzíveis por outra pessoa.

Um experimento reproduzível registra:

- a versão do Python e das dependências relevantes;
- o modelo e o provider utilizados;
- os parâmetros de inferência (temperature, top-p, seed quando disponível);
- o dataset ou as entradas usadas;
- as métricas e como foram calculadas;
- as limitações observadas.

Resultados não determinísticos devem ser declarados como tal. Não apresente
uma execução isolada como se fosse um resultado estável.
