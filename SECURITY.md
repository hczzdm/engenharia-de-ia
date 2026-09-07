# Política de segurança

Este é um repositório educacional público. Ainda assim, ele lida com chaves de
API de provedores de modelos, e por isso segue uma política explícita.

---

## Como relatar um problema de segurança

**Não abra uma issue pública** para vulnerabilidades ou exposição de
credenciais.

Use um destes canais privados:

1. **GitHub Security Advisories** — aba *Security* → *Report a vulnerability*.
2. Contato direto com o mantenedor do repositório.

Ao relatar, inclua:

- descrição do problema;
- passos para reproduzir;
- impacto potencial;
- sugestão de correção, se houver.

Não inclua a credencial completa no relato. Um prefixo curto é suficiente para
identificá-la.

---

## Regras para chaves e credenciais

**Nunca** publique neste repositório:

- chaves de API (`OPENAI_API_KEY`, `ANTHROPIC_API_KEY`, `GOOGLE_API_KEY`, etc.);
- tokens de acesso de qualquer serviço;
- credenciais de banco de dados;
- certificados ou chaves privadas (`*.pem`, `*.key`);
- arquivos `credentials.json` ou `secrets.json`;
- arquivos `.env` com valores reais.

O arquivo `.env` está no `.gitignore` e **não deve ser commitado em hipótese
alguma**.

Apenas `.env.exemplo` é versionado, e ele contém somente nomes de variáveis
com valores vazios — nunca valores reais.

---

## Como configurar suas chaves localmente

```bash
cp .env.exemplo .env
```

Edite o `.env` com suas chaves reais. Ele já está ignorado pelo Git.

Antes de qualquer commit, confirme:

```bash
git status
git ls-files | grep -E '\.env$|\.pem$|\.key$|credentials\.json|secrets\.json'
```

O segundo comando deve retornar vazio.

---

## Se uma chave for exposta

Se uma credencial for commitada ou publicada, mesmo por engano:

1. **Revogue a chave imediatamente** no painel do provedor. Este é o primeiro
   passo — antes de qualquer limpeza do histórico.
2. **Gere uma nova chave** e atualize seu `.env` local.
3. Avise o mantenedor do repositório por canal privado.
4. Só então trate a remoção do histórico do Git.

Remover o commit **não** torna a chave segura. Uma chave que chegou a um
repositório público deve ser considerada comprometida de forma permanente,
independentemente do que aconteça com o histórico.

---

## Boas práticas ao trabalhar com LLMs

- Não envie dados pessoais ou sensíveis para APIs de modelos.
- Não versione respostas de modelos que contenham dados sensíveis.
- Revise notebooks antes de commitar: a saída das células pode conter chaves,
  caminhos locais ou dados de entrada.
- Limpe as saídas dos notebooks quando não forem parte do resultado
  documentado.

---

## Escopo

Esta política cobre o conteúdo deste repositório.

Vulnerabilidades em serviços de terceiros (provedores de modelos, bibliotecas,
Obsidian) devem ser reportadas diretamente aos respectivos mantenedores.
