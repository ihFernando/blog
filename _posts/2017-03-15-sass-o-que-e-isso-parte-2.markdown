---
layout: post
title: “Sass? O que é isso? - Parte 2”
date: 2017-03-18 16:00:23 -0300
Excerpt: Olá, caro coleguinha que está lendo, hoje falar sobre como instalar o Sass no Windows e dar continuidade aos tópicos, com uma exploração maior, iniciados no post passado. Você pode acessá-lo clicando aqui > [ Sass? O que é isso? ] (https://ihfernando.github.io/blog/sass-o-que-e-isso)
categories: Front-End
permalink: sass-o-que-e-isso-parte-2
---
No último post sobre Sass, eu iniciei mostrando como fazer a instalação do mesmo no Ubuntu. Hoje vou mostrar como efetuar essa instalação no Windows e como trabalhar em cima dela. Também mostrarei algumas coisas sobre variáveis e cálculos, que podem ser feitos usando as 4 operações.

## Instalação
Antes de instalar o Sass, você precisa ter o **Ruby** e o seu terminal já na sua máquina, isso pode ser resolvido facilmente clicando no link a seguir [Download Ruby](https://rubyinstaller.org/downloads/). Após baixado e instalado, abra o terminal do Ruby que localizado na própria pasta do Ruby com nome de **“Prompt with Ruby”**. Com ele aberto, vamos instalar o Sass digitando os seguintes comandos:

	$ gem install sass

Ele irá baixar todos os pacotes do Sass e concluir a instalação. Após a mensagem de confirmação, verifique se está tudo bem e qual a versão atual, utilizando **sass-v**. Agora, vamos dar início ao arquivo Sass. 

Crie uma pasta seguindo a mesma lógica do post passado, em que mostro a hierarquia de pastas criadas:

	  Sass
	  ‘-- Css
	  ‘-- Sass

Com as pastas criadas, navegue pelo terminal até ela, utilizando os comandos padrões, sendo eles:

    cd.. -> volta uma pasta
    cd + nome_pasta -> entra na pasta escolhida

Depois de certificar que está no lugar certo, vamos abrir o nosso editor de código e criar o primeiro arquivo. Se tudo ocorreu certo até aqui, você já deve conseguir escrever o seu código em Sass. 
Vamos fazer um teste, digite o seguinte código no seu editor e depois salve esse arquivo na pasta Sass com a extensão **.scss**, siga o modelo:

    $cor1 : #333 ;
    $cor2 : #fff ;

    body {
        background: $cor1 ; 
        color: $cor2 ;
    }
	
*Obs.: Para entender o que vamos fazer abaixo, eu aconselho que dê uma lida no post anterior sobre Sass, leva poucos minutinhos, [clique aqui]( https://ihfernando.github.io/blog/sass-o-que-e-isso)*

Depois, com o terminal aberto, digite:
    
    sass --watch sass/estilo.scss:css/estilo.css

Ele irá gerar um arquivo chamado **estilo.css** na pasta **Css**. Se nada de errado aparecer nesta etapa, significa que estamos indo bem. xD

## Operações no Sass

É possível trabalhar com cálculos dentro do arquivo Sass, vamos ver alguns exemplos e brincar um pouco com isso. Abra o arquivo que acabamos de criar e vamos começar.

<img src="http://i.imgur.com/3FKZXFE.png" alt="Exemplo de códigos no Sass" />

E o resultado deve ser:
 
<img src="http://i.imgur.com/7OXvY3h.png" alt="Resultado do código digitado acima" />
 
Observe que nós podemos usar valores de outras variáveis ou valores locais.
Podemos criar cálculos para diversos tipos de situações, como por exemplo o **for** do post passado. Essa é uma poderosa função do Sass que pode agilizar muito o seu desenvolvimento, explore-a o quanto quiser.

## Mixins

Um outro tema interessante do Sass é o Mixins, podemos criar blocos de códigos que serão reutilizados facilmente. A maioria das pessoas que trabalha com **Web Design**, passa por aquele momento chato, no qual temos que declarar as cores e efeitos para um **link**, utilizando o **hover**, **visited** etc. Com o Mixin isso fica bem mais fácil de fazer.

Crie um Mixin como o exemplo abaixo:

<img src="http://i.imgur.com/sddcFr2.png" alt="Criando um mixin" />

Chame ele na tag **a**, declarando cada cor seguindo as variáveis $normal, $hover e $visited:

<img src="http://i.imgur.com/awkDzmX.png" alt="Incluindo o mixin criado" />

O resultado deve ser igual este: 
 
<img src="http://i.imgur.com/uUGIKkv.png" alt="Resultado da utilização do mixin" />

Você também pode fazer variações com **Box-shadow**, como por exemplo:
    
    @mixin border-radius ($radius) {
      -webkit-border-radius: $radius;
      -moz-border-radius: $radius;
      -ms-border-radius: $radius;
      -o-border-radius: $radius;
      border-radius: $radius;
    }
    
E adicionar esse Mixin na classe desta forma, em que o **10px** refere-se ao valor que será aplicado à variável **$radius**:
  
  .box-full {
    @include border-radius(10px);
  }

O resultado fica:
  .box-full {
    -webkit-border-radius: 10px;
    -moz-border-radius: 10px;
    -ms-border-radius: 10px;
    -o-border-radius: 10px;
    border-radius: 10px; }

Você pode optar por criar folhas de estilos separadas para cada situação, pode criar uma apenas para os mixins e variáveis, e outra para importar essa folha e adicionar os valores ao código. Além de manter mais organizado, você consegue ter um controle maior do que está fazendo e onde cada item está, sem ter que ficar caçando pelo código todo.

Para importar uma folha de estilo no Sass, adicionamos ao topo do arquivo o seguinte código:
    
    @import "mixins-variaveis.scss";

## Conclusão

Note que o Sass tem muitas funcionalidades interessantes para auxiliar o desenvolvedor, eu sou totalmente a favor de utilizá-lo em um projeto, entretanto, é importante saber o tamanho do que está sendo desenvolvendo e se ele não acabará trazendo mais complicações do que facilidade.

Arquivo usado no post: [ArquivoSass]( http://codepen.io/ihFernando/pen/KWZwEK)

Até a próxima!

## Links úteis

* Ruby - https://www.ruby-lang.org/pt/
* Sass - http://sass-lang.com/
* Vídeo aula - https://youtu.be/D9OpSGViDgA?list=PL3C05B7A66AC502CF
* Introdução ao Sass - http://websocialdev.com/2013/11/05/introducao-ao-sass/
