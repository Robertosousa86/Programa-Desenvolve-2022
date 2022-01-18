# A importância da tag meta

Quando salvamos um arquivo texto no disco ele é salvo usando uma cadeia de caracteres (character set encoding). Se no editor de texto salvamos o arquivo contendo charset UTF-8, precisamos dar uma pista para o navegador de como ele deve ser processado. Se não fizermos isso, ele não conseguirá exibir corretamente qualquer texto acentuado.

Contudo, muito cuidado! Vamos supor que acidentalmente seu editor de texto não salvou o arquivo como UTF-8, mas em latin1. Se colocarmos a tag <meta charset="UTF-8"> estaremos dando uma dica errada para o navegador e isso nos trará problemas na acentuação. Para resolver esse tipo de situação, podemos usar <meta charset="latin"> ou mudar nosso arquivo para UTF-8, o que é mais difícil.

Pode ser que o editor de texto escolhido não siga o padrão UTF e utilize outro qualquer que nem eu ou você sabemos.

Mais do que os caracteres saírem certos ou errados, o importante é aprender a lógica de programação. O que estamos abordando serve para tornar sua experiência melhor e seu programa mais bonito. Afinal, quem não gosta de ver os acentos todos bonitinhos.
