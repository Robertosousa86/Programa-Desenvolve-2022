# Sobre memória cache

A memória cache é uma técnica muito importante para otimizar o funcionamento do processador e é cada vez mais explorada atualmente. Mesmo assim, essa não é uma ideia limitada aos componentes do processador mas é usada em quase todas as comunicações de dados atualmente.

Alguns lugares muito comuns são em navegadores, banco de dados e servidores.

## Cache em navegadores

Quando você acessa páginas em um navegador, como Chrome ou Firefox, você precisa se comunicar com servidores pela internet e esperar todo o conteúdo da página ser transferido para seu computador. Como as páginas não costumam ser alteradas com frequência, os navegadores costumam guardar esses dados dentro do próprio computador. Dessa forma, a próxima vez que você acessar ela, será muito mais rápido.

Esse tipo de armazenamento local de dados de servidores também é usado em outros aplicativos, além de navegadores, como o Facebook.

## Cache em bancos de dados

Alguns sistemas usam estruturas chamadas de bancos de dados. Elas são formas de guardar e estruturar uma grande quantidade de informação no HD/SSD. Porém, algumas pesquisas nessa estrutura podem não ser tão rápidas e seria interessante guardar valores muito pedidos para acelerar as respostas.

Por isso, muitos bancos de dados utilizam uma estrutura de dados rápida (muitas vezes em memória RAM) para guardar essas respostas, como o Memcached e o Redis. Você pode encontrar cursos aqui na Alura sobre Redis.

## Cache em servidores

Muitas vezes, alguns serviços de um servidor podem ser bem mais requisitados que outros. Por exemplo, uma página inicial de um site de computadores que mostra todos os produtos em desconto naquele dia. Dessa forma, para acelerar a resposta e diminuir a carga nas máquinas, esses equipamentos podem guardar versões prontas dessas páginas durante um período de tempo. Assim, sempre que uma pessoa pedir a página para o servidor, ele não precisará buscar no banco de dados nem fazer um processamento complexo para devolver a resposta.

Esse processo é normalmente feito em conjunto com uma Content Delivery Network (CDN) ou Rede de Distribuição de conteúdo. Elas basicamente distribuem cópias das suas mídias para diversos servidores para que o dado esteja o mais próximo possível de você. Essa é a técnica vital para o funcionamento da Netflix. Você pode ver mais sobre como elas funcionam no vídeo do Código Fonte TV.
