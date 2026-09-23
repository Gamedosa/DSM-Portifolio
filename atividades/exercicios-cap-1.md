---
title: Exercícios propostos - Capítulo 1
description: Resoluções passo a passo dos exercícios de introdução à lógica de programação.
---

# Exercícios propostos - Capítulo 1

Resoluções passo a passo, com foco no desenvolvimento do raciocínio lógico.

## 1. Torneio de atletismo

No torneio de atletismo, Barnabé, Gumercindo e Teodoro participaram das provas de 100 metros rasos, salto em distância e arremesso de dardo. Cada um conseguiu um primeiro, um segundo e um terceiro lugar. Descubra o que cada um conquistou, sabendo que:

1. Gumercindo venceu Barnabé no salto em distância;
2. Teodoro chegou atrás de Gumercindo no arremesso de dardo;
3. Barnabé não chegou em primeiro nos 100 metros rasos.

### Resolução passo a passo

1. Em cada prova, escreva as três posições possíveis: primeiro, segundo e terceiro.
2. No salto, coloque Gumercindo antes de Barnabé, conforme a primeira pista.
3. No dardo, coloque Gumercindo antes de Teodoro, conforme a segunda pista.
4. Lembre que cada atleta precisa terminar o torneio com um primeiro, um segundo e um terceiro lugar.
5. Barnabé não pode ser o primeiro nos 100 metros. Ao combinar essa condição com as duas anteriores, Teodoro fica em primeiro, Barnabé em segundo e Gumercindo em terceiro nos 100 metros.
6. Para completar uma colocação de cada tipo por atleta, o salto fica com Gumercindo em primeiro, Teodoro em segundo e Barnabé em terceiro.
7. As colocações restantes vão para o dardo: Barnabé em primeiro, Gumercindo em segundo e Teodoro em terceiro.
8. Confira as pistas e verifique que todas são atendidas.

### Resultado

| Prova | 1º lugar | 2º lugar | 3º lugar |
|---|---|---|---|
| 100 metros rasos | Teodoro | Barnabé | Gumercindo |
| Salto em distância | Gumercindo | Teodoro | Barnabé |
| Arremesso de dardo | Barnabé | Gumercindo | Teodoro |

## 2. O problema dos três barris

João tem três barris. No barril A, que está vazio, cabem 8 litros. No barril B cabem 5 litros e no C, 3 litros. O que ele deve fazer para deixar os barris A e B com 4 litros cada e o C vazio?

> **Premissa:** considera-se que, no início, B e C estão cheios. Assim, o estado inicial é `(A, B, C) = (0, 5, 3)`.

### Resolução passo a passo

| Passo | Ação | Estado (A, B, C) |
|---|---|---|
| 0 | Estado inicial | (0, 5, 3) |
| 1 | Despejar B em A | (5, 0, 3) |
| 2 | Despejar C em B | (5, 3, 0) |
| 3 | Encher C usando A | (2, 3, 3) |
| 4 | Completar B usando C | (2, 5, 1) |
| 5 | Despejar B em A | (7, 0, 1) |
| 6 | Despejar C em B | (7, 1, 0) |
| 7 | Encher C usando A | (4, 1, 3) |
| 8 | Despejar C em B | **(4, 4, 0)** |

### Conferência

1. Ao final do passo 8, o barril A contém 4 litros.
2. O barril B também contém 4 litros.
3. O barril C está vazio.
4. A quantidade total continua sendo 8 litros, portanto nenhuma água foi perdida ou acrescentada.

## 3. Troca de pneu furado

Elabore algoritmos que mostrem os passos necessários para trocar um pneu furado. Para cada algoritmo, faça um refinamento do anterior:

1. Trocar o pneu traseiro esquerdo;
2. Trocar o pneu traseiro esquerdo e, antes, verificar se o pneu reserva está em condições de uso;
3. Verificar se existe algum pneu furado; se houver, verificar o pneu reserva e trocar o pneu correto.

### a) Trocar o pneu traseiro esquerdo

1. Estacionar o carro em local plano e seguro.
2. Acionar o freio de mão, ligar o pisca-alerta e sinalizar o local.
3. Pegar o macaco, a chave de roda e o pneu reserva.
4. Afrouxar os parafusos do pneu traseiro esquerdo.
5. Posicionar o macaco e levantar o carro.
6. Retirar os parafusos e o pneu furado.
7. Colocar o pneu reserva e apertar levemente os parafusos.
8. Baixar o carro e terminar de apertar os parafusos em cruz.

### b) Verificar o reserva antes da troca

1. Realizar as ações de segurança do item anterior.
2. Retirar o pneu reserva e observar seu estado e sua calibragem.
3. Se o reserva não estiver em boas condições, não iniciar a troca e solicitar ajuda.
4. Se o reserva estiver em boas condições, afrouxar os parafusos do pneu traseiro esquerdo.
5. Levantar o carro, retirar o pneu furado e colocar o reserva.
6. Baixar o carro e apertar os parafusos em cruz.

### c) Localizar e trocar o pneu correto

1. Estacionar com segurança e verificar os quatro pneus.
2. Se nenhum pneu estiver furado, encerrar a verificação.
3. Se houver um pneu furado, identificar sua posição.
4. Verificar o estado e a calibragem do pneu reserva.
5. Se o reserva não puder ser usado, solicitar ajuda.
6. Se puder ser usado, afrouxar os parafusos do pneu identificado.
7. Levantar o lado correto do carro e retirar o pneu furado.
8. Colocar o reserva, baixar o carro e apertar os parafusos em cruz.

## 4. Torre de Hanói com quatro discos

Amplie a solução do problema da Torre de Hanói para completar a troca dos discos da torre A para a torre B, considerando quatro discos.

### Raciocínio

Em cada movimento, somente um disco pode ser deslocado e um disco maior nunca pode ficar sobre um menor. Com quatro discos, a solução mínima possui **15 movimentos**: primeiro são levados três discos de A para C, depois o disco 4 vai de A para B e, por fim, os três discos vão de C para B.

### Resolução passo a passo

| Movimento | Disco | Origem | Destino |
|---|---:|:---:|:---:|
| 1 | 1 | A | C |
| 2 | 2 | A | B |
| 3 | 1 | C | B |
| 4 | 3 | A | C |
| 5 | 1 | B | A |
| 6 | 2 | B | C |
| 7 | 1 | A | C |
| 8 | 4 | A | B |
| 9 | 1 | C | B |
| 10 | 2 | C | A |
| 11 | 1 | B | A |
| 12 | 3 | C | B |
| 13 | 1 | A | C |
| 14 | 2 | A | B |
| 15 | 1 | C | B |

### Conferência

1. Após o movimento 7, os três discos menores estão em C.
2. No movimento 8, o maior disco passa sozinho de A para B.
3. Os sete movimentos seguintes transferem os três discos de C para B.
4. No final, os quatro discos estão em B, do maior para o menor, e nenhuma regra foi quebrada.

## 5. Calculadora sem multiplicação e divisão

Uma calculadora comum, de quatro operações, está com as teclas de divisão e multiplicação inoperantes. Resolva as expressões usando apenas adição e subtração:

1. 12 × 4;
2. 23 × 11;
3. 10 ÷ 2;
4. 175 ÷ 7;
5. 2⁸.

> **Observação:** o enunciado original apresenta sinais corrompidos por reconhecimento de imagem. Eles foram interpretados como 23 × 11, 10 ÷ 2, 175 ÷ 7 e 2⁸.

### a) 12 × 4 usando adição

1. Começar com 12.
2. Somar mais 12: 12 + 12 = 24.
3. Somar mais 12: 24 + 12 = 36.
4. Somar mais 12: 36 + 12 = 48.
5. **Resultado: 48.**

### b) 23 × 11 usando adição

1. Somar 23 dez vezes para calcular 23 × 10: 23 + 23 + 23 + 23 + 23 + 23 + 23 + 23 + 23 + 23 = 230.
2. Somar mais um grupo de 23: 230 + 23 = 253.
3. **Resultado: 253.**

### c) 10 ÷ 2 usando subtração

1. Subtrair 2 de 10: sobra 8. Contagem: 1.
2. Subtrair 2 de 8: sobra 6. Contagem: 2.
3. Subtrair 2 de 6: sobra 4. Contagem: 3.
4. Subtrair 2 de 4: sobra 2. Contagem: 4.
5. Subtrair 2 de 2: sobra 0. Contagem: 5.
6. **Resultado: 5**, pois foram feitas cinco subtrações.

### d) 175 ÷ 7 usando subtração

1. Subtrair 7 repetidamente e contar quantas subtrações são feitas.
2. Após 10 subtrações, restam 105, pois 175 − 70 = 105.
3. Após mais 10 subtrações, restam 35, pois 105 − 70 = 35.
4. Subtrair 7 mais cinco vezes: 35 → 28 → 21 → 14 → 7 → 0.
5. Foram feitas 10 + 10 + 5 = 25 subtrações.
6. **Resultado: 25.**

### e) 2⁸ usando adição

1. Começar em 1 e dobrar o valor somando-o com ele mesmo.
2. Primeiro dobro: 1 + 1 = 2.
3. Segundo dobro: 2 + 2 = 4.
4. Terceiro dobro: 4 + 4 = 8.
5. Quarto dobro: 8 + 8 = 16.
6. Quinto dobro: 16 + 16 = 32.
7. Sexto dobro: 32 + 32 = 64.
8. Sétimo dobro: 64 + 64 = 128.
9. Oitavo dobro: 128 + 128 = 256.
10. **Resultado: 256.**