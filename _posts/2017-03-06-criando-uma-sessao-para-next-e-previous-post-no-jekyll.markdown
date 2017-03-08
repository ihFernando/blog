---
layout: post
title: "Criando uma sessão para Next e Previous post no Jekyll"
date: 2017-03-06 17:05:23
excerpt: Olá caro coleguinha que está lendo, o post de hoje será sobre como criar uma section no seu blog para exibir dois botões com o nome da postagem anterior e a próxima, segundo a página em que você está.
categories: Jekyll
permalink: criando-uma-sessao-para-next-e-previous-post-no-jekyll
publised: false
---

Uma função muito útil para blogs é fornecer ao leitor uma breve chamada do post que está a seguir ou o post anterior ao que eles está lendo, isso faz com que, caso o leitor se interesse pelo título da postagem, ele entre e leia.

No **Jekyll** nós também podemos desenvolver essa função, aqui no tema **HopeCode**, você pode olhar que ao final de cada post tem uma seção com dois botões, cada um indicando para um post. O código que permite isso está na própria documentação do Jekyll, mas como eu encontrei uma certa dificuldade para adicionar quando estava desenvolvendo essa parte, achei interessante deixar um post falando sobre, para auxiliar alguém que venha enfrentar o mesmo problema. Você também pode entrar no meu [**Github**](www.github.com/ihfernando/blog) e baixar o arquivo que já está com o código pronto, entretanto, se quiser saber como funciona e como você pode fazer para personalizar o seu próprio código, pegue um café e continue lendo, porque nós vamos conversar sobre isso agora!

### Entendendo a função

Enquanto estava dando uma pesquisada em alguns temas, achei essa função que me chamou muita atenção, apesar de simples, ela é bem eficiente. Utilizamos como base um **if** que checa se há ou não um próximo/anterior post, e se houver, ela exibe na tela um link para ele.

O código é o seguinte:

    <section>
        <div class="container-fluid">
            <div class="row">

                <div class="col-md-6">
                {% if page.previous %}
                    <a href="/blog{{ page.previous.url }}" rel="prev">
                        <button class="btn btn-default btn-lg btn-block"> &larr; {{ page.previous.title }} </button>
                    </a>
                {% endif %}
                </div>

                <div class="col-md-6">
                {% if page.next %}
                    <a href="/blog{{ page.next.url }}" rel="next">
                        <button class="btn btn-success btn-lg btn-block"> {{ page.next.title }} &rarr; </button> 
                    </a>
                {% endif %}
                </div>

            </div>
        </div>
    </section>

Vamos analisar um por vez, começando pelo post anterior (previous):

    {% if page.previous %} //Checa se há um post anterior
        <a href="/blog{{ page.previous.url }}" rel="prev"> //Cria link para o post anterior
            <button class="btn btn-default btn-lg btn-block" style="padding: 20px"> &larr; {{ page.previous.title }} </button> //Exibe botão com o nome do post anterior 
        </a>
    {% endif %} //Finaliza if

Após abrir a seção onde ficará o post, nós criamos um **if** checando se há ou não um post anterior, caso haja ele irá executar a condição que cria um botão com o título e link da postagem antiga.
O link é criado pelo **page.previous** que chama a página anterior e pega sua **url**, ficando;

     [...] /blog{{ page.previous.url }}

Se no mesmo **if** você chamar a página anterior novamente e pedir o título, ele te dará o título, seguindo o exemplo de:

     [...] {{ page.previous.title }}

Vale ressaltar que você pode chamar qualquer informação do post anterior, como por exemplo:

    [...] {{ page.previous.excerpt }} //Chama a descrição do post anterior
    [...] {{ page.previous.categories }} //Chama a categoria do post anterior

A mesma lógica que foi utilizada para o post previous, funciona para o próximo post, sendo assim:

    {% if page.next %} // Checa se há um próximo post
        <a href="/blog{{ page.next.url }}" rel="next"> // Cria um link para o próximo post
             <button class="btn btn-success btn-lg btn-block" style="padding: 20px"> {{ page.next.title }} &rarr; </button> //Exibe botão com o nome do próximo post
        </a>
    {% endif %} //Finaliza if

### Conclusão

Essa função é muito utilizada atualmente nos blogs, é um código tranquilo, mas que pode causar uma certa dúvida na hora de ser incorporado. Ele pode ser mais explorado seguindo os próprios exemplos da documentação, fica a seu critério ir além.

Até a próxima!
