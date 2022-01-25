# O que são listas

As listas são estruturas de dados muito utilizadas. Elas armazenam os dados em um formato de lista (dado o nome).
Basicamente, uma lista é, na verdade, um conjunto de estruturas chamadas “nós”. Um nó é uma estrutura que armazena a informação a ser gerenciada por uma lista. Na computação, existem dois tipos de lista: as listas ligadas e as listas duplamente ligadas. Cada um dos nós de uma lista ligada, além de conhecer o valor que está sendo armazenado em seu interior, também conhece o elemento posterior a ele: por isso ela é chamada de “lista ligada”, pois os nós são amarrados com essa indicação de qual é o próximo nó.

## O que são listas encadeadas(ou ligadas)

Listas encadeadas são estruturas de dados feitas de grupos de nós que juntos representam uma sequência. Você notará que a Fila e a Pilha foram criadas usando a ideia básica de uma lista encadeada. No entanto, eles têm regras especiais que os tornam diferentes em funcionalidade.

```javascript
function ListaEncadeada() {
  let contador = 0;
  let head = null;
  this.GetCount = function () {
    return countador;
  };
}
```

Nossa lista encadeada terá 6 métodos adicionais: DisplayAll (), DisplayAt (índice), AddFirst (dados), Add (dados, índice), RemoveFirst (), RemoveAt().

**DisplayAll()**:
Descrição:

- O nome já diz tudo. Retorna um array com os dados ou, se vazio, retorna nulo.

```javascript
this.DisplayAll = function () {
  // se está vazio
  if (head === null) {
    return null;
  } else {
    //senão, percorre a lista e a coloca em um array.
    let arr = new Array();
    let atual = head;
    for (let i = 0; i < contador; i++) {
      arr[i] = atual.dado;
      atual = atual.próximo;
    }
    return arr;
  }
};
```

**DisplayAt()**:
Descrição:

- Como o método PeekAt (indice) anterior da Fila, é exibido em um índice específico ou, fora dos limites, ele retorna null.

```javascript
this.DisplayAt = function (indice) {
  // verifique se há valores fora dos limites
  if (indice > -1 && indice < contador) {
    let atual = head;
    let i = 0;
    // não fui eu, é da nczonline (veja fonte).
    // É uma maneira diferente de implementar o FOR que estamos usando
    // e eu queria que todos tivessem a chance de conhecê-lo.
    while (i++ < indice) {
      atual = atual.proximo;
    }
    return atual.dado;
  } else {
    return null;
  }
};
```

**AddFirst()**:
Descrição:

- Adiciona à frente da lista. Se você está se perguntando, frente é onde o índice é 0 e referenciado pelo cabeçalho.

```javascript
this.AddFirst = function (dado) {
  // Cria um novo nó
  let node = {
    dado: dado,
    proximo: head,
  };
  head = node;
  contador++;
};
```

**Add()**:
Descrição:

- Adiciona um item à lista na posição especificada.

```javascript
this.Add = function (dado, indice) {
  // se o índice escolhido for 0, faça o método AddFirst (dado).
  if (indice === 0) {
    this.AddFirst(dado);
  }
  // verifique se há valores fora dos limites
  else if (indice > -1 && indice < contador) {
    let node = {
      dado: dado,
      proximo: null,
    };
    let anterior;
    let atual = head;
    let i = 0;
    // encontre o local certo
    while (i++ < indice) {
      anterior = atual;
      atual = atual.proximo;
    }
    anterior.proximo = node;
    node.proximo = atual;
    contador++;
  } else {
    alert('fora de alcance');
  }
};
```

**RemoveFirst()**:
Descrição:

- Remove o primeiro item.

```javascript
this.RemoveFirst = function () {
  // se não há itens na lista, retorna nulo
  if (head === null) {
    return null;
  } else {
    let out = head;
    head = head.proximo;
    if (contador > 0) {
      contador--;
    }
    return out.dado;
  }
};
```

**RemoveAt()**:
Descrição:

- Remove um item de um índice específico.

```javascript
this.RemoveAt = function (indice) {
  if (indice === 0) {
    return this.RemoveFirst(indice);
  }
  // verifique se há valores fora dos limites
  else if (indice > -1 && indice < contador) {
    let atual = head;
    let anterior;
    let i = 0;
    // encontre a localização correta
    while (i++ < indice) {
      anterior = atual;
      atual = atual.proximo;
    }
    // pule o item para remover
    anterior.proximo = atual.proximo;
    // diminuir o comprimento
    contador--;
  } else {
    return null;
  }
  // retorna o valor
  return atual.dado;
};
```

#### Fontes:

- Treinaweb, disponível em: https://www.treinaweb.com.br/blog/o-que-e-e-como-funciona-a-estrutura-de-dados-lista
- Mundojs, disponível em: https://www.mundojs.com.br/2019/11/01/estrutura-de-dados-com-javascript-lista-encadeada/
