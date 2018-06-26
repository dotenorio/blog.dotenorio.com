---
title: Criando aliases para comandos GIT
date: 2018-06-11 12:44:51
tags: [git, aliases, config]
category: Geral
---

Se assim como eu, você é o típico programador preguisoço que quer automatizar tudo, escrever pouco e tentar dominar o mundo todos com o mínimo de esforço. Bem, essa dica é pra você!

Eu sempre achei chato ter que escrever `checkout` toda vez para recuperar algum arquivo ou trocar de branch, isso por que eu sempre errava e tinha que rodar o comando mais de uma vez até acertar. 

Você pode dizer que isso dislexia. Não é!!! (pelo menos eu acho que não :p)

<!-- more -->

Piadocas a parte, descobri que o *GIT* tinha um recurso para criar aliases para seus comandos, e que é bem simples.
Por exemplo, para não ter de ~~errar~~ escrever mais `checkout` eu rodei o seguinte comando:

```
  $ git config --global alias.co checkout
```

E agora eu só preciso digitar `git co master` e pronto, me tornei uma pessoa mais feliz.

O mesmo pode ser feito pros outros comandos:

```
  $ git config --global alias.br branch
  $ git config --global alias.ci commit
  $ git config --global alias.st status
```

E como se já não fosse vadiagem demais eu criei um módulo no npm para fazer esses aliases de maineira automatizada. É só rodar `npm i -g git_aliases` ou baixar um executável no [GitHub](https://github.com/dotenorio/git_aliases/tree/master/output).

Referências
-----------

https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases
https://github.com/dotenorio/git_aliases