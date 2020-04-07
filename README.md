# Git-Flow

Links úteis para este estudo:

- https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html#sobre
- https://github.com/nvie/gitflow

## Resumo do que é o Git-flow

É uma metodologia que tem o intuito de agilizar o processo de commits. É de fato muito mais tranquilo para ser utilizado comparado ao uso do git puro!

## Iniciando um projeto com Git-flow

O comando `git flow init -d` iniciará o git com a estrutura inicial do flow, com as branchs `develop`, `hotfix`, `bugfix`, `feature`, `release`.<br>
Mas também é possível iniciar um projeto com a estrutura de branchs que atende melhor a estrutura do projeto usando o comando `git flow init` e criando as branchs com a nomenclatura que deseja.

## Comandos mais utilizados no Git-flow

> <sub>Vou utilizar como exemplo o hotfix, mas para as demais branchs funciona da mesma forma.</sub>

##### Criar a nova branch

O comando para iniciar uma nova branch é:

```
git flow hotfix start meu-primeiro-hotfix
```

Esse comanda criará a branch `hotfix/meu-primeiro-hotfix`, e ele se baseará na branch master para trazer os arquivos do projeto.

##### Adicionar commit ao HEAD

Os comando de `git add` e `git commit` devem ser utilizados normalmente para salvar as alterações no `HEAD` do git.

##### Publicando as alterações em um repositório remoto

Para subir uma nova alteração para que outros devs consigam trabalhar nela o comando é:

```
git flow hotfix publish meu-primeiro-hotfix
```

> :warning: <br><br> <i>É indicado que esse comando sempre seja para a branch release, nas demais branchs o uso é totalmente opcional e de acordo com a necessidade do projeto!</i>

Esse comando fará o papel do git push, subindo as informações para o repositório remoto.

##### Finalizando a branch

o comando para fechar a branch de hotfix quando todas as alterações forem finalizadas é:

```
git flow hotfix finish meu-primeiro-hotfix
```

Esse comando fará com que a branch de hotfix seja fechada e mergeará com a branch base.

> No caso do hotfix e do bugfix, eles serão mergeados com a branch master e com a branch develop, mas isso é exclusivo somente de hotfix e bugfix.<br><br>
> A branch feature é somente mergeada com a develop.<br><br>
> E a branch release cria uma nova versão mergeando a develop com a master.

## Branchs

#### Master

A branch master é a branch base para a criação de novas correções de bugs, e ajustes rápidos.

#### Develop

A branch develop é a branch base para a criação de novas features e novas releases.

#### Feature

O comando para iniciar uma nova feature é `git flow feature start NOME_DA_BRANCH_DE_FEATURE`, esse comando fará com que a branch `NOME_DA_BRANCH_DE_FEATURE` seja criada a partir da branch develop em sua última versão.

#### Release

O comando para iniciar uma nova release é `git flow feature start NOME_DA_BRANCH_DE_RELEASE`, esse comando fará com que a branch `NOME_DA_BRANCH_DE_RELEASE` seja criada a partir da branch develop em sua última versão.

Essa branch também fará com que uma versão seja fechada se baseando em um commit em específico, utilizando o comando `git flow release start RELEASE COMMIT_DE_REFERENCIA`

#### Bugfix

O comando para iniciar um novo bugfix é `git flow bugfix start NOME_DA_BRANCH_DE_BUGFIX`, esse comando criará uma branch se baseando na master.

#### Hotfix

O comando para iniciar um novo hotfix é `git flow bugfix start NOME_DA_BRANCH_DE_HOTFIX`, esse comando criará uma branch se baseando na master.

