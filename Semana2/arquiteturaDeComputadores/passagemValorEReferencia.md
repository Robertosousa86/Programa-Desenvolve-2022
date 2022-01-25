# Diferenças entre "Valor" e "Referência" em JavaScript

JavaScript é uma linguagem orientada a objetos: isso significa que a maioria das coisas em JavaScript são Objetos. Por exemplo, as funções são Objetos. Os únicos elementos que não são objetos são os Dados de Tipos Primitivos: string, number, boolean, null e undefined. Esses tipos de dados primitivos também são imutáveis, o que significa que, uma vez criados, eles não podem ser modificados.

Uma das diferenças entre os dois é que os dados de tipos primitivos são passados como valor e os objetos são passados como referência.

- Dados de Tipos Primitivos são passados como valor e Objetos são passados como referência.

O que isso significa? Você pode pensar nisso dessa maneira:

- Por Valor: Significa criar uma CÓPIA do original. Imagine gêmeos: eles nascem exatamente iguais, mas o primeiro gêmeo não tem seu cabelo modificado quando o segundo gêmeo corta o próprio.

- Por Referência: Significa criar um APELIDO (alias) para o original. Quando sua mãe te chama de "Doce de Leite", embora seu nome seja Eduardo, isso não cria um clone de você mesmo: você ainda é você, mas você pode ser chamado por esses dois nomes muito diferentes.

Vamos ver a forma como os valores primitivos e os objetos se comportam, primeiro quando atribuímos valores com o operador de atribuição (=) e segundo quando passamos para uma função como um parâmetro.

1. Atribuindo um valor com o operador = com Valores Primitivos e Objetos
   Com Valores Primitivos, o operador = funciona por valor

Considere o código abaixo:

```javascript
var name = 'Carlos';
var firstName = name;
name = 'Carla';
console.log(name); // "Carla" console.log(firstName); // "Carlos"
```

O resultado é bastante direto: é o operador = está trabalhando por valor. O que realmente acontece aqui pode ser simplificado da seguinte forma: Uma variável name é criada e recebe o valor "Carlos". Um pedaço de memória em JavaScript é alocado para ele. Uma variável firstName é criada e recebe uma cópia do valor de name. firstName tem seu próprio ponto de memória e é independente de name. Neste momento no código,firstName também tem um valor "Carlos". Em seguida, alteramos o valor de name para "Carla". Mas firstName ainda mantém seu valor original, porque ele vive em um ponto de memória diferente. Ao trabalhar com valores primitivos, o operador = cria uma cópia da variável original. Isso é o que "por valor" significa. Com objetos, o operador = funciona por referência Considere o código abaixo:

```javascript
var myName = { firstName: 'Carlos' };
var identity = myName;
myName.firstName = 'Carla';
console.log(myName.firstName); // "Carla" console.log(identity.firstName); // "Carla"
```

Aqui, o resultado é o mesmo para as variáveis que contêm objetos. Isso ocorre porque, ao lidar com objetos, o operador = funciona por referência. O que realmente acontece pode ser descrito da seguinte forma: Uma variável myName é criada e recebe o valor de um objeto que possui uma propriedade chamada firstName. firstName tem o valor de "Carlos". É alocado um pedaço em memória no JavaScript para myName e o objeto que ele contém. Uma variável identity é criada, apontando uma referência para myName. Não há espaço em memória dedicado ao valor identity. Ele apenas aponta para o valor do myName. Alteramos o valor da propriedade firstName em myName para "Carla", ao invés de "Carlos". Quando logamos myName.firstName, ele exibe o novo valor, que é esperado. Mas quando nós logamos identity.firstName, ele também exibe o novo valor de myName.firstName, "Carla". Isso acontece porque identity.firstName apenas aponta para o lugar em memória de myName.firstName. Ao trabalhar com objetos, o operador = cria um alias para o objeto original, ele não cria um novo objeto. Isso é o que "por referência" significa.

## Passando Valores Primitivos e Objetos para uma função

Dados de Tipos Primitivos são passados para uma função como valor Se você alterar o valor de um dado de tipo primitivo dentro de uma função, essa alteração não afetará a variável no escopo externo:

```javascript
var myName = 'Carlos';
function myNameIs(aName) {
  aName = 'Carla';
}
myNameIs(myName);
console.log(myName); // "Carlos"
```

Mesmo que mudando a variávelmyName dentro da função myNameIs, quando logamos, depois de chamar a função, ela ainda possui o valor "Carlos". Isso ocorre porque quando os tipos primitivos são passados, eles são passados como valor. Estamos passando uma cópia de myName: qualquer coisa que você faça para myName dentro do corpo da função não afetará myName no escopo global, porque você está passando uma cópia de myName e não a variável myName original. Objetos são passados para uma função como referência Quando você está passando algo por referência, você está passando algo que aponta para outra coisa, e não uma cópia do objeto. Portanto, como o JavaScript passa objetos por referência, quando você altera uma propriedade desse objeto dentro da função, a alteração será refletida no escopo externo:

```javascript
var myName = {};
function myNameIs(aName) {
  aName.firstName = 'Carla';
}
myNameIs(myName);
console.log(myName); // Object {firstName: "Carla"}
```

Logando a variável myName depois de ter invocado a função myNameIs, irá mostrar um objeto com uma chave firstName com um valor igual a "Carla". O objeto mudou no escopo global quando o passamos para a função. Isso ocorre porque quando você passa um objeto para a função, você não está passando uma cópia. Você está passando algo que aponta para o objeto myName. Então, quando você altera uma propriedade desse objeto na função, você está mudando a propriedade do objeto no escopo externo. Mas há uma coisa com a qual você deve prestar atenção:

```javascript
var myName = { firstName: 'Carla' };
function myNameIs(aName) {
  aName = { nickName: 'Carlita' };
}
myNameIs(myName);
console.log(myName); // Object {firstName: "Carla"}
```

Aqui logamos o valor da variável myName no escopo externo, e verificamos que não foi adicionado uma propriedade nickName ao objeto. Por quê? Se você olhar com atenção, o que estamos tentando fazer na função é reatribuir o objeto myName com um novo valor. Você não pode alterar onde myName aponta, você só pode alterar uma propriedade dentro do objeto myName, para qualquer outra coisa:

```javascript
var myName = { firstName: 'Carla' };
function myNameIs(aName) {
  aName.nickName = 'Carlita';
}
myNameIs(myName);
console.log(myName); // Object {firstName: "Carla", nickName: "Carlita"}
```

#### Fonte:

- brazilJs, disponível em: https://www.braziljs.org/p/diferencas-entre-valor-e-referencia-em-javascript