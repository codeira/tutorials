---
layout: page
title: Introdução ao JavaScript
---

## O que é o JavaScript?

**JavaScript** é a linguagem que permite a interação de quem acessa a página web, controlando o conteúdo do navegador, e alterando o documento exibido. 

Alguns usos comuns na web

#### [Lightboxes](http://lokeshdhakar.com/projects/lightbox2/#example)

![](assets/images/lightbox.png)

#### [Data visualisations](http://www.nytimes.com/interactive/2013/04/08/business/global/asia-map.html?_r=0)
![](assets/images/data_visualisations.png)

#### Muitas outras coisas legais!

[The interactive ear](http://www.amplifon.co.uk/interactive-ear/index.html)
![](assets/images/interactive_ear.png)

[Stack of cards](http://designlovr.com/examples/dynamic_stack_of_index_cards/)
![](assets/images/effects_1.png)

[Games](http://gorillas.heroku.com)
![](assets/images/game.png)

Também se tornou comum o uso fora do navegador. Você pode escrever seus próprios programas e servidores em Javascript usando [Node.js](http://nodejs.org/).



### Hoje nós vamos nos focar em entender o básico

## Mas antes de iniciar...

### Arquivos necessários

Baixe os arquivos para começar a trabalhar o tutorial [aqui](https://gist.github.com/despo/0b674ec9d5ae9cb09704/download)

## Vamos testar algum JavaScript!

Nós vamos começar retirando um pouco de conteúdo do console inspetor do navegador.
Para acompanhar o que estamos fazendo, você deve escrever o código em `script.js`.

Primeiro abra sua página HTML e o **inspetor**.

> Nós iremos atualizar o navegador constantemente para visualizar suas modificações! O **JavaScript** carrega quando a página abre, então é essencial atualizar o navegador!

Vamos escrever um pouco no console, para ter certeza que seu arquivo está no lugar certo e funcionando! 

```js
console.log("Ola! Essa é minha primeira linha de código do JavaScript!");
```

Aqui acontencem algumas coisas. Por enquanto o que você precisa saber é que `console.log` é uma *função* que te permite imprimir alguma coisa no console. O que está entre parênteses é o que será impresso. 

##Variáveis e Expressões

### O que são as variáveis?

Variáveis são objetos que têm conteúdo. Elas são declaradas usando `var` e podem receber valores atribuídos. 

### O que são expressões?

Expressões são conjuntos de variáveis, operações e expressões que são processadas juntas.


#### Vamos tentar entender variáveis escrevendo algumas expresssões simples

Existem alguns tipos diferentes de variáveis que podemos declarar:

Tente todas elas! 
 
- **strings (texto)** - cadeia de caracteres, deve estar sempre entre vírgulas

```js
var name = "Codebar";

console.log(name + " é demais!"); // isso é uma expressão
```

> Você vê a mudança no seu console? Tente mudar o valor do `nome`

O operador `+` adiciona as coisas. Para as strings, isso significa que estamos *concatenando* os itens. Se alguma coisa que não for  texto for adicionada à string, o Javascript tentará transformá-la em texto primeiramente.

- **números**

Vamos trazer os valores de pi:

```js
var pi = 3.14;

console.log("O valor de: " + pi);
```

No caso acima, um número está sendo adicionado ao texto. O Javascript transforma o número em texto, e então adiciona as duas strings. 
Agora vamos tentar imprimir o ano presente, e calcular automaticamente o próximo ano usando a **adição**

```js
var year = 2015;
var nextYear = year + 1;

console.log("Nós estamos em " + year + ", mas " + nextYear + " já tá ali na esquina!");
```

Ótimo! Nós usamos texto e adicionamos números.

> Algumas vezes você terá que usar `;` depois de uma declaração. Normalmente não temos problemas, mas algumas vezes coisas estranhas podem acontecer. Tente não usar `;`.

- **booleans** - true/false (verdade/falso)

```js
var faltaAgua = true;
var numTemAgua = false;

console.log("Falta água em São Paulo? " + faltaAgua);
console.log("Tem água para esbanjar em São Paulo? " + numtemAgua);
```

- **variáveis indefinidas**
Se não tivermos valores definidos para variáveis, elas não terão tipos até serem definidas.

```js
var euNaoTenhoValor;

console.log("Que tipo de variável eu sou? " + euNaoTenhoValor);
```
> Convencionalmente no Javascript é usamos `minusculaCamelCase` para nomear variáveis.

### Operações
Existem um número variado de operações que você pode utilizar, assim como na matemática.

Vamos fazer as operações de cada seção

```js
console.log("Operações");
```

#### adição  `+`

```js
var x = 6;
var y = 3;
var addition = x + y;

console.log("Adição: x + y = " + addition);
```

#### subtração `-`

```js
var subtraction = x - y;

console.log("Subtração: x - y = " + subtraction);
```

#### Multiplicação `*`

```js
var multiplication = x * y;

console.log("Multiplicação: x * y = " + multiplication);
```

#### Divisão `/`

```js
var division = x / y;

console.log("Divisão: x / y = " + division);
```

### A condicional if
No JavaScript nós podemos escrever condicionais para controlar o resultado

Vamos tentar isso

```
if (faltaAgua) {
  console.log("São Paulo não tem água!");
}
```

Ahazou! :)

Também podemos escrever o oposto, então, falso

```js
if (!faltaAgua) {
  console.log("São Paulo tem água :(!");
}
```

> Isso não deve resultar em nada. Tente configurar `faltaAgua` para false antes de rodar essa expressão. 

> Você usou `var`? Sendo que já declaramos nossas variáveis, você não deveria precisar fazer isso.


A condição `if` tentará transformar tudo entre parênteses em `true` (verdade) ou `false` (falso). É muito comum deixar isso acontecer, então quando você encontrar algum Javascript selvagem, prepare-se! As seguintes coisas se tornarão `false` quando usadas com a condição `if`:

 - `false`
 - `0`
 - `"" // (texto vazio)`
 - `null`
 - `undefined`
 - `NaN`

Não se preocupe com tudo isso ainda. Se tornará mais claro com o tempo. 

Condições funcionam com um número dedeclarações processadas. Algumas das comparações que podemos usar são:

#### Idêntico `===`

```js
var banana = "banana";
var laranja = "laranja";

if (bananas === laranjas) {
  console.log("banana e laranja são a mesma coisa!");
}
```

Existe também uma igualdade simples chamada somente de 'igual' que é `==`. Desenvolvedores de JavaScript tentam evitar isso, porque às vezes isso causa um comportamento estranho. Pergunte mais informações a pessoa que te está te orientando, mas também lembre-se de evitar `==`.

Isso não deverá resultar em nada, pois **banana** e **laranja** não é a mesma coisa!

#### Diferente de idêntico `!==`

```js
if (banana !== laranja) {
  console.log("banana não é laranja!");
}
```

Como com `===`, existe uma versão de desigualdade simples chamada somente de 'diferente de igual'. Também se comporta estranhamente e deve ser evitado.

#### Maior que `>`

```js
var tutores = 20;
var participantes = 24;
var pizzas = 25;

var pessoas = tutores + participantes;

if (pessoas > pizzas) {
  console.log("Temos mais pessoas que pizzas!");
}

if (participantes > pizzas) {
  console.log("Temos mais participantes que pizzas! Não vamos dar comida para mais ninguém.");
}
```

#### Menos que `<`

```js
if (tutores < participantes) {
  console.log("Temos menos tutores que participantes.");
}
```

### condicionais if-else (se-o que mais)

Uma condicional **if-else** nos possibilita alternativas de ações quando sua condição não é verdadeira

```js
if (pessoas > pizzas) {
  console.log("Temos mais pessoas que pizzas. Isso não é muito bom :/");
} else {
  console.log("Temos muito pizza meeesmo. Isso nunca é ruim! :)");
}
```

> Tente mudar os números. O que acontece quando configuramos participantes para `2`. Você vê a parte else da condição sendo processada?

## Funções

Funções são a parte mais importante da linguagem de programação. Elas nos dão a possibilidade de criar trechos de código significativos que podem rodar mais de uma vez sem ter que ser definidas novamente.

Vamos escrever uma pequena função que aparece quando alguém acessa uma página com uma mensagem.

Vamos fazer isso nos seguintes passos. Primeiro criar a função:

```js
function ola() {
 console.log("Olá!");
}
```

Se você atualizar o seu navegador, você irá reparar que nenhum resultado aparece. Isso é porque você tem que chamar a função para rodar e nos dar um resultado.

```js
ola();
```

Agora vamos estender o conhecimento sobre as funções para entrar em **argumentos**. Nós queremos dizer ola para pessoas diferentes.

```js
function ola(nome) {
 console.log("Olá " + nome + "!");
}
```

Argumentos são uma lista de variáveis que serão dadas quando a função é chamada. Pense sobre eles como marcadores de lugar. 

Se você roda `ola();` você perceberá que será mostrado "Olá indefinido".

>  Por que isso acontece?  O que você sabe? Cheque as **variáveis indefinidas** se você não se lembrar

Então, vamos chamar a função com o nosso nome.

```js
ola("Amigues");
```

> Chama a função com o seu nome e com o nome da pessoa que está te orientando. O que você como resultado?

Vamos escrever uma versão aprimorada disso que mostra uma caixa de diálogo com a mensagem.

> Nós vamos te fornecer só parte dessa função, tente fazer isso funcionar. 

```js
function popupOla(nome) {
  alert("Ola " + nome);
}
```

Agora que você solucionou o problema, chame a função no console do seu navegador!

> Não adicione a chamada para a função no seu `script.js`(Isso pode ser chato de ver toda a vez que você atualizar seu navegador!)

### Múltiplos argumentos

Até agora nós tentamos funções com nenhum argumento e somente um argumento. Mas nós podemos fazer mais! Vamos tentar escrever a função com múltiplos argumentos. 

```js
function oqueEstouFazendoHoje (tutora, lugar) {
 console.log("Hoje, eu estou " + lugar + " e aprendendo um pouco de JavaScript com a ajuda da " + tutora);
}
```


### Retornando valores

Além de imprimir, que é legal quando estamos aprendendo porque nos ajuda a ver os resultados, nós podemos também `retornar`valores.

Crie uma função que adiciona dois números juntos

```js
function adicioneNumeros(x, y) {
  x + y;
}
```
> Tente rodar isso. Não é o que você esperava?

Para consertar isso, nós devemos explicitadamente usar `return` (voltar) quando nós queremos que a função nos devolva o resultado
Modifique a função para

```js
return x + y;
```

> Qualquer coisa após return será ignorada. O que acontece se você adicionar algum conteúdo antes do final da sua função mas depois de definir `return`?

Você pode preencher um argumento com a chamada de outra função. É comum ver isso, mas melhor atribuir o valor para a variável antes. O que você espera conseguir quando rodar `adicioneNumeros(adicioneNumeros(1,2), 4);`? Tente.

### Objetivo 

Quando declaramos uma variável dentro da função, elas não são visíveis fora dela.

```js
function subtrairNumeros(x,y) {
  var resultado = x - y;
}

subtrairNumeros(10,3);
console.log(resultado);
```

mas, quando nós declaramos elas fora da função, elas são

```js
var resultado;

function subtrairNumeros(x,y) {
  resultado = x - y;
}

subtractNumbers(10,3);
console.log(result);
```

No segundo exemplo, `resultado` não pertence a `subtrairNumeros`, mas pode ser visto e modificado. No primeiro exemplo, `resultado` é definido apenas dentro da função `subtrairNumeros`. O erro que o primeiro exemplo acima faz é nos dizer informações desnecessárias.

Tem uma outra possibilidade:

```js
var resultado;

function subtrairNumeros(x,y) {
  var resultado = x - y;
}

subtrairNumeros(10,3);
console.log(result);
```

Note que a variável `resultado` tem uma `var` tanto dentro e fora da função. Isso significa que elas são na verdade *duas variáveis diferentes*. Isso é chamado *shadowing* (obscurecer em tradução livre). Como pode ser confuso, tente não fazer isso. 

## Bonus
Agora que você sabe o suficiente para escrever o seu próprio pequeno programa de **JavaScript**!

Com a ajuda da pessoa que está te orientando tente e escreva um programa para fazer o seguinte:

- Guardar o seu nome numa variável

- Guardar informação sobre você em uma variável

- Guardar quantas aulas de programação você participou

- Rode o resultado do programa
  ```
  Ola! Meu nome é _nome_.
  Algumas coisas sobre mim _sobre você_.
  Eu já participei de _números de aulas_ aulas de programação!
  ```

- Se o número de aulas que você participou é 0
  ```
  Essa é a primeira vez que estou fazendo uma aula de programação!
  ```
- Se o número de aulas que você participou é maior que 0
  ```
  Essa não é minha primeira aula aqui. Eu <3 códigos!
  ```

---
Assim terminamos a aula de *Introdução ao JavaScript*. Tem algo que você não entendeu? Tente passar pelo material fornecido com seu orientador. Se você tiver alguma sugestão ou pode pensar em outras formas de melhorar este tutorial [nos envie um email](mailto:feedback@codebar.io).
