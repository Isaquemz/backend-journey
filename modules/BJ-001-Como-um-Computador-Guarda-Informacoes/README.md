# BJ-001

🚀 Backend Journey
BJ-001 | Como um computador guarda informações

Objetivo: entender como um computador representa informações na memória e por que isso influencia diretamente a forma como escrevemos código.

Antes de começar

Quero que você faça um pequeno exercício mental.

Imagine que eu desligo seu computador.

Quando ele liga novamente, tudo o que você escreveu em TypeScript ainda está lá.

Agora imagine que você executa:

const numero = 10;

Nesse momento...

Onde está esse número?

Pense alguns segundos.

Algumas possibilidades:

No SSD?
Na memória RAM?
Dentro do Node?
Dentro do V8?
Dentro da CPU?
Em todos eles?

A maioria dos programadores nunca pensa nisso.

Mas essa pergunta é a porta de entrada para entender praticamente toda a programação.

Uma analogia

Imagine um escritório.

Ele possui quatro lugares importantes.

                 COMPUTADOR

          ┌─────────────────────┐
          │      CPU            │
          │  (quem trabalha)    │
          └─────────────────────┘
                   ▲
                   │
                   │
          ┌─────────────────────┐
          │      RAM            │
          │  (mesa de trabalho) │
          └─────────────────────┘
                   ▲
                   │
                   │
          ┌─────────────────────┐
          │      SSD            │
          │   (arquivo morto)   │
          └─────────────────────┘

Cada componente tem uma função.

SSD

É onde ficam armazenados:

Windows
Node.js
VS Code
PostgreSQL
seu projeto

Quando você salva um arquivo .ts, ele vai para o SSD.

O SSD é lento.

Mas guarda dados mesmo desligando o computador.

RAM

Agora acontece algo interessante.

Quando você executa:

npm run dev

O Node NÃO executa o código diretamente do SSD.

Ele faz algo parecido com isto:

SSD

backend-journey

↓

Node.exe

↓

carrega para RAM

Ou seja...

O programa inteiro é copiado para a memória RAM.

A RAM é milhares de vezes mais rápida que o SSD.

Mas esquece tudo quando o computador desliga.

CPU

A CPU é quem realmente trabalha.

Ela não sai procurando arquivos.

Ela recebe pequenas instruções.

Algo parecido com:

Leia esse número

↓

Some dois valores

↓

Compare

↓

Copie

↓

Guarde

Ela faz isso bilhões de vezes por segundo.

Então...

Quando você escreve:

const numero = 10;

O que acontece?

Não é instantâneo.

Existe uma sequência.

VS Code

↓

arquivo salvo no SSD

↓

Node inicia

↓

arquivo carregado para RAM

↓

V8 interpreta

↓

CPU executa

↓

valor fica armazenado na memória

Esse fluxo é extremamente importante.

Vamos aprofundar

Imagine agora:

const idade = 26;

O computador NÃO entende português.

Ele não sabe o que significa:

idade

Nem:

const

Nem:

=

Nem:

26

Isso tudo precisa ser transformado em outra linguagem.

O verdadeiro idioma do computador

No final das contas...

Tudo vira isto.

0010101010101010010

Ou melhor.

Tudo vira zeros e uns.

Chamamos isso de binário.

Mas por quê?

Porque dentro do computador existem bilhões de transistores.

Cada transistor consegue assumir apenas dois estados.

Ligado

Desligado

ou

1

0

Não existe meio ligado.

Nem 0,5.

A base de toda computação moderna é essa.

O bit

Um único 0 ou 1 recebe um nome.

Bit

Exemplo

1

é um bit.

0

também.

Pouquíssima informação cabe em um bit.

Byte

Agora juntamos oito bits.

10100110

Isso é um byte.

Um byte consegue representar até 256 combinações diferentes.

Por isso um caractere ASCII tradicional ocupa um byte.

Então o número 26 vira o quê?

Em binário.

26

↓

11010

O computador guarda isso.

Não guarda "26".

Guarda bits.

Uma curiosidade

Quando você escreve:

const numero = 26;

Você provavelmente imagina que ele ocupa apenas:

11010

Mas não.

Na maioria das arquiteturas modernas, números ocupam muito mais espaço.

Vamos entender exatamente o motivo na próxima aula.

Onde isso aparece no backend?

Muito mais do que parece.

Quando você faz:

await prisma.cliente.findMany()

Os dados:

saem do disco
vão para RAM
são convertidos
passam pelo V8
viram objetos JavaScript
ocupam memória
depois são enviados pela rede

Cada etapa tem custo.

Quando um backend começa a consumir muita RAM ou ficar lento, entender esse fluxo deixa de ser teoria e vira ferramenta de diagnóstico.

Resumo

Hoje aprendemos que:

O SSD armazena programas e arquivos permanentemente.
A RAM é a área de trabalho onde os programas executam.
A CPU executa instruções, mas não guarda programas.
O Node carrega seu código para a RAM antes de executá-lo.
O computador não entende TypeScript nem JavaScript. Antes da execução, tudo precisa ser traduzido para instruções que, no fim das contas, manipulam bits.
Um bit representa um único estado (0 ou 1).
Um byte é formado por 8 bits.
