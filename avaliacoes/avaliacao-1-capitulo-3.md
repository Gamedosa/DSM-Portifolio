---
title: Avaliação 1 - Estruturas de controle
date: 2026-09-22
description: Síntese do capítulo 3 e resolução de quatro exercícios em algoritmos.
---

# Avaliação 1 - Estruturas de controle

**Disciplina:** Algoritmos e Lógica de Programação  
**Tema:** Capítulo 3 - Estruturas de controle  
**Integrantes:** Felipe Marinho, Gabriel Melo, Matheus Beccari, João Mateus M, João Victor Lima, Thierry Araujo

## 1. Síntese conceitual

As estruturas de controle determinam a ordem em que as instruções de um algoritmo são executadas. Por meio delas, é possível organizar uma solução em etapas, tomar decisões de acordo com determinadas condições e repetir ações quando necessário.

### 1.1 Fluxo de execução

O fluxo de execução é o caminho percorrido pelo algoritmo desde o início até o fim. Sem uma estrutura de controle diferente, as instruções são executadas na ordem em que foram escritas. Esse fluxo pode ser alterado por decisões e repetições.

### 1.2 Estrutura sequencial

Na estrutura sequencial, cada instrução é executada uma vez, de cima para baixo. Geralmente, o algoritmo recebe dados de entrada, realiza um processamento e apresenta uma saída.

Exemplo de sequência:

1. Ler duas notas;
2. Calcular a média;
3. Mostrar o resultado.

Essa estrutura é adequada quando todas as ações devem acontecer sem a necessidade de escolher caminhos ou repetir etapas.

### 1.3 Estrutura de seleção

A estrutura de seleção permite que o algoritmo tome decisões. Uma condição é avaliada e, de acordo com seu resultado, um bloco de instruções é executado.

As formas mais comuns são:

- **Seleção simples:** executa uma ação somente quando a condição é verdadeira;
- **Seleção composta:** escolhe entre uma ação para a condição verdadeira e outra para a condição falsa;
- **Seleção encadeada:** verifica mais de duas possibilidades por meio de condições sucessivas.

As condições utilizam operadores relacionais, como `>`, `<`, `=`, `>=` e `<=`, e podem combinar testes com operadores lógicos, como `e`, `ou` e `não`.

### 1.4 Estrutura de repetição

A estrutura de repetição executa um conjunto de instruções várias vezes. Ela evita escrever a mesma ação repetidamente e é útil quando uma tarefa deve continuar até que uma condição seja atendida.

Entre as formas de repetição estão:

- **Enquanto:** verifica a condição antes de cada repetição;
- **Repita até:** executa o bloco ao menos uma vez e verifica a condição no final;
- **Para:** é utilizada quando a quantidade de repetições é conhecida.

Uma repetição deve possuir uma condição de parada. Caso essa condição nunca seja alcançada, o algoritmo entra em um laço infinito.

### 1.5 Importância das estruturas de controle

As estruturas sequenciais, de seleção e de repetição podem ser combinadas para resolver problemas maiores. O ponto principal é escolher a estrutura mais adequada para cada situação e manter o algoritmo claro. Uma boa solução deve apresentar uma ordem lógica, condições compreensíveis e repetições com início e fim bem definidos.

## 2. Exercícios resolvidos

### Exercício 1 - Cálculo da média

**Enunciado:** elabore um algoritmo que leia duas notas, calcule a média aritmética e mostre o resultado.

**Estrutura utilizada:** sequencial.

#### Raciocínio

1. Receber as duas notas;
2. Somar os valores;
3. Dividir a soma por 2;
4. Mostrar a média.

#### Algoritmo

```text
algoritmo "calcular_media"
var
   nota1, nota2, media: real
inicio
   escreva("Digite a primeira nota: ")
   leia(nota1)
   escreva("Digite a segunda nota: ")
   leia(nota2)

   media <- (nota1 + nota2) / 2

   escreva("Média: ", media)
fimalgoritmo
```

**Exemplo:** para as notas 7 e 9, a média calculada é 8.

### Exercício 2 - Verificação de maioridade

**Enunciado:** elabore um algoritmo que leia a idade de uma pessoa e informe se ela é maior ou menor de idade.

**Estrutura utilizada:** seleção composta.

#### Raciocínio

1. Receber a idade;
2. Verificar se a idade é maior ou igual a 18;
3. Mostrar a mensagem correspondente ao resultado da condição.

#### Algoritmo

```text
algoritmo "verificar_maioridade"
var
   idade: inteiro
inicio
   escreva("Digite a idade: ")
   leia(idade)

   se idade >= 18 entao
      escreva("Maior de idade")
   senao
      escreva("Menor de idade")
   fimse
fimalgoritmo
```

**Exemplo:** para a idade 20, o algoritmo mostra “Maior de idade”.

### Exercício 3 - Situação do aluno

**Enunciado:** elabore um algoritmo que leia a média de um aluno. Se a média for maior ou igual a 7, informe “Aprovado”. Se estiver entre 5 e 6,9, informe “Recuperação”. Caso contrário, informe “Reprovado”.

**Estrutura utilizada:** seleção encadeada.

#### Raciocínio

1. Receber a média do aluno;
2. Verificar primeiro se ela é maior ou igual a 7;
3. Se não for, verificar se é maior ou igual a 5;
4. Mostrar uma das três situações possíveis.

#### Algoritmo

```text
algoritmo "situacao_aluno"
var
   media: real
inicio
   escreva("Digite a média do aluno: ")
   leia(media)

   se media >= 7 entao
      escreva("Aprovado")
   senao
      se media >= 5 entao
         escreva("Recuperação")
      senao
         escreva("Reprovado")
      fimse
   fimse
fimalgoritmo
```

**Exemplo:** para a média 6,5, o algoritmo mostra “Recuperação”.

### Exercício 4 - Soma de cinco números

**Enunciado:** elabore um algoritmo que leia cinco números, calcule a soma de todos eles e mostre o resultado.

**Estrutura utilizada:** repetição com `para`.

#### Raciocínio

1. Criar uma variável para guardar a soma e iniciá-la com zero;
2. Repetir a leitura de um número cinco vezes;
3. Acrescentar cada número à soma;
4. Mostrar o total depois da última repetição.

#### Algoritmo

```text
algoritmo "somar_cinco_numeros"
var
   numero, soma: real
   contador: inteiro
inicio
   soma <- 0

   para contador de 1 ate 5 faca
      escreva("Digite um número: ")
      leia(numero)
      soma <- soma + numero
   fimpara

   escreva("Soma: ", soma)
fimalgoritmo
```

**Exemplo:** para os valores 2, 4, 6, 8 e 10, a soma é 30.

## 3. Conclusão

As estruturas de controle permitem representar soluções de maneira organizada. A sequência estabelece a ordem das ações, a seleção escolhe o caminho adequado e a repetição reduz tarefas repetitivas. Nos exercícios, cada estrutura foi aplicada isoladamente para facilitar a compreensão, mas elas também podem ser combinadas em algoritmos mais completos.

## Referência

FORBELLONE, André Luiz Villar; EBERSPÄCHER, Henri Frederico. *Lógica de programação: a construção de algoritmos e estruturas de dados*. Capítulo 3: Estruturas de controle.