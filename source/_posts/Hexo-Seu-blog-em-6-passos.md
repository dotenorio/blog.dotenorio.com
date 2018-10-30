---
title: Hexo - Seu blog em 6 passos
date: 2018-10-29 23:05:48
tags: [hexo, framework, blogs, static, nodejs, javascript, markdown, open-source]
category: Geral
---

Olá!

[**Hexo**](https://hexo.io/pt-br/) nada mais é do que mais um projeto **javascript** para agilizar as coisas, ou, como ele mesmo se entitula: Um rápido, simples e poderoso framework para blogs.

Bem, suas principais caracterísiticas são:

* Feito em **NodeJS**
* Suporta **Markdown**
* Deploy simples em várias plataformas (GIT, Heroku, FTP, entre outros)
* Muitos temas e plugins
* E está no GitHub, ou seja, é **Open Source**!!

> Talk is cheap. Show me the code.

![](https://citacoes.in/media/authors/21068_linus-torvalds.jpeg)

> (Linus Torvalds)

Ok! Ok! Ok!

<!-- more -->

## Vamos fazer um blog em 6 passos, ok?

O objetivo aqui é subir esse blog no [GitHub Pages](https://pages.github.com/). Então o primeiro passo é criar um repositório...

&nbsp;

### 1) Criar repositório no GitHub

* Defina um nome e uma descrição
* Adicione um README
* Coloque na licença MIT

Estes dois últimos são só para manter organizado e livre :)

![Criar repositório no GitHub](/images/Hexo-Seu-blog-em-6-passos/1.png)

&nbsp;

### 2) Instalar Hexo CLI

É preciso instalar o CLI do Hexo, você deve executar seguinte comando:

`$ npm i -g hexo-cli`

&nbsp;

### 3) Dar `init` no blog

Agora vamos iniciar um blog com o nome do seu repositório.

`$ hexo init <your-repo-name>`

Ele vai executar uma série de comandos e deve retornar uma mensagem de sucesso como a seguir:

`INFO: Starting blogging with Hexo!`

**F I R S T&nbsp;&nbsp;W I N&nbsp;&nbsp;:)**

&nbsp;

### 4) Instalar dependências

Isso é padrão para um projeto em NodeJS, então só vai...

`$ cd <your-repo-name>`
`$ npm install`

&nbsp;

### 5) Servir localmente para ver se está tudo ok

Tenha calma, esta parte é realmente difícil.

Você está pronto?!

Tem certeza?!

Então vamos lá hein?!

Vai!!

`$ hexo serve`

Bem, foi complexo mas deve ter dado certo.
Então agora acesse http://localhost:4000 e...

![Servir localmente para ver se está tudo ok](/images/Hexo-Seu-blog-em-6-passos/2.png)

**S E C O N D&nbsp;&nbsp;W I N&nbsp;&nbsp;\o/**

&nbsp;

### 6) Fazer Deploy

Tá bom, parei de brincar... Agora vem mesmo a parte mais complicadinha, mas fácil, entendeu?!

* Precisamos de um plugin para fazer o deploy:

`$ npm i hexo-deployer-git --save`

* Precisamos também editar o `_config.yml` para adicionar as configurações do GitHub:

![Deploy - _config.yml](/images/Hexo-Seu-blog-em-6-passos/3.png)

Obviamente você deverá trocar `your-user` e `your-repo-name` pelo dados do seu repositório.
E também trocar (ou não) a *branch* para uma de sua escolha. No meu caso eu coloquei `gh-pages` pois o GitHub já reconhece e gera automaticamente uma url para seu blog.

* Agora vamos colocar esse blog no ar:

`$ hexo deploy --generate`

Isso irá gerar os arquivos estáticos e fazer o deploy no GitHub Pages..

Voilà!

`Your site is published at http://<your-user>.github.io/<your-repo-name>`

ou

`Your site is published at http://<your-custom-domain>/<your-repo-name>`

![Deploy - Your site is published at](/images/Hexo-Seu-blog-em-6-passos/4.png)

**T H I R D&nbsp;&nbsp;W I N&nbsp;&nbsp;^_^**

E é isso, seu blog está no ar!

> Acha que acabou, achou errado OTÁRIO!

# Escrevendo..

`$ hexo new [layout] <title>`

O `[layout]` pode ser `post`, `page` ou `draft`.
E `<title>` deve ser o título desejado para seu post, o mesmo que irá aparecer na URL.

* Na prática

`$ hexo new post "Teste de Post"`

Ele cria um arquivo `Teste-de-Post.md` dentro de `source\_posts` e nele você deve escrever algo como isso:

```
---
title: Teste de Post
date: 2018-10-30 00:05:58
tags: [teste, post]
category: Geral
---

Olá, como estão?

<!-- more -->

Eu estou bem :D
```

Pronto, agora é só seguir o passo 6 e ser feliz!!


> Ainda não acabou, temos que falar sobre personalizações..

# Personalizações

Eu sei que já falamos sobre o `_config.yml` mas tem muito mais coisas que vocês pode/deve configurar:

* Dados básicos do blog
* Formato da URL
* Categorias e Tags
* Data e Hora

Deve ficar mais ou menos assim:

```
# Hexo Configuration
## Docs: https://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site #### <<< Trabalhe bem esta seção, isso vai ajudar muito seu blog a ser indexado e crescer
title: My User
subtitle: A one simple subtitle
description: Hello, i'm a description
keywords: blog, myuser
author: My Name
language: pt
timezone: America/Sao_Paulo

# URL
## If your site is put in a subdirectory,
## set url as 'http://myuser.github.io/child' and root as '/child/'
url: http://myuser.github.io  #### <<< Coloque a URL do seu site
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

[...]
  
# Category & Tag
default_category: Geral #### <<< É sempre bom ter uma categoria padrão
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: DD/MM/YYYY #### <<< Mude para o formato brasileiro, por exemplo
time_format: HH:mm:ss

[...]

```

# Temas

O Hexo em seu site, disponibiliza vários [temas](https://hexo.io/themes/) criados pela própria comunidade, basta você escolher um, baixar em formato `.zip` e colocar dentro da pasta `themes`.

*Você pode usar submodule, mas confesso que é um trabalho desnecessário, prefira o zip*

Feito isso, basta trocar o tema no `_config.yml`

```
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: landscape #### <<< Coloque aqui o nome do tema que você escolheu
```

Teste o localmente usando o passo 5 para ver se está tudo ok.
Se está tudo certo, faça o processo de deploy (passo 6) novamente para ver o resultado.

**É importante saber que cada tema tem suas próprias configurações, ou seja, dentro da pasta dele também existe um arquivo `_config.yml`, pode edita-lo sem medo.**

# Plugins

O processo para uso de plugins é bem mais simples, é só dar `$ npm install --save hexo-<plugin>` e sair usando..

*Nessa caso você não precisa alterar nada no `_config.yml`*

Veja os plugins disponíveis [aqui](https://hexo.io/plugins/), baixe um, leia a documentação e divirta-se!

&nbsp;

### Por hoje é só pessoal!

Se tiver dúvidas, sugestões ou o que quer seja relacionado ao Hexo e a criação de blogs, deixe seu comentário.

É isso, até a próxima..