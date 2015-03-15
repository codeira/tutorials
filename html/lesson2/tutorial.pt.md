---
layout: page
title: HTML Aula 2
footer: true
---

## O que é CSS?

**CSS** é a linguagem utilizada para estilizar websites.

Ela define a representação visual do conteúdo. Por exemplo cor, margens, bordas, cores de fundo, posições de elementos na página.

### O que significa?

 **C**ascading **S**tyle **S**heets. *(Folhas de estilo em cascata)*

### No que constitui um website

HTML: estrutura do website

CSS: apresentação

_**CSS** trabalha em conjunto com o **HTML**_

### Hoje nós vamos focar nos conceitos fundamentais do CSS

Nós vamos aplicar estilos a [esta página](http://github.com/codebar/tutorials/blob/gh-pages/html/lesson2/example.pt.html), para que ela se pareça [com este exemplo](http://codebar.github.io/tutorials/html/lesson2/example.pt.html).

## Mas antes de começarmos...

> O primeiro tutorial não te prepara para este exercício. Antes de continuar, faça download dos arquivos necessários. 


### Arquivos necessários

[Faça download dos arquivos necessários](https://gist.github.com/miguelpeixe/dcc111e287ce3a634569/download) para começar a trabalhar neste tutorial.

### O que eu posso fazer com CSS?

Você pode alterar cor, posição, dimensão e apresentação de diferentes elementos.

### Anatomia de um elemento CSS

```css
body {
  color: hotpink;
}
```

**body** seletor

**color** propriedade

**hotpink** valor

```css
seletor {
  propriedade: valor;
}
```

Um grupo de propriedades para um determinado seletor é definido dentro das chaves

```css
body {
  color: hotpink;
  font-size: 12px;
}
```

## Começando

No cabeçalho - *head* - da página HTML defina uma tag style (tag para escrita do CSS)

```html
<head>
  <title>Eu amo corujas</title>
  <style type="text/css">

  </style>
</head>
```

Inclua o estilo descrito abaixo dentro da tag style que definimos.

## Introdução ao seletor

### Seletores

#### Seletor: elemento

Vamos ver a fonte que gostaríamos que nossa página utilize.

```css
body {
   font-family: Helvetica, Arial, sans-serif;
}
```

Ao selecionarmos o elemento **body** a alteração de fonte será aplicada a tudo aninhado dentro dele, todo o conteúdo da nossa página.

Vamos também remover os pontos dos items das listas que definimos

```css
ul {
   list-style: none;
}
```

e alterar a aparência dos links em nossa página

```css
a {
   color: #a369d5;
   text-decoration: none;
   border-bottom: 1px dotted #a369d5;
}
```
**color**  define a cor do texto. `#a369d5` é a representação da cor em HEX *(sistema hexadecimal)*.
Uma ferramenta útil para descobrir os códigos das cores é [http://0to255.com](http://0to255.com).

**text-decoration** especifica a decoração aplicada ao texto. Algumas outras opções que você pode tentar são _underline_, _overline_ e _line-trough_. Links por padrão tem a decoração sublinhada _(underline)_ aplicada a eles, ao definir como none _(nenhuma)_, nós removemos a propriedade.

**border-bottom** faz o texto aparecer sublinhado. Propriedades de borda podem ser unificadas em uma linha só.

`border-bottom: espessura estilo-da-borda cor`

**1px** define a espessura da borda

**dotted** define o estilo da linha

**#a369d5** a cor da borda

#### Seletor: classe

Um seletor de classe seleciona todos os elementos que utilizam a classe especificada.

```css
.pictures {
   margin: 10px auto;
   width: 900px;
}
```

**margin** é a área ao redor do elemento. A definição acima é uma versão curta para

```css
margin-top: 10px; /* Superior */
margin-bottom: 10px; /* Inferior */
margin-right: auto; /* Direita */
margin-left: auto; /* Esquerda */
```

O que nós definimos acima é
_margin: (top bottom) (left right)_

> Você pode ver a margem de um elemento inspecionando-o pelo navegador e observando na aba _computed_ (valores de estilo computados)

#### Seletor: id

Selecionando um elemento com o id _logo_.

```css
#logo {
   margin: 0 auto 30px;
   width: 200px;
}
```

> Só pode haver um elemento com um id particular. Se você definir múltiplos elementos, apenas o primeiro será selecionado.

#### Seletor: elementos aninhados

Selecionando todos os elementos de lista que estão aninhados à **classe** _pictures_

```css
.pictures li {
   display: inline;
   margin: 3px;
}
```

**display** especifica como os elementos são exibidos. **li** é um elemento _block_ (bloco). Ao alterar sua propriedade _display_, nós garantimos que será exibido como um elemento _inline_ (em linha).

> Altere _inline_ para _inline-block_, e para _block_. Você pode observar a diferença?

## Formas de conectar CSS ao HTML

### CSS incorporado _(embedded)_

No início do tutorial nós descrevemos como conectar o CSS à nossa página.

```html
<head>
  <title>Eu amo corujas</title>
  <style type="text/css">

  </style>
</head>
```

Este método de utilizar CSS, definindo-o dentro da própria página HTML é chacado de **incorporado**, ou _embedded_ em inglês. O problema neste método é que ele não permite a reutilização do estilo em outras páginas e torna o trabalho mais difícil.

### CSS ligado _(linked)_

Um melhor método para definir CSS é incluí-lo como uma folha de estilos separada. É mais fácil de manter e pode ser reutilizado em várias páginas.

Para alcançar isso, vamos mover nosso CSS para fora do cabeçalho _(head)_ e para um novo arquivo que vamos ligar através do cabeçalho.

```html
<head>
  <title>Eu amo corujas</title>
  <link rel="stylesheet" type="text/css" href="style.css">
</head>
```

## Cascata

Folhas de estilo operam em cascata em todos os elementos até eles serem alterados.

Primeiro vamos remover a margem e a borda de todas as imagens.

```css
img {
  margin: 0;
  border: 0;
}
```

Nós podemos alterar o estilo de algumas dessas imagens definindo um seletor mais específico. Isso vai substituir o seletor `img` que acabamos de definir

```css
.bigimg img {
  margin: 15px 2px;
  width: 439px;
  border: 2px solid #b9b1bf;
}
```

## Propriedades do CSS

Até agora nós explicamos algum seletores e apresentamos outros com nomes mais auto explicatórios. Saber todos os seletores não é uma tarefa fácil, mas não se preocupe. A internet é sua amiga. [Aqui você você pode encontrar uma lista de todas as propriedades CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_Reference)


## Aplicando mais estilos à nossa página

### line-height _(altura da linha)_

Vamos extender o seletor do _body_ para que nossa página apareça um pouco menos encavalada.

```css
body {
  font-family: Helvetica, Arial, sans-serif;
  line-height: 1.3;
}
```

### Centralizando o conteúdo da nossa página

No HTML da página você vai notar um elemento `div` com o id **main**. Vamos utilizar este seletor para centralizar o elemento

```css
#main {
  width: 900px;
  margin: 0 auto 40px;
  padding: 0;
}
```

Para alcançar a centralização do elemento nós precisamos definir sua largura. Se você remover a propriedade de largura - _width_ - você irá notar que o elemento não estará no centro da página.

Nós também estamos utilizando uma versão curta para definir margem. A versão longa é assim

```css
margin-top: 0;
margin-bottom: 40px;
margin-right: auto;
margin-left: auto;
```

**auto** ajusta as margens direita e esquerda. Se você ajustar o tamanho da janela do browser vai observar que mas margens direita e esquerda irão se ajustar automaticamente, para que o elemento **main** se mantenha no centro da página.

**padding** é a área ao redor do elemento, mas dentro de sua borda.

> Não confunda padding (preenchimento) com margin (margem), dê uma olhada no inspetor de elemeentos par aver como o padding e margin de um elemento se diferem.


### Elementos flutuantes

```css
.right-box {
  float: right;
}
```

### Utilizando elementos vazios para aplicação de estilos

Para fazer o desenho da página ficar mais bonit às vezes podemos adicionar elementos vazios. Como `<div id="top-line"></div>`

```css
#top-line {
  width: 100%;
  height: 5px;
  background-color: #2d183d;
  border-bottom: 3px solid #eedffb;
  margin-bottom: 10px;
}
```

Vamos também aplicar estilos ao final da nossa página de forma similar

```css
#bottom-line {
  width: 100%;
  height: 5px;
  background-color: #2d183d;
  border-top: 3px solid #eedffb;
}
```

### Alterando estilo através dos seletores de elemento

Quando queremos garantir que a aparência de um elemento se altere de forma consistente através das nossas páginas, é melhor utilizar seletores de elemento. Dessa forma podemos garantir que não precisaremos redefinir o esitlo e que se aplicará a todos os elementos deste tipo.

```css
h1 {
  font-size: 39px;
  color: #2d183d;
  text-align: center;
  border-bottom: 1px solid #f6f4f8;
  border-top: 1px solid #f6f4f8;
  padding: 20px 0;
}

h2 {
  font-size: 28px;
  margin: 15px 0;
  color: #663095;
  padding: 15px 0;
  font-weight: 400;
  text-align: center;
}

h4 {
  color: #6D6A6A;
  font-size: 19px;
  padding: 27px 25px 15px;
}

small {
  color: #6D6A6A;
  font-size: 15px;
  margin: 0 30px 10px;
  text-align: right;
}

ol {
  margin: 14px 0;
}

ol li {
  background-color: #F6F4F8;
  color: #663095;
  font-size: 16px;
  font-weight: 400;
  margin: 10px 30px 10px 40px;
  padding: 6px 20px;
  border-radius: 9px;
}
```

**font-weight** espessura do texto exibido

**text-align** alinhamento horizontal de um elemento de texto

### Um pouco mais de estilo

```css
#the-quote{
  border-bottom: 1px solid #f6f4f8;
  border-top: 1px solid #f6f4f8;
  margin: 40px auto;
  width: 90%;
}

#links {
  margin: 10px 15px 0 0;
}

#links li {
  margin: 0 7px;
  font-size: 18px;
  display: inline;
}

#text-block {
  height: 370px;
}

```

### Mais seletores em cascata

```css
.pictures li img {
  border: 2px solid #b9b1bf;
}

.bigimg img {
  margin: 15px 2px;
  width: 439px;
  border: 2px solid #b9b1bf;
}
```

### Alguns toques extras

```css
.bigimg{
  display: inline;
}
```

## Material avançado

### Pseudo-classes


Pseudo-classe é uma palavra-chave adiciona a um seletor que especifica um estado especial do elemento a ser selecionado. [Essas](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) são as pseudo-classes padrões.

Vamos adicionar o código abaixo para garantir que nós vamos aplicar a margem apenas ao **primeiro elemento** da lista dentro da classe _pictures_.

```css
.pictures li:first-child {
  margin-left: 5px;
}
```

> O que acontece quando você remove _:first-child_ do seu seletor?


### Bonus - Removendo estilos

Você provavelmente notou que as páginas se parecem diferentes quando carregadas em diferentes navegadores. Para evitar as inconsistência entre navegadores uma técnica comum é a **remoção de estilo**, ou, _CSS resetting_ em inglês.

Vamos tentar aplicar aos elementos da nossa página

```css
html, body, div, h1, h2, h3, h4, h5, h6, p, a, img, small, b, i, ol, ul, li {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  vertical-align: baseline;
}
```

-----

Assim terminamos nossa segunda aula. Tem algo que você não entendeu? Tente passar pelo material fornecido com seu orientador. Se você tiver alguma sugestão ou pode pensar em outras formas de melhorar este tutorial [nos envie um email](mailto:feedback@codebar.io).
