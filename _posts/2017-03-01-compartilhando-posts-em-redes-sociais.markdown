---
layout: post
title:  "Compartilhando posts em Redes Sociais"
date:   2017-03-01 00:20:23 -0300
excerpt: Olá caro coleguinha que está lendo, hoje estarei disponibilizando três códigos bem rápidos para criar um link de compartilhamento do seu post, página ou qualquer outra coisa que preferir em redes sociais como <strong>Twitter</strong>, <strong>Facebook</strong> e <strong>Google Plus</strong>.
categories: RedesSociais
---

# Compartilhando posts em Redes Sociais

Olá caro coleguinha que está lendo, hoje estarei disponibilizando três códigos bem rápidos para criar um link de compartilhamento do seu post, página ou qualquer outra coisa que preferir em redes sociais como **Twitter**, **Facebook** e **Google Plus**.

Neste tema que criei para o Jekyll (HopeCode), eu adicionei estes mesmos códigos, caso queira utilizar, basta acessar o repositório no meu [**Github**](http://www..com), o arquivo que vou utilizar como exemplo está na pasta **"_includes"** com nome de **"share.html"**

Atualmente uma das formas mais fáceis de atingir muitos views e acessos em uma página é compartilhando o conteúdo nas redes sociais, muitos sites/blogs já utilizam essa função, então que tal entender como funciona? Pegue o seu café e vamos começar!

### Por onde começar?

Crie um arquivo separado com o nome que desejar, o meu está com o nome de "share.html".
Dentro dele eu coloquei o código abaixo:


Para compartilhar no twitter

	
	<a class="icon-twitter" href="http://twitter.com/share?text={{page.title}}&amp;url={{site.url}}{{ page.url }}"
	    onclick="window.open(this.href, 'twitter-share', 'width=550,height=235');return false;"> 
        <span class="hidden"><i class="fa fa-twitter"></i> Twitter</span>
    </a>
		
Para compartilhar no Facebook

    <a class="icon-facebook" href="https://www.facebook.com/sharer/sharer.php?u={{site.url}}{{page.url}}"
        onclick="window.open(this.href, 'facebook-share','width=580,height=296');return false;">
        <span class="hidden"><i class="fa fa-facebook"></i> Facebook</span>
    </a>

Para compartilhar no Google Plus

    <a class="icon-google-plus" href="https://plus.google.com/share?url={{site.url}}{{page.url}}"
       onclick="window.open(this.href, 'google-plus-share', 'width=490,height=530');return false;">
       <span class="hidden"><i class="fa fa-google-plus"></i> Google+</span>
    </a> 



*O código que está entre {{exemplo}} refere-se ao padrão do Jekyll*

Cole e troque os termos pelos do seu site, como por exemplo:

**{{ page.tittle }}** = Título da página;

**{{ site.url }}** = Url do seu site;

**{{ page.url }}** = Url da página (Post)

#### Vamos analisar a semelhança entre os códigos

Até a palavra **"share"** os três mantêm a mesma lógica, depois desse pedaço cada um segue a sua linha para efetuar o compartilhamento.

O twitter é um pouco diferente pois pede o título  da página antes de pedir o link. Já os outros dois pedem apenas o link do post.

**Twitter**

    [...] share?text={{page.title}}&amp;url={{site.url}}{{ page.url }}

**Facebook**

    [...] sharer/sharer.php?u={{site.url}}{{page.url}}

**Google Plus**
   
    [...] share?url={{site.url}}{{page.url}}


### Conclusão
As redes sociais em sua maioria mantêm um padrão para essas funções, são simples e eficientes. Você pode testá-las aqui no blog, abaixo tem a opção para compartilhar. Viu como é fácil? Assim que encontrar alguma novidade e tiver mais tempo para postar, estarei disponibilizando os códigos para as outras redes.

Até a próxima!