---
layout: post
title:  " Criando um Snippet para o Emmet"
date:   2017-03-8 12:05:00
excerpt: Criando um snippet para inicialização de projeto feito com Emmet no Sublime Text 3.
permalink: criando-um-snippet-para-o-emmet
categories: SublimeText3
---

Olá caro coleguinha que está lendo, recentemente eu liberei um código no meu Github que fala sobre o **Emmet**, em que disponibilizei um arquivo para configuração de um novo snippet no próprio Emmet usando o **Sublime Text 3**.

### O que é?

O Emmet é um plugin disponível no **Sublime**, que serve para agilizar o desenvolvimento com HTML e CSS, ele te da atalhos para que você não precise escrever linha por linha do seu código.
Mas, como isso funciona? Vamos supor que você queira criar um nav, dentro desse nav você tem uma lista não ordenada com 3 itens e todos com a mesma classe e conteúdo.

Se você digitar no Sublime com o Emmet instalado, o código abaixo:

     nav>ul>li.item-lista[Itens menu]*3

e der Tab, ele irá gerar automaticamente:

     <nav>
		<ul>
		     <li class="item-lista">Itens menu</li>
		     <li class="item-lista">Itens menu</li>
		     <li class="item-lista">Itens menu</li>
		</ul>
     </nav>

Neste exemplo nós trocamos 7 linhas de código, por apenas uma.

Você pode criar atalhos maiores totalmente personalizados, assim como eu fiz com o do repositório **Snippet-Init-Project** no meu Github. Nele você vai encontrar um atalho para gerar uma estrutura que já linka o **CDN do Bootstrap 3**, vamos usar esse arquivo como exemplo.

## Criando um novo Snippet

Quando o Emmet é instalado ele deixa a opção de configuração disponível no Sublime, basta ir em:

     Preferências > Package Settings > Emmet Settings - User

<img src="http://i.imgur.com/jofHmN8.png?2" title="Exemplo de como abrir a configuração" />

Após clicar nele, uma nova janela será aberta, por padrão, ela vem vazia. é onde você vai configurar o snippet. A escrita utilizada já é definida por padrão pelo próprio plugin, começando com { }:

     {
     "snippets": {
               "html": {
                    "abbreviations": {

                    "bts-cdn": "link[href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css' type='text/css' rel='stylesheet']+script[src='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js']",

                       }
		  }
            },
      }

O código acima está chamando o CDN do Bootstrap minificado na versão 3.3.7 hospedado no site MaxCDN, assim como o script. Note que é um código simples e fácil de ser alterado. Se criarmos um arquivo HTML e digitarmos "bts-cdn" ele trará como resultado:

     <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" type="text/css">
     <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>

Após abrirmos o { }, definimos ele como snippets e a qual formato de arquivo será aplicado. Caso você tente digitar no Css, o mesmo não irá entender como um snippet e sim como uma propriedade do Css.

O arquivo que deixei open traz outros tipos de atalhos e como você pode fazer para criar vários de uma só vez.

## Conclusão

O Emmet é um plugin muito bom, que agiliza demais o desenvolvimento. Poucas pessoas o conhecem e utilizam todas as suas funções. Ele é totalmente intuitivo e tem uma documentação bem explicada. Se você já utiliza o Sublime, mas não conhece o Emmet, está perdendo tempo, teste e veja a grande diferença que ele faz.

Links úteis:

* [Emmet](http://emmet.io/);

* [Sublime Text 3](https://www.sublimetext.com/3);

* [Repositório com o exemplo](https://github.com/ihFernando/Snippet-Init-Project).
