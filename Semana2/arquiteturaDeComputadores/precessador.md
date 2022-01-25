# Como funciona um processador

O processador é um circuito eletrônico cadenciado por um relógio interno, graças a um cristal de quartzo ou a frequência da corrente elétrica que, submetido a uma corrente elétrica, emite impulsos, chamados de top. A frequência do relógio, também chamada de ciclo, correspondente ao número de impulsos por segundo, é expressa em Hertz. Assim, um computador de 200 MHz tem um relógio que envia 200 milhões de batidas por segundo. Geralmente, a frequência do relógio é um múltiplo da frequência do sistema FSB (Front-Side Bus), ou seja, um múltiplo da frequência da placa-mãe.

A cada toque do relógio, o processador executa uma ação correspondente a uma instrução, ou parte dela. O indicador chamado CPI (Ciclos Por Instrução) indica o número médio de ciclos do relógio, necessário à execução de uma instrução em um microprocessador. Assim sendo, a potência do processador pode ser caracterizada pelo número de instruções processadas por segundo. A unidade utilizada é o MIPS (Milhões de Instruções Por Segundo), correspondente à frequência do processador que divide o CPI.

## O que é uma instrução

Uma instrução é a operação mais elementar que o processador pode efetuar. As instruções são armazenadas na memória principal para serem tratadas pelo processador. Uma instrução é composta de dois campos: o código operacional, que representa a ação que o processador deve efetuar, e o código operando, que define os parâmetros da ação. O código operando depende da operação. Pode ser um dado ou um endereço da memória.

O número de bytes de uma instrução varia de acordo com o tipo de dado (a ordem de grandeza é de um a quatro Bytes. As instruções podem ser divididas em categorias, como:

- acesso à memória: acessos à memória ou transferências de dados entre registros;
- as operações aritméticas: adições, subtrações, divisões ou multiplicações;
- as operações lógicas: E, OU, NÃO, NÃO exclusivo;
- o controle: controles de sequência, conexões condicionais,
  entre outras.

#### Fonte:

- CCM, disponivel em: https://br.ccm.net/contents/400-processador
