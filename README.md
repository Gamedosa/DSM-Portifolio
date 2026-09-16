# Portfólio DSM

Portfólio acadêmico de Gabriel Melo para a disciplina de Algoritmos e Lógica de Programação da Fatec Indaiatuba.

## Estrutura de conteúdo

- `reflexoes/`: textos e anexos das reflexões.
- `atividades/`: atividades, códigos e arquivos de entrega.
- `avaliacoes/`: avaliações e documentos relacionados.

## Adicionar uma publicação

O site lê automaticamente as três pastas pela API pública do GitHub. Não é necessário editar o `index.html` nem manter um catálogo.

### Arquivo individual

Adicione o arquivo diretamente na categoria. Um Markdown pode informar título, data e descrição:

```md
---
title: Reflexão da aula 01
date: 2026-09-16
description: Síntese dos conceitos estudados na aula.
---

# Reflexão da aula 01

Texto completo da reflexão.
```

Sem esses metadados, o primeiro título `#` vira o título do card e o texto do arquivo vira a descrição. Uma data no início do nome, como `2026-09-16-aula-01.md`, também é reconhecida.

### Publicação com anexos

Crie uma subpasta na categoria. O `README.md` da subpasta define o card, e todos os outros arquivos nela aparecem automaticamente como anexos:

```text
atividades/
  2026-09-16-atividade-01/
    README.md
    algoritmo.py
    relatorio.pdf
```

Pastas vazias não são versionadas pelo Git e, por isso, não aparecem no site.

## Publicar no GitHub

```bash
git add .
git commit -m "Adiciona novo registro ao portfólio"
git push
```

O site consulta a branch `main`. Se o conteúdo estiver em outra branch, como `portifolio`, ele aparecerá depois do merge em `main` e do `push`.