<div style="align:center; text-align:center; align-items:center;">
  <img src="./assets/banner.jpg">

  <h1>GUIA RAPIDO GIT & GITHUB</h1>

  <a href="https://www.linkedin.com/in/jeffersonsjunior/">
    <img alt="Made by jefferson1104" src="https://img.shields.io/badge/made%20by-jefferson1104-blue">
  </a>
  
  <img alt="License" src="https://img.shields.io/badge/license-MIT-brightgreen?color=blue">
  <br>
</div>

Este e um guia rapido com explicacoes basicas dos comandos git para utilizar no seu controle de versao de codigo para seus projetos, segue tambem algumas dicas para boas praticas.

## GIT
O git denominado por muitos como um VCS (Version controle service) e um sistema de controle de versao distribuido.

## GITHUB
O github e uma plataforma ou podemos dizer tambem rede social para desenvolvedores, onde armazenamos nossos codigos/projetos em um repositorio remoto com o controle de versao de codigo de cada projeto.

<hr>

## CONFIGURACAO INICIAL
>Baixe o git e instale em seu computador de acordo com seu sistema operacional, baixe atraves so site oficial [clicando aqui](https://git-scm.com).


### Veja abaixo alguns comandos iniciais de configuracao:
_importante frisar que cada nivel de configuracao sobrescrevre os valores do nivel anterior_

`$ git config --local user.name "Seu nome para exibicao"`
`$ git config --local user.email "seu.email@email.com"`
Comandos para criar uma configuracao inicial de nivel de projeto, define os dados de acesso, uma identidade para apenas aquele projeto especifico.

`$ git config --global user.name "Seu nome para exibicao"`
`$ git config --global user.email "seu.email@email.com"`
Comandos para criar uma configuracao inicial de nivel de usuario, define os dados de acesso, uma identidade para apenas um usuario especifico do sistema operacional.

`$ git config --system user.name "Seu nome para exibicao"`
`$ git config --system user.email "seu.email@email.com"`
Comandos para criar uma configuracao inicial de nivel sistema para todos os usuarios, define uma configuracao de identidade global com dados de acesso para todos os usuarios do sistema operacional.

`$ git config --global core.editor "Caminho do editor de texto"`
Com este comando voce define qual o editor de texto default do seu git.

`$ git config --list --show-origin`
Com este comando voce consegue visualizar onde esta armazenado o seu arquivo de configuracao do git.

`$ git config --list`
Com este comando voce consegue visualizar os dados definidos na configuracao atual do seu git.

**abaixo segue uma sequencia de comandos que editam as configuracoes de cores do seu git:**
```
$ git config --global color.ui auto
$ git config --global color.diff auto
$ git config --global color.status auto
$ git config --global color.branch auto
```

<hr>


## FLUXO DE OPERACOES
Os fluxos de operacoes do git sao organizados em 4 estruturas, veja abaixo quais sao:
> - **WORKSPACE**: pasta/diretorio onde contem todos os arquivos do projeto, codigos, configuracoes e etc.
> - **INDEX**: conhecindo tambem como area temporaria e tambem chamada de *'staging area'*, nesta estrutura ficam armazenados os arquivos que modificamos, excluimos, adicionamos antes de ser enviados para o repositorio local (HEAD)
> - **HEAD**: conhecido tambem como repositorio local, nesta estrutura ficam armazenado em ambiente local diversos versoes do codigo do projeto , aqui dentro tambem fica seu workspace, que anteriormente citado e o diretorio onde contem seus arquivos do projeto.
> - **REPOSITORIO REMOTO**: o proprio nome ja descreve esta estrutura, este e o local onde voce vai hospedar seus arquivos do seu projeto com todas as versoes e ramificacoes para compartilhar e armazenar em nuvem.

![Alt ou título da imagem](./assets/estruturas.png) 


**GIT INIT**
Inicia um repositorio vazio no seu projeto.

**GIT ADD**
Transfere os arquivos do seu WORKSPACE para seu INDEX (area temporaria)
 
**GIT COMMIT**
Transfere seus arquivos criados/modificados para o HEAD (repositorio local)
 
**GIT CHECKOUT**
Retorna ou avanca para uma determinada ramificacao (branch) do seu projeto, ou seja ele vai para uma versao especifica do seu codigo.

**GIT DIFF**
Verifica as diferencas entre os codigos/arquivos do seu projeto no WORKSPACE comparando com o HEAD (repositorio local).

**GIT FETCH**
Atualiza o HEAD (repositorio local) sincronizando com o seu REPOSITORIO REMOTO, desta maneira atualizado seu HEAD.

**GIT PULL**
Transfere ou atualiza os arquivos do seu HEAD (repositorio local) sincronizando a partir do seu REPOSITORIO REMOTO, desta maneira atualizando seus arquivos do projeto em seu WORKSPACE.

**GIT PUSH**
Transfere ou atualiza seu REPOSITORIO REMOTO com os novos arquivos criados/modificados no seu HEAD (repositorio local).

<hr>

## DICAS DE BOAS PRATICAS
* Em todos os projetos voce pode criar um arquivo com o nome ".gitignore" dentro deste arquivo voce pode declarar qual diretorio e arquivos voce deseja que o git ignore e nao faca upload para seu repositorio remoto.

* Importante que antes de qualquer COMMIT voce faca um GIT PULL do seu repositorio remoto para atualizar o repositorio local quando voce esta trabalhando em equipe em um determinado projeto, dessa forma voce evita conflitos corrigindo qualquer possivel conflito direto no seu HEAD (repositorio local), antes de fazer um GIT PUSH e causar este conflito no seu REPOSITORIO REMOTO.

<hr>

## PRINCIPAIS COMANDOS

`$ git init`
Inicia um repositorio vazio no seu projeto.

`$ git add * `
Transfere todos os arquivos criados/modificados do seu projeto para o INDEX (area temporaria).

`$ git commit -m "descricao do seu commit"`
Transfere os arquivos criados/modificados da sua INDEX (area temporaria) para seu HEAD (repositorio local), identificando pela descricao do commit o que ele esta atualizando/incrementando.

`$ git commit --amend -m "atualiza a descricao do commit"`
Caso voce tenha feito um commit e nao gostou da sua descricao, e possivel alterar esta descricao executando este comando antes de fazer um push para seu REPOSITORIO REMOTO.

`$ git status`
exibe os arquivos criados/modificados que estao na sua INDEX (area temporaria) prontos para ir ao seu HEAD (repositorio local).

`$ git clone usuário@servidor:/caminho/para/o/repositório`
Com este comando voce pode clonar um REPOSITORIO REMOTO, baixar todo o codigo fonte para sua maquina local.

`$ git remote add origin usuário@servidor:/caminho/para/o/repositório.`
Com este comando voce pode adicionar em sua WORKSPACE a conexao de um REPOSITORIO REMOTO e desta maneira atualizar modificando ou inserindo novos arquivos.

`$ git checkout -b "nome da branch"`
cria uma nova branch (ramificacao) no seu projeto.

`$ git branch`
Lista as todas as branchs (ramificacoes) existentes no seu projeto.

`$ git checkout "nome da branch"`
Com este comando voce vai para uma determinada versao ou ramificacao do seu projeto.

`$ git merge "nome da branch"`
Com este comando e possivel voce fazer incluir na branch (ramificacao) atual as alteracoes feitas ou criadas em outra branch, desta forma incluindo partes de codigos/arquivos, atualizando arquivos e etc... 

`$ git branch -d "nome da branch"`
este comando voce deleta uma ramificacao (brach) do seu projeto.

`$ git log`
este comando lista todos os commits do seu branch (ramificacao).

`$ git fetch`
Atualiza/transfere todos os branchs existentes no REPOSITORIO REMOTO para seu HEAD (repositorio local), necessario fazer um *"$ git pull"* logo apos executar este comando.

`$ git pull`
Transfere seus arquivos criados/modificados existentes no seu REPOSITORIO REMOTO para o HEAD (repositorio local) sincronizando/atualizando seu workspace e vice-versa.

`$ git push -u origin master`
Transfere e atualiza seus arquivos criados/modificados do seu repositorio local para seu REPOSITORIO REMOTO na branch MASTER.

<hr>

## VARIAVIES DE AMBIENTE
Podemos definir e guardar em variavies de ambiente as informacoes de uso global do projeto, como por exemplo usuario de banco de dados, senha de banco de dados, porta de conexao, nome de servidor e etc... essas variaveis de ambiente sao armazenadas em uma variavel global chamada **process.env**

Abaixo vamos ensinar a criar exemplo de projeto utilizando javascript com nodeJS, para que voce possa compreender melhor essas variaveis de ambiente.

> Necessario que voce tenha instalado em sua maquina o **nodeJS** e tambem o gerenciador de pacotes **NPM**


Inicie um novo projeto, crie um diretorio e execute os comandos para iniciar e instalar um pacote do node_modules chamado **dotenv**, veja abaixo os comandos:

```
  $ npm init -y
  $ npm install dotenv
```

Agora na raiz do projeto crie um arquivo chamado **.env** e dentro deste arquivo coloque o conteudo abaixo:

```
USERDB="myUserTest"
PWDDB="123456"
```

Por ultimo vamos criar um arquivo chamado **index.js** e dentro dele coloque o conteudo abaixo:
```
require('dotenv').config();

console.log(process.env.USERDB);
```

Para exibir as informacoes da variavel de ambiente colocamos um console.log(), voce pode executar este programa no terminal com o seguinte comando:
`$ node index.js`

