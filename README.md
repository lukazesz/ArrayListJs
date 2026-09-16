## Tutorial map, filter e reducer
Ambos são métodos muito utilizados em **JavaScript** para manipular **arrays** (listas), nos permitindo implementar uma lógica mais customizada, evitando o uso de loops mais tradicionais. Esses métodos permitem transformar, filtrar e agregar dados de maneira concisa e legível. Abaixo, exploraremos como usar cada um desses métodos e seu conceito.
### Map()
O método **map()** é usado quando queremos transformar os elementos de um **array**, aplicando uma função de callback a cada elemento e retornando um novo com os resultados. É ideal quando precisamos modificar os dados de um **array** sem alterar a lista original.

Exemplos de código com **map()**:
```js
let numeros = [1, 2, 3, 4, 5];
let quadrado = numeros.map(function(numero) {
  return numero * numero;
});
console.log(quadrado);  // saída: [1, 4, 9, 16, 25]
```
Neste exemplo, o método **map()** aplica a função chamada de **quadrado**, que calcula o quadrado de cada número, criando um novo **array** com os valores já alterados.
```js
let lista= [2, 4, 8, 10]
let atualizandoLista = lista.map(val=> val+2)
console.log(lista); // saída: [ 2, 4, 8, 10 ]
console.log(atualizandoLista); // saída: [ 4, 6, 10, 12 ]

```
Nesse segundo exemplo é criado uma  função **atualizandoLista** onde cada valor é incrementado em 2. A primeira lista permanece inalterada, enquanto a segunda lista contém os valores atualizados.
### Filter()
O método **filter()**, como o próprio nome diz, ele filtra os dados do array no **JavaScript** e cria um novo **array** contendo apenas os elementos que atendem uma condição definida em uma função de callback. Ao contrário do **map()**, o **filter()** não altera os elementos, mas seleciona aqueles que atendem ao critério definido.
Exemplos de código com **filter()**:
```js
let numeros = [1, 2, 3, 4, 5];
let pares = numeros.filter(function(numero) {
  return numero % 2 === 0;
});
console.log(pares);  // saída: [2, 4]
```
No exemplo acima foi criada a função **pares**, ela irá analisar todos os valores da lista **numeros** e filtrar apenas aqueles que forem pares ( que o resto da divisão por 2 foi igual a zero).

```js
let lista = [2, 17, 21, 5, 9];
let maiores = lista.filter((n) =>{ return n > 10});
console.log(maiores); // saída: [17, 21]
```
Neste segundo exemplo a função **maiores** usa o **filter()** para pegar apenas os valores que atendam a condição imposta.
### reduce()
O método **reduce**, sendo bem literal, reduz o tamanho do nosso **array** combinando todos os elementos em um único valor e aplicando a função **callback** a cada elemento. Ele é o ideal quando queremos executar operações aritiméticas, por exemplo multiplicar.
Exemplos de códigos com **reduce()**:
```js
let inteiros = [1, 3, 6, 8, 21, 15, 18];
let multiplicacao = inteiros.reduce((acumulador, numeros) => {return acumulador * numeros}, 1);
console.log(multiplicacao); // saída: 816480
```
O exemplo acima usa o **reduce()** na função **multiplicacao** para adicionar cada número ao acumulador durante as iterações. 
```js
let produtos = [
  { nome: "Notebook", preco: 3000, quantidade: 2 },
  { nome: "Mouse", preco: 100, quantidade: 5 },
  { nome: "Teclado", preco: 200, quantidade: 3 }
];

let valorTotal = produtos.reduce((acumulador, produto) => {
  return acumulador + (produto.preco * produto.quantidade);
}, 0);

console.log(valorTotal); // saída: 7100
```
No exemplo temos uma lista (**array**) de produtos (**objetos**), usamos a função **valorTotal** para pegar a soma total dos valores de todos os produtos da lista. 
### Dicas para quem está começando a aprender a como utilizar esses métodos:
* Use  o **map()** quando quiser criar um novo **array** com os dados transformados sem alterar o original.
* Experimente o **filter()** quando quiser pegar dados específicos de um **array** a partir das condições que você definir.
* Use o **reduce()** para calcular totais ou fazer operações agregadas, como somar valores em um array.
* Por fim, entenda que esses métodos são imutáveis, ou seja, eles não alteram o array original, mas retornam um novo array ou valor.
