---
title: Exercícios propostos - Capítulo 2
description: Resoluções passo a passo dos exercícios sobre entrada, processamento e saída de dados.
---

# Exercícios propostos - Capítulo 2

Resoluções passo a passo, com foco nos conceitos de entrada, processamento e saída de dados.

## 1. Análise de um trecho de algoritmo

Utilizando o seguinte trecho de algoritmo, explique o que está acontecendo em cada linha e qual é o resultado de cada ação executada.

```text
inteiro: X, Y;
real: Z;
leia(X);
escreva(X, "elevado ao cubo =", pot(X, 3));
leia(Y);
escreva(X + Y);
Z ← X / Y;
escreva(Z);
Z ← Z + 1;
X ← (Y + X) mod 2;
escreva(X);
```

### Explicação linha por linha

| Linha | O que acontece | Resultado da ação |
|---|---|---|
| `inteiro: X, Y;` | Declara duas variáveis chamadas X e Y. | X e Y poderão armazenar números inteiros. |
| `real: Z;` | Declara uma variável chamada Z. | Z poderá armazenar números com casas decimais. |
| `leia(X);` | Solicita um valor ao usuário. | O número digitado fica armazenado em X. |
| `escreva(X, "elevado ao cubo =", pot(X, 3));` | Calcula X elevado à terceira potência e mostra o resultado. | É exibido o valor de X³. O valor armazenado em X não muda. |
| `leia(Y);` | Solicita outro valor ao usuário. | O número digitado fica armazenado em Y. |
| `escreva(X + Y);` | Soma os valores armazenados em X e Y. | A soma é exibida, mas não é guardada em outra variável. |
| `Z ← X / Y;` | Divide X por Y e guarda o resultado em Z. | Z recebe o quociente da divisão. Y deve ser diferente de zero. |
| `escreva(Z);` | Mostra o conteúdo atual de Z. | É exibido o resultado da divisão de X por Y. |
| `Z ← Z + 1;` | Soma 1 ao valor atual de Z. | Z passa a guardar o resultado da divisão acrescido de 1. |
| `X ← (Y + X) mod 2;` | Soma Y e X e calcula o resto da divisão dessa soma por 2. | X recebe 0 quando a soma é par e 1 quando a soma é ímpar. |
| `escreva(X);` | Mostra o novo conteúdo de X. | É exibido 0 ou 1, conforme a paridade da soma. |

### Resultado geral

Não existe um único resultado numérico, pois o algoritmo depende dos valores digitados para X e Y. Em termos gerais:

1. O primeiro resultado exibido é `X³`.
2. O segundo resultado exibido é `X + Y`.
3. O terceiro resultado exibido é `X / Y`.
4. O último resultado exibido é `(X + Y) mod 2`.
5. O novo valor de Z, depois da soma de 1, não é exibido.

### Exemplo com X = 5 e Y = 2

1. X recebe 5.
2. O cubo de X é calculado: 5 × 5 × 5 = 125.
3. É exibido: `5 elevado ao cubo = 125`.
4. Y recebe 2.
5. A soma é calculada: 5 + 2 = 7.
6. É exibido: `7`.
7. Z recebe o resultado de 5 ÷ 2, portanto Z = 2,5.
8. É exibido: `2,5`.
9. Z recebe Z + 1, portanto passa de 2,5 para 3,5.
10. X recebe o resto de 7 ÷ 2, portanto X = 1.
11. É exibido: `1`.

## 2. Entrada, processamento e saída no dia a dia

Cite e discorra sobre três exemplos do dia a dia nos quais estão presentes entrada, processamento e saída.

### Exemplo 1: caixa eletrônico

1. **Entrada:** o usuário insere o cartão, digita a senha, escolhe a opção de saque e informa o valor.
2. **Processamento:** o sistema verifica a senha, consulta o saldo e confere se o caixa possui dinheiro suficiente.
3. **Saída:** se tudo estiver correto, o caixa entrega as notas, mostra uma mensagem de confirmação e atualiza o saldo.

### Exemplo 2: aplicativo de navegação

1. **Entrada:** o usuário informa o destino e o celular obtém a localização atual pelo GPS.
2. **Processamento:** o aplicativo analisa as ruas, as distâncias, o trânsito e as rotas disponíveis.
3. **Saída:** o aplicativo apresenta a melhor rota, o tempo estimado e as instruções do caminho.

### Exemplo 3: máquina de lavar roupas

1. **Entrada:** a pessoa coloca as roupas, adiciona os produtos e escolhe o programa de lavagem.
2. **Processamento:** a máquina controla a entrada de água, os movimentos do cesto, o enxágue e a centrifugação conforme o programa escolhido.
3. **Saída:** ao final, as roupas estão lavadas e a máquina emite um aviso de conclusão.

## 3. Analogias de entrada, processamento e saída

Faça uma analogia de entrada, processamento e saída de dados com o que acontece quando você lê e sintetiza um livro e quando dialoga com outra pessoa.

### a) Ler e sintetizar um livro

1. **Entrada:** as palavras, ideias, exemplos e informações do livro são recebidos por meio da leitura.
2. **Processamento:** o leitor interpreta o texto, relaciona as ideias, identifica os pontos principais e separa o conteúdo essencial dos detalhes.
3. **Saída:** o leitor produz uma síntese com as ideias principais escritas de maneira mais curta e organizada.

Nesse caso, o livro fornece os dados de entrada, o raciocínio do leitor realiza o processamento e a síntese é o resultado produzido.

### b) Dialogar com outra pessoa

1. **Entrada:** a pessoa recebe as palavras, o tom de voz, as expressões e os gestos de quem está falando.
2. **Processamento:** ela interpreta a mensagem, considera o contexto e organiza mentalmente uma resposta.
3. **Saída:** ela responde por meio da fala, de gestos ou de outra forma de comunicação.

O processo se repete durante toda a conversa, pois a saída de uma pessoa se transforma na entrada da outra.