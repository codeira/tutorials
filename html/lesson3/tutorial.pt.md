---
layout: page
title: HTML Aula 3
footer: true
---

##  HTML e CSS - Além do básico

### Recaptulando

Nas duas aulas anteriores nós falamos sobre **H**yper **T**ext **M**arkup **L**anguage e **C**ascading **S**tle **S**heets. **HTML** define a _estrutura_ de um site e o **CSS** sua _apresentação_.

### Hoje vamos criar do início um site com estilos aplicados

A página que vamos criar se parecerá com esta [página de exemplo](http://codebar.github.io/tutorials/html/lesson3/example.pt.html "Ada Lovelace").

Nós também vamos explicar em mais detalhes elementos que mencionamos em nossas aulas anteriores.

## Mas antes de começarmos...

### Arquivos necessários

Baixe [aqui](https://gist.github.com/despo/7328342/download) os arquivos necessário para começar a trabalhar com este tutorial

### Ferramentas de desenvolvimento - inspetores

Inspetores são ferramentas de desenvolvimento que auxiliar a visualização, edição e _debug_ (correção de bugs) de CSS, HTML e JavaScript.

Um inspetor muito popular é o [firebug](http://getfirebug.com/), funciona muito bem com o Firefox. Chrome tem um inspetor embutido, mas recomendamos a utilização do firebug por ser mais fácil de utilizar e com ele alterar diferentes propriedades.

![](assets/images/firebug.png)

> Peça ao seu orientador para mostrar como se edita estilos na nossa página de exemplo utilizando o firebug

## Começando

Vamos começar do cabeçalho da nossa página e definir o título como aprendemos em nossa primeira aula.

```html
<title>Ada Lovelace</title>
```

### Estruturando conteúdo

Nós vamos separar nossa página em três diferentes áreas. O **header** (cabeçalho) ficará no topo da nossa página, exibindo título e imagem. O **container** (encapsulador de conteúdo) será onde vamos inserir o conteúdo principal e o **footer**, nosso rodapé.

```html
<header>

</header>
<div>

</div>
<footer>

</footer>
```

> Você se lembrou de inserir as tags dentro das tags `<body>` da sua página?

> Inspecione a página. Você pode ver o título e os elementos que acabamos de inserir?

## Elementos _inline_ (em linha) vs _block_ (bloco)

No CSS existem diferentes modos de [exibir](https://developer.mozilla.org/pt-BR/docs/Web/CSS/display) elementos. Os mais comuns são: _block_, e _inline_

### elementos _block_

Elementos aparecem em uma nova linha

![](assets/images/span-block.png)

Alguns elementos _block_ são: `<div>, <p>, <h1>, <ul>, <li>`. A maioria dos elementos são elementos _block_.

### elementos _inline_

Elementos aparecem na mesma linha

![](assets/images/span-inline.png)

Alguns elementos _inline_ são `<img>, <a>, <em>, <strong>, <span>`

#### Para aprimorar elementos e alterá-los de _block_, para _inline_, ou o inverso, você pode usar a propriedade CSS `display` com os valores `inline` ou `block`

## Definindo o conteúdo do `<header>`

### Estrutura

Nós vamos desenvolver a página de cima para baixo. Você pode depois voltar e aprimorar seu código se quiser.

Adiciona uma imagem encapsulada em um elemento `<div>`

```html
<div>
  <img src="ada_lovelace.jpg"/>
</div>
```

Adicione o texto de cabeçalho `<h1>` abaixo do elemento `<div>` que está encapsulando a imagem, dentro do elemento `<header>`

```html
<div>
  <h1>Olá, eu sou Ada Lovelace</h1>
</div>
```

> Carregue a página. Dê uma olhada em como os elementos estão exibidos utilizando o inspetor

### Apresentação

Vamos utilizar o que nós aprendemos e fazer a imagem como um elemento _inline_.

Antes de manipular a `<div>` que contém a imagem, você deve ser capaz de acessá-la do CSS. Defina a classe `my-picture` neste elemento.

```html
<div class="my-picture">
  <img src="ada_lovelace.jpg"/>
</div>
```

Adicione o estilo em questão em `style.css`

```css
.my-picture {
 display: inline;
}
```

> Dê uma olhada na página. Inspecione a imagem e observe suas propriedades CSS

#### Fazendo funcionar

Faça um elemento `div` encapsulando o texto de cabeçalho em linha. Comece adicionando a classe `title` à ele

```html
<div class="title">
 <h1>Olá, eu sou Ada Lovelace</h1>
</div>
```
e o CSS em questão

```css
.title {
  display: inline-block;
}
```

`inline-block` é outro atributo da propriedade `display`. Você deve utilizar `inline-block` ao invés de `inline` para fazer o elemento aparecer em linha porque o elemento `div` com a classe `title` contém um elemento `block`, `<h1>`, que assume a linha e expande até seu fim.

> Utilizando o firebug altere `inline-block` para `inline` e perceba como eles são exibidos

Ajuste o alinhamento de `.title`

```css
vertical-align: top;
```

faça a imagem parecer um pouco menor

```css
.my-picture img {
  height: 60px;
}
```

## Modelo de caixa

### O que é o modelo de caixa?

Um elemento pode ser visualizado como uma caixa. O modelo de caixa é um jeito de descrever o epilhamento de propriedades espaciais de um elemento, ou seja, os quem tem efeito em seu tamanho e espaçamento na página. Eles são: `padding`, `margin`, `border` assim como `height` e `width`.

**<span style="color: rgb(130,171,182);">azul</span>** representa os valores para `height` e `width`. Geralmente esses valores são definidos de forma implícita, baseado no conteúdo.

**<span style="color: rgb(185,197,124);">verde</span>** representa o valor de `padding` &mdash; o espaço dentro de `border`. `padding` complementa ao valor total de tamanho da caixa. Então ao definir `padding-left: 10px;` e `width: 10px;` o resultado é um elemento com **30px** de largura na página.

**<span style="color: rgb(244,211,139);">amarelo</span>** representa o valor de `border` &mdash; a borda ao redor do conteúdo e do `padding`. Ela pode ter estilos variados e representa a parte externa mais visível de um elemento.

**<span style="color: rgb(239,195,144);">laranja</span>** representa o valor de `margin` &mdash; a margem ao redor da borda. Isso distancia o elemento de outros elementos na página.

Note: `padding`, `margin` and `border` can be applied to any combination of sides, below all three are applied in equal measure to all four sides around the content.

![](assets/images/box-model.png)

### Styling the header

The page is gradually starting to come together. Make `<header>` a bit more distinct by setting a background color and aligning its contents in its center.

```css
header {
  background-color: #fdfdfc;
  text-align: center;
}
```

### Applying box properties to header

Expand the styling of the header so that it has a border and tweak the height and padding

```css
border-bottom: 1px solid #e7e6e6;
padding-top: 14px;
height: 70px;
```

> Do you remember the border properties description from our previous lesson?


> Tweak the width of the border and refresh your page

_border: `thickness` `style` `color`;_

## Setting up the sidebar

Along with `width` and `height`, `min-width`, `max-width`, `min-height`, and `max-height` can be set. These properties tend to be used to ensure that when the page is resized, the browser won't allow for it to be smaller or bigger than the specified property value.

Let's add some content! Add the following inside the `div` in the html file

```html
<div>
  <strong>Me on the internet</strong>
  <ul>
   <li><a href="https://www.facebook.com/augusta.ada.lovelace">facebook</a> </li>
   <li><a href="http://en.wikipedia.org/wiki/Ada_Lovelace">wikipedia</a> </li>
 </ul>
</div>
```

### Styling

Add a class `sidebar` to the div we just defined. This is so that we can change its styling without impacting other elements.

```html
<div class="sidebar">
  <strong>Me on the internet</strong>
  ...
```

Begin by adding a background color so we can clearly see the container

```css
.sidebar {
  background-color: #fdfdfd;
}
```

Restrict the width of the sidebar

```css
width: 30%;
min-width: 300px;
max-width: 320px;
```

Make it an inline-block and set some of its box properties

```css
display: inline-block;
padding: 25px 30px 20px;
border: 1px solid #e8e8ea;
margin-top: 55px;
margin-left: 20px;
```

###padding and margin
Padding and margin can be set in a number of different ways

`padding: top right bottom left;` e.g. _padding: 10px 20px 30px 5px;_

`padding: top right/left bottom;` e.g. _padding: 10px 20px 5px;_

`padding: top/bottom right/left;` e.g. _padding: 5px 15px;_

`padding: all;` e.g. _padding: 20px_

Alternatively, you can only set the side you want `padding-right: 20px`

_this also applies to the margin_

###more styling...

Specify a class `.social-media` in the `ul` element

```html
<ul class="social-media">
  <li><a href="https://www.facebook.com/augusta.ada.lovelace">facebook</a> </li>
```

Remove the list bullets and change the default margin and padding of the **u**nordered **l**ist

```css
ul.social-media {
  list-style: none;
  margin-left: 10px;
  padding-left: 20px;
}
```

Add a bottom border, to give the effect of a line, to the individual list items and tweak its dimensions

```
.social-media li {
  border-bottom: 1px solid #b0afc0;
  padding: 10px;
  width: 200px;
}
```

> Tweak the properties using the inspector
> What happens when you remove the width or increase the padding?

## Pseudo classes

A pseudo class is a keyword added to selectors that specifies a special state. Using pseudo classes we can specify different styling for different states of a link:

```css
a:link
a:visited
a:hover
a:active
```

Order is **very** important. Always use the order described above if you want to apply different styling for all of the states.
The most commonly used pseudo class for links is `a:hover`. That is what we will use today.

We talk about *pseudo* classes, because in contrast to the classes we address by
putting a dot in front of them, the *pseudo* classes have no actual
correspondent in the HTML. Instead, they refer to a certain state of the element
that is not expressed through the markup.

## Styling links

We only want links that are within the list to be affected. So we will specifically style `.social-media li a`

```css
.social-media li a {
  color: #4c4066;
  text-decoration: none;
  text-shadow: 1px 0px #ffffff;
  border-left: 7px solid #fdcc38;
  padding-left: 10px;
}
```

### Styling link on :hover state

We only want to change the border color when hovering over the link. To avoid repeating ourselves an easy way to do that is by being more specific and using `border-left-color`. Since we have no other borders, we could also use `border-color`

**Remember to have a look [at the list of all CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference?redirectlocale=en-US&redirectslug=CSS%2FCSS_Reference) (mentioned in the previous tutorial) when working on styling. The properties are too many to remember!**

```css
.social-media li a:hover {
  border-left-color: #a26cd2;
}
```

## Almost there..

The sidebar is now almost perfect. Tweak a couple of other properties so that the list description is aligned with the other elements and emphasized

```css
.sidebar b {
  margin-left: 36px;
  color: #4c4066;
  font-size: 19px;
}
```

## Before we continue, some other nice to know box properties...

Add these to the `.sidebar` CSS

```css
border-radius: 6px;
box-shadow: 0 1px 1px 1px rgba(237, 235, 232, 0.4);
```
**border-radius** creates rounded corners

**box-shadow** creates a drop shadow effect allowing us to specify color, size, blur and offset


## Setting up the main container

You've done a great job so far! The sidebar is done and you know about box properties.
Time to add some content to the page.

Add a div, with the class main after `.sidebar`

```html
<div class="main">

</div>
```

Here, we will define the text we want to display about **Ada Lovelace**, using paragraphs to make the content easier to read.

### First, a little bit about her

```html
<p>My name is August Ada King. I'm the Countess of Lovelace.</p>

<p>I am a mathematician and a writer. People know me from my work on Charles Babbage's early mechanical general-purpose computer, the Analytical engine. I wrote the first algorithm intended to be processed by a machine. In other words, I am the world's first programmer.</p>

<p>My mother, Anne Isabella Byron, was a great help to me as she helped me by promoting my interest in mathematics and logic, but I also never forgot about my dad, who moved to Greece when I was just an infant to help out in the civil war.</p>
```

Now that the content is there, we can see that again, we need to tweak the element to display as an inline block and set its width to make sure it appears next to the sidebar.

```css
.main {
  display: inline-block;
  width: 55%;
}
```

> Are the sidebar and container displayed next to each other? What happens when you tweak the width?


Add a bit more space around the main container and set the vertical alignment.

```css
margin-left: 70px;
padding-top: 60px;
vertical-align: top;
```

> Try removing `vertical-align`. What happens?

### Now, focus on the content

Add a link so that anyone coming to the page can easily find out more about Charles Babbage. In the second paragraph, wrap his name in a link as shown below.

```html
<a href="http://en.wikipedia.org/wiki/Charles_Babbage">Charles Babbage's </a>
```

Ada was the world's first programmer. We want that content to stand out. Add a span around and specify a class `highlight`, so the intention is obvious and other people working on the code of the page can easily understand it.

```html
<span class="highlight">I am the world's first programmer</span>
```

Set the style for the highlight class

```css
.highlight {
  color: #4c61a9;
}
```

### More content

```html
<blockquote>&ldquo;I do not believe that my father was such a poet as I shall be an Analyst; for with me the two go together indissolubly.&rdquo;</blockquote>

<p>Throughout my life, mathematics have been my primary interest. I always question even basic assumptions by integrating poetry, another great love of mine, and science. I also have a keen interest in scientific developments and trends of my era like phrenology and mesmerism.</p>
```

Being the first paragraph a quote, so we can use `<blockquote>`, as it's more appropriate than a p tag.

```html
<blockquote>&ldquo;I do not believe....</blockquote>
```

and then the styling

```css
blockquote {
  border: 1px solid #E7E6E6;
  padding: 20px 27px;
  border-radius: 6px;
  background-color: #FDFDFC;
  color: #4C4066;
  margin-top: 40px;
  margin-bottom: 40px;
}
```

> Tweak the properties. Explain to your coach what each property does.

A poem about Ada

```html
<p>
 Charles Babbage wrote the following poem about me
 <br/>
 <span>
   Forget this world and all its troubles and if<br/>
   possible its multitudinous Charlatans-every thing<br/>
   in short but the Enchantress of Numbers.
 </span>
</p>
```

> Why do we need a line break (`<br/>`) before the span? What happens when we remove the line break?

Make the poem look different than the rest of the text. Add a CSS class `poem` to the span element and add styling

```css
.poem {
  font-style: italic;
  color: #4C4066;
}
```

### Some more information about Ada
```html
<p>The computer language <a href="http://en.wikipedia.org/wiki/Ada_(programming_language)">Ada</a>, was named after me. The Defense Military standard for the language, MIL-STD-1815 was also given the year of my birth.</p>

<p>These days, the British Computer Society runs an annual competitions for women students of computer science in my name. Also, the annual conference for women undergraduates is named after me. Google also dedicated its <a href="http://www.google.com/doodles/ada-lovelaces-197th-birthday">Google doodle</a> to me, on the 197th anniversary of my birth. </p>

<p>
 <a href="http://www.google.com/doodles/ada-lovelaces-197th-birthday">
  <img src="http://www.google.com/logos/2012/ada_lovelaces_197th_birthday-991005-hp.jpg" />
 </a>
</p>
```

That looks great but we can tweak the position of the doodle so its aligned in the middle and there is a bit more space between it and the page.

Add the class `google-doodle` in the last paragraph and set its styling.

```css
.google-doodle {
  text-align: center;
  margin-top: 90px;
  margin-bottom: 70px;
}
```

### Styling links

Previously, we specified the styling for link elements included within the sidebar. Now we can set a default link style that will be applied to all remaining elements.

```css
a {
  color: #7a3cb7;
}

a:hover {
  color: #a26cd2;
}
```

## Setting up the footer
To complete our page, we will be adding some content and styling the footer

Within the footer, add an attribution to yourself and link to your twitter, Facebook or any other place you want to.

```html
<p>Made by <a href="...">[your name]</a></p>
```

and add the final styling touches for the footer elements

```css
footer {
  height: 60px;
  padding-top: 20px;
  padding-left: 30px;
  background-color: #1f1430;
  border-top: 1px solid #eeeeee;
  margin-top: 20px;
}

footer p {
  color: #b0afc0;
  font-size: 14px;
}

footer a {
  color: #b0afc0;
}
```

> Do you have any questions?

### Bonus - Inspector

Have a look at the [example page](http://codebar.github.io/tutorials/html/lesson3/example.html "Ada Lovelace"). The heading and body of the page have some differences from the page we just created.

Use the inspector to have a look at `<body>` and `<h1>` and apply these changes to your page.

-----

This ends our third lesson. Is there something you don't understand? Try and go through the provided resources with your coach. If you have any feedback, or can think of ways to improve this tutorial [send us an email](mailto:feedback@codebar.io) and let us know.
