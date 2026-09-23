# Prompt para criar um portfólio acadêmico com GitHub como banco de dados

Copie o prompt abaixo e substitua os valores entre colchetes antes de enviá-lo a uma IA de programação.

---

## Prompt

Crie um portfólio acadêmico estático, moderno e responsivo, publicado pelo GitHub Pages. O projeto não deve possuir backend nem banco de dados tradicional. O próprio repositório público do GitHub deve funcionar como fonte de dados para as publicações.

### Informações pessoais

- Nome: `[SEU NOME]`
- Curso: `[SEU CURSO]`
- Instituição: `[SUA INSTITUIÇÃO]`
- Disciplina: `[SUA DISCIPLINA]`
- Ano: `[ANO]`
- LinkedIn: `[URL DO LINKEDIN]`
- Usuário ou organização do GitHub: `[USUARIO_GITHUB]`
- Nome do repositório: `[NOME_REPOSITORIO]`
- Branch principal: `[BRANCH_PRINCIPAL, normalmente main]`
- Branches adicionais opcionais: `[BRANCH_1, BRANCH_2]`

### Objetivo

Construa uma página única em HTML, CSS e JavaScript puros, sem framework e sem etapa de build. O site deve poder ser hospedado diretamente no GitHub Pages e possuir as seguintes seções:

1. Apresentação pessoal;
2. Sobre mim e competências;
3. Reflexões;
4. Atividades;
5. Avaliações;
6. Rodapé com informações pessoais e link profissional.

Use uma interface sóbria, organizada e adequada a um portfólio acadêmico. Garanta boa leitura em celulares e computadores, navegação por âncoras, menu móvel acessível, contraste adequado e estados de carregamento, conteúdo vazio e erro.

### Estrutura do repositório

Use esta estrutura:

```text
index.html
README.md
img/
reflexoes/
  README.md
atividades/
  README.md
avaliacoes/
  README.md
```

As pastas `reflexoes`, `atividades` e `avaliacoes` devem funcionar como coleções. O site deve descobrir os arquivos automaticamente, sem manter uma lista manual dentro do `index.html`.

### GitHub como fonte de dados

Em produção, consulte a API pública de conteúdo do GitHub:

```text
https://api.github.com/repos/[USUARIO_GITHUB]/[NOME_REPOSITORIO]/contents/[PASTA]?ref=[BRANCH]
```

Requisitos:

- Não utilizar token, segredo ou chave de API no frontend;
- Considerar que o repositório é público;
- Carregar a branch principal e, opcionalmente, branches adicionais configuradas em uma lista;
- Combinar os resultados das branches e remover duplicatas pelo tipo e nome do item;
- Se um mesmo caminho existir em mais de uma branch, dar prioridade à última branch configurada;
- Se uma branch adicional não existir, ignorá-la sem impedir o carregamento da branch principal;
- Tratar erros da API com uma mensagem compreensível na interface;
- Informar no README que a API pública do GitHub possui limite de requisições para usuários não autenticados.

Centralize a configuração em um objeto semelhante a este:

```js
const repository = {
  owner: "[USUARIO_GITHUB]",
  name: "[NOME_REPOSITORIO]",
  branch: "[BRANCH_PRINCIPAL]",
  additionalBranches: [],
  folders: {
    reflexao: "reflexoes",
    atividade: "atividades",
    avaliacao: "avaliacoes"
  }
};
```

### Formato das publicações

Um arquivo Markdown colocado diretamente em uma das coleções deve criar um card automaticamente. O arquivo pode possuir front matter simples:

```md
---
title: Título da publicação
date: 2026-09-22
description: Pequena descrição exibida no card.
---

# Título da publicação

Conteúdo completo.
```

Implemente a leitura dos campos `title`, `date` e `description`. Quando eles não existirem:

- Usar o primeiro título `#` como título do card;
- Usar o nome do arquivo como alternativa;
- Inferir a data quando o nome começar com `AAAA-MM-DD`;
- Usar o início do texto como descrição.

Ordene os cards da data mais recente para a mais antiga.

### Abertura dos arquivos

- Para arquivos `.md`, o botão deve abrir o preview nativo do GitHub usando o endereço `html_url`, com rota `/blob/`, e nunca o endereço bruto de `raw.githubusercontent.com`;
- Arquivos `.docx` podem permanecer no repositório para edição e compartilhamento, mas não devem criar cards nem aparecer como anexos no site;
- Outros anexos, como `.pdf`, imagens e códigos, podem ser exibidos como botões para abertura ou download;
- Os links devem abrir em nova aba com `target="_blank"` e `rel="noreferrer"`;
- Todo texto inserido dinamicamente deve ser escapado antes de ser adicionado ao HTML.

### Publicações com anexos

Aceite também uma subpasta dentro de uma coleção. Nela:

- O arquivo `README.md` define título, data e descrição do card;
- Os demais arquivos aparecem como anexos;
- Arquivos `.docx` continuam ocultos;
- Se não existir `README.md`, use o nome da pasta como título;
- Se não houver anexos visíveis, apresente um botão para abrir a pasta no GitHub usando a rota `/tree/`.

Exemplo:

```text
atividades/
  2026-09-22-atividade-01/
    README.md
    algoritmo.py
    relatorio.pdf
    versao-editavel.docx
```

### Pré-visualização local

Quando o site estiver em `localhost` ou `127.0.0.1`, ele deve ler as listagens de diretórios fornecidas por um servidor HTTP local, em vez de consultar o conteúdo remoto da API.

O modo local deve:

- Descobrir automaticamente os arquivos atuais das três pastas;
- Ler localmente os Markdown para montar os cards;
- Ocultar os `.docx` da mesma maneira que em produção;
- Fazer os botões dos Markdown apontarem para o preview do arquivo na branch configurada no GitHub;
- Construir links de arquivos com `/blob/` e links de pastas com `/tree/`.

Inclua no README este comando para testar localmente:

```bash
python3 -m http.server 8000
```

O site deverá ficar acessível em `http://localhost:8000/`.

### Requisitos técnicos

- Manter todo o site em um único `index.html` quando isso não prejudicar a organização;
- Usar HTML semântico e atributos de acessibilidade;
- Usar CSS responsivo, sem bibliotecas obrigatórias;
- Usar JavaScript assíncrono com `fetch`, `async` e `await`;
- Não usar banco de dados externo;
- Não exigir instalação de dependências para executar o site;
- Não incluir credenciais no código;
- Não criar uma página HTML para cada publicação;
- Documentar como adicionar publicações, testar localmente e publicar no GitHub Pages.

### Validação obrigatória

Antes de concluir:

1. Inicie um servidor HTTP local;
2. Confirme que as três seções carregam seus diretórios locais;
3. Adicione um Markdown de teste com front matter e confirme título, data e descrição no card;
4. Confirme que nenhum `.docx` aparece no site;
5. Confirme que o botão de Markdown aponta para `github.com/.../blob/...`, e não para `raw.githubusercontent.com`;
6. Confirme que o layout funciona em uma tela de celular e em uma tela de computador;
7. Confirme que o site publicado usa a API do GitHub e não depende da listagem local do servidor.

Entregue todos os arquivos necessários, um README com instruções claras e um resumo das decisões tomadas.

---

## Observação

Esse modelo funciona melhor com repositórios públicos. Em um repositório privado, a API exigiria autenticação, e colocar um token diretamente no JavaScript do site seria inseguro.