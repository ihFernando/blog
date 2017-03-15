---
layout: post
title: "Sass? O que é isso?"
date: 2017-03-15 01:00:23 -0300
excerpt: O tema de hoje será sobre um assunto bem interessante no mundo do Front-End, vamos conversar um pouco sobre o Sass e suas funcionalidades.
categories: Front-End
permalink: sass-o-que-e-isso
---

Estava recentemente conversando com alguns colegas da faculdade e notei que um assunto muito importante, porém, pouco explorado, é o Sass. Algumas perguntas repetitivas acabam ficando no ar, por isso, este post tem a intenção de responder algumas delas e facilitar de uma forma bem simples e objetiva, a vida de quem quer trabalhar com essa ferramenta sensacional. Então pegue o seu café e vamos bater um papo sobre isso!

Para agilizar o processo e não ficar consumindo tempo daqueles que já tem uma noção maior sobre essa Gem, eu irei deixar o assunto separado em tópicos, chamados de:

* O que é?
* Instalação
* Criando um arquivo Sass
* Variáveis
* Funções
* Bônus e Conclusão

*Obs.: Também irei disponibilizar links de vídeos e artigos onde você pode encontrar mais informações sobre o tema.*

## O que é?

O Sass é uma gem do Ruby, que atua como um preprocessador de Css. Ela te dá a oportunidade de trabalhar com variáveis, funções e loops dentro da sua folha de estilos. Sendo assim, agilizando o desenvolvimento e trazendo a opção de reutilização de códigos.

O Sass permite que você crie o seu arquivo com dois tipo de extensões:

* **estilo.sass** : Quando criamos um arquivo **.sass**, temos que obrigatoriamente utilizar a indentação como base para a escrita dos parâmetros e regras, o Sass utiliza essa indentação para definir o que pertence ao que, além de não utilizar **;** e nem **{}** no código.
* **estilo.scss** : Também podemos criar um arquivo **.scss**, este, por sua vez, é o mais indicado, além de utilizar **;** na escrita, ele acaba sendo o que chega mais perto do próprio Css que utilizamos.

Veja o exemplo na imagem a seguir:

<img src="http://i.imgur.com/Lor7JjK.png?1" />

## Instalação

Como dito em outro momento, estou utilizando o Linux para administrar este blog e fazer suas configurações, pois o Jekyll exige isso. Então, apesar de já ter instalado e trabalhado com o Sass no Windows, estarei utilizando o próprio Ubuntu neste exemplo de instalação.

Para instalarmos o Sass no Ubuntu, primeiro devemos ter o Ruby instalado na máquina, geralmente o Ubuntu já vem com ele, mas, caso o seu não tenha, abra o terminal e digite os seguintes códigos:

Lembrando que para checar se na sua dist há o Ruby, digite:

    $ ruby -v

Ele deve retornar a versão atual instalada na sua máquina, caso não apareça nada, digite o seguinte comando para instalar:

    $ sudo apt-get install ruby-full

Após a instalação ser concluída, digite o comando de verificação da versão novamente, e se desta vez aparecer o numero, então tudo está rodando corretamente. Agora vamos instalar o Sass:

    $ sudo gem install sass

Depois que concluir a instalação, faça a verificação com o comando **sass -v**.

## Criando um arquivo Sass

Agora que já estamos com tudo instalado, vamos criar o nosso primeiro arquivo Sass, Crie uma pasta chamada Sass, dentro dela crie outras duas pastas chamadas Css e Sass.

Exemplo:

      Sass
      '-- Css
      '-- Sass

Dentro da pasta Sass, criamos um arquivo chamado estilo.scss. Com o terminal aberto, digite o seguinte comando:

    sass --watch  entrada:saída

    sass --watch sass/estilo.scss:css/estilo.css

O comando acima significa que o Sass ficará "assistindo" o arquivo estilo.scss e, a cada alteração, irá atualizar o arquivo estilo.css. Sua estrutura de pastas deve estar da seguinte maneira:

Exemplo:

    Sass
    '-- Css
          '-- estilo.css
          '-- estilo.css.map
    '-- Sass
          '-- estilo.scss

## Variáveis

Agora que já estamos com tudo funcionando corretamente, vamos começar a trabalhar com as variáveis dentro do próprio arquivo Sass. Abra ele e digite o seguinte código:

    $laranja : #f50;

    body {
        background: $laranja;
    }

O Sass utiliza o **$** para identificar a variável e **:** para separa-lá de seu valor.
Você pode criar variáveis para diversos tipos de utilidades, como por exemplo:

    $laranja : #f50;
    $padding : 8px;

    p {
        padding: $padding;
    }

    ul {
        li {
            color: $laranja ;
          }
        padding: $padding;
    }

Com isso, em vez de ter que ficar buscando no código os padding 8px ou todos os lugares que utilizaram a cor laranja, você pode simplesmente alterar a variável, que todos irão ser alterados automaticamente.

## Funções

Agora vamos brincar um pouco. xD

No Sass você também pode criar funções e loops de códigos para gerar blocos automaticamente. Eu disponibilizei aqui no meu [Github](https://github.com/ihFernando/Funcao-o-Padding-Margin-SASS), um **for** que gera padding e margin de 6 em 6 para top, right, bottom e left, do 0 até 15. Esse **for** foi apenas uma brincadeira que fiz e vou estar utilizando ele para este exemplo.

O código é o seguinte:

    @for $i from 0 through 15 {

      .#{padding}-#{$i} {
        padding: $valor2 * $i
      }

      .#{padding-top}-#{$i} {
        padding-top: $valor2 * $i
      }

      .#{padding-left}-#{$i} {
        padding-left: $valor2 * $i
      }

      .#{padding-right}-#{$i} {
        padding-right: $valor2 * $i
      }

      .#{padding-bottom}-#{$i} {
        padding-bottom: $valor2 * $i
      }

      .#{margin}-#{$i} {
        margin: $valor2 * $i
      }

      .#{margin-top}-#{$i} {
        margin-top: $valor2 * $i
      }

      .#{margin-left}-#{$i} {
        margin-left: $valor2 * $i
      }

      .#{margin-right}-#{$i} {
        margin-right: $valor2 * $i
      }

      .#{margin-bottom}-#{$i} {
        margin-bottom: $valor2 * $i
      }
  }

Iniciamos o for colocando o contador e definindo o seu valor de início e fim, depois chamamos esse contador novamente para atribuir o valor que será gerado em cada classe.

    .#{padding}-#{$i} { //Aqui chamamos o nome da classe e o contador
        padding: $valor2 * $i //Aqui chamamos a propriedade css e o valor que ela irá receber
    }

Adicione este código ao seu **estilo.scss** e salve, veja o resultado no **estilo.css**. Como eu comentei, esta foi apenas uma brincadeira que fiz, então o código gerado é extremamente grande de propósito. Serve de exemplo para termos uma noção do quanto ele pode agilizar o nosso trabalho.

## Bônus e Conclusão

Também podemos gerar um arquivo Css já minificado, digitando no terminal:

    sass --watch sass/estilo.scss:css/estilo.min.css --style compressed

Para concluirmos, note que na verdade o Sass é uma ferramenta bem simples e que pode ser utilizada de diversas formas, podemos fazer mixins, cálculos e outras coisas muito interessantes nele, coisas que só tendem a facilitar o nosso desenvolvimento.

Pelo fato deste post ter ficado um pouco grande demais, eu deixei passar alguns tópicos, irei falar deles em outra oportunidade. Espero ter ajudado a esclarecer suas dúvidas, vale lembrar que eu não sou nenhum expert no assunto, então se algo der errado, pode comentar para tentarmos resolver juntos.

Até a próxima!

#### Links úteis:

* Ruby - https://www.ruby-lang.org/pt/
* Sass - http://sass-lang.com/
* Vídeo aula - https://youtu.be/D9OpSGViDgA?list=PL3C05B7A66AC502CF
* Introdução ao Sass - http://websocialdev.com/2013/11/05/introducao-ao-sass/