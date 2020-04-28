# Guia de ferramenta de versionamento Git
</br>
</br>

  Neste documento falará um pouco da ferramenta de versionamento git, e mostrara os comandos basicos que se precisa dominar para poder utilizar o git. Se você não sabe nada sobre o git acesse o site: (https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control), pois nele você verá uma breve história do git, o que é essa ferramenta, porque ela é importante, e assim, só lendo o primeiro capitulo estará pronto para saber seus principais comandos.


  Agora que você, se não sabia, já sabe o que é o git, está pronto para continuar e ver os prinipais comandos que se deve saber sobre o git, que irão facilitar a sua vida, seja você um simples úsuario afim de tal ferramenta, ou até mesmo um programador junior ou experiente.


* Fazendo algumas configurações e criando um repositório:


Você precisara fazer algumas configurações em seu git apos instalar em sua maquina, e para começar os seus projetos, você precisara de uma pasta para guardar seus projetos. Este guia estara sempre mostrando comandos no terminal para o Linux, se quisar usar outro sistema terá que dar uma pesquisada mais aí.

```sh
$ git config --global user.name "seu nome"
(configurar seu nome)
$ git config --global user.email seu email
(configurar seu email)
$ git config --global core.editor "seu editor"
(configurar seu editor padrão como o VSCode ou Sublime)
$ mkdir <nome do diretorio> 
(Diretório de progetos)
$ git init <nome do repositorio criado>
(Aqui o git é iniciado em seu repositório com uma pasta .git)
md <nome do diretorio>
(aqui nos entramos no diretorio que você ira salvar seus arquivos)
```


  Pronto! Agora você tem o git configurado com seu nome, email, editor e em sua pasta, assim poderá começar seus projetos, para ver suas configuração digite o comando:

```sh
$ git config --list
clear
(Para apagar tudo e começar a trabalhar, comando opcional)
```

***

   * Criando nossos arquivos
  Agora vamos criar nossos arquivos, todo repositório tem como padão, criar um README.md e um LICENSE. No README.md, você descreve seu projeto, colocando para que ele serve, e algumas informações adicionais, e o LICENSE, para escrever qual sua licença quado for jogar isso em uma máquina remota como o github, e provavelmente você ira escoher a licensa MIT.

```sh
$ touch README.md
(criar um arquivo chamado README, você tambem pode trazer um arquivo ja pronto)
$ touch LICENSE
(criar um arquivo chamado LICENSE)
$ git add README.md
$ git add LICENSE
(até agora o repositório estava apenas em seu diretório, agora você o adicionou ao git)
```


  Pronto! agora você tem os dois arquivos padrão e agora adicione os arquivos que você quiser como seu projeto, seu site, ou somente seus lembretes mesmo se quiser.

***

   * Primeiro commit:

  Agora vamos salvar esses arquivos em seu git, pois até agora você criou dois arquivos e os adicionou ao git, porem para salvar esses arquivos no git é necessário dar o commit, que salva as alterações, se você quiser ver o status de seu git digite ... git status ... e agora você vê que tem arquivos não salvos e para salva-los vamos fazer nosso commit.

```sh
$ git commit -m "Primeiro commit"
(fazendo commit)
$ git status
(ver que não ha mais alterações)
$ git log
(ver seus commits)
```


  Você pode adicionar os arquivos no git e na mesma linha já criar um commit com o comando ... $ git commit -am "Primeiro commit", e esse a atrás do m vem de adicionar e o m de minimizar, ou seja, um commit simples com descrição.

***

   * Modificando arquivos:

  Se você quiser adicionar um arquivos, ou modificalos, tera que fazer um novo commit, para que ele carregue essas modificações para o git.
  E você pode modificar, abrindo seu editor, ou por comando mesmo, vamos supor que você queira acressentar algo em seu README.md, pois por enquanto você só adicionou ele mais não colocou nada:

```sh
$ echo "Esse arquivo é feito para..." > README.md
(escrever em README.md)
$ git status
(ver o status dos arquivos)
$ git commit -m "Escrevi em README.md"
(Comite as alterações)
$ git status
(ver o status)
$ git log
(ver os commits)
$ echo "Alterando arquivo" >> README.md
(fazer alterações em README, >> para acresentar linha)
$ git commit -m "Adicionando linha em README.md"
```


  Pronto! Agora você pode adicionar, renomear e modificar os seus arquivos e após isso é só gerar um commit para salvar.
*Obs: o README.md pode ser escrito em markdown, que é uma linguagem de hipertexto para documentos.

***

   * Voltando em versões anteriores:

  Se você fez uma modificação em um determinado arquivo e agora percebeu que acabou dando problema e precisa da versão anterior, o git tambem faz isso para você. Cada commit tem um codigo, e precisaremos deste código para poder voltar. Você pode consutar ele com o comando ... $ git log ...
  E agora se juntarmos esse código ao comando abaixo, poderemos então restaurar o projeto antes do commit, ou em qual commit você quiser.

```sh
$ git log
(consutar o código)
$ git reset --hard <codigo>
(volta no commit que selecionou)
```


  E agora você não pede mais os arquivos modificados.

***

   * Navegando entre as branch:

  As branch, podem serem entendidas como versões do seu projeto, de padrão se inicia com a branch master, onde você adiciona, renomeia e modifica seus arquivos. Mas você pode tambem ter uma branch teste e após comitar em seu projeto e ver que pode adicionar ou testar um recurso, você pode adicionar uma nova versão como a teste e modificar testar e fazer o que quiser nela que na branch master estara intacta. Vamos fazer alguns testes para entender melhor esse recurso.

```sh
$ git branch
(Ver em qual branch estamos)
$ git branch teste
(Cria uma nova branch)
$ git checkout teste
(Ir para branch teste)
(Agora podemos modificaros arquivos)
$ git commit --m "Modificação em nova branch"
(Fazer o commit em nova branch)
$ git checkout master
(Voltar para branch master)
$ git status
(Ver que nada mudou nesta nova branch)
git branch
(Ver que mudamos para essa nova branch)
```

***

   * Comando diff:

  Quando estamos trabalhando com dois arquivos é possivel tirar a diferença entre eles, ou seja, o Path entre eles, e o comando diff faz exatamente isso, tira o Path dos arquivos.

...
$ git diff
(Tirar a diferença)
...


  Agora você pode ver tudo que foi modificado e fazer seu commit. É possivel tambem com o comando diff ver só quais arquivos foram modificados:

```sh
$ git diff --name-only
(Ver os arquivos modificados)
```


  Tambem é possivel dirar a diff de apenas um arquivo em especifico, como por exemplo:

```sh
$ git diff <nome do arquivo>
(ver a diferença entre determinado arquivo)
```

***

   * Revertendo modificações de um unico arquivo:

  Aprendemos como reverter commits e trazer novas modificações, mas e se você modificou varios arquivos e quer voltar apenas um arquivo em como ele estava antes do commit anterior. E então precisaremos aprender um novo comando:

```sh
$ git checkout HEAD -- <nome de arquivo>
(trazendo as configurações anteriores)
```


  Agora podemos, no branch que estamos atravéz do comando HEAD, voltar, com o comando checkout, para o estado anterior.

   * Salvando no GitHub:

***

  Você precisara agora salvar seus projetos no GitHub, pois ate agora, os arquivos estão salvos apenas em sua maquina local, você precisa passar isso para uma maquina remota como o GitHub. E para fazer isso você precisara fazer uma conta no GitHub, se não tiver e criar um repositório. 
  Após isso, você precisara dar um push, ou seja, enviar o repositório que esta em sua maquina para o GitHub, criando uma SSH e configurando ela no Git onde tem a opção configurações. E para fazer isso, você precisa gerar uma chave ssh e por ela passar seus arquivos para o github. Primeiro vamos gerar essa chave ssh com o seguite comando:

```sh
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
(gerar chave ssh)
(obs: o e-mail deve ser o mesmo que o do github)
(e assim, ele mostrara onde ele ira salvar a chave publica e a privada, aperte [enter])
(depois informe sua senha e depois confirme ela novamente)
```


  Agora precisamos passar essa chave para o GitHub e transferir os arquivos. Entre no local onde ele baixou a chave, copie essa chave (não o arquivo, o conteúdo dele), acesse seu GitHub clicle em seu avatar do canto superior direito e clica em setings. Após isso clice em ssh and gpq keys, crie uma nova ssh e cole a chave na opção informada, e escreva um titulo, que lembre seu pc por exemplo <seu usuário> home.

  Pronto! você agora tem uma chave ssh, vamos passar os arquivos através dessa chave. Escreva em seu terminal:

```sh
$ git remote add origin https://<o endereço de seu repositorio do github>.git
(adicionar repositorio origin em ...)
(você pode ver se ele adicionou com git remote)
$ git push -u origin master
(da um push do branch master para o repositório origin)
```


  Pronto! você ja tem o repositório no GitHub, basta atualisar seu GitHub que o repositório estara lá.

***

   * Dando Push e Pull:

  Se você ainda não sabe, Push é basicamente que empurrar, e quando se aplica ele no termina ou manda o GitHub dar um Push, é o mesmo que dizer empurre, ou transfira os arquivos para o GitHub. Já o Pull, busca arquivos alterados do GitHub para sua maquina. E alem desses, ainda tem outro termo impotante que vale citar, o fetch, que é usado para atualizar o repositório local, para ver se não foram feita nenhuma alteração do GitHub, sim da para alterar pelo GitHub 
  Para dar esse comandos é bem simples, basta digitar:

```sh
$ git push origin master
(empurrar os arquivos para o GitHub)
$ git pull origin master
(puxar do GitHub)
$ git fetch origin master
(atualizar os arquivos local)
```

***

   * Ignorando arquivos:

  Ignorar um arquivo no GitHub, é arquivar sem que mostre como um arquivo escondido, e para fazer isso, crie um arquivo chamado .gitignore, e nele coloque o que você quer deixar oculto, ou seja, ignorar. Escreva no arquivo que você criou, o nome dos arquivos que você quer ignorar.

***

   * Comando git revert:

  Esse comando tambem serve para reverter as ações, porem ele não perde as alterações, pois ele deixa o commit das alterações la, e cria um novo com a situação anterior. E se você quiser pegar de novo essas alterações, ela esta salva em seus commits e você só precisa dar um reset --hard:

```sh
$ git revert --no-edit <codigo do commit que deu o problema>
(faz um novo commit com a situação anterior do commit que deu o problema)
```

***

   * Adicionando e Deletando branchs remotos e locais:

  Para enviar seus branchs para o seu repositório remoto, é só substituir o push de branch master para <nome do branch>, mas se você quer deletar esse branch que você ja criou, escreva: 

```sh
$ git branch
(consutar o branch)
$ git checkout <nome do branch>
(muda o branch)
$ git push origin <nome do branch>
(envia o branch para o repositorio remoto)
$ git branch
(consutar o branch)
$ git push origin :<nome do branch>
(remover branch do repositorio remoto)
$ git checkout master
(ir para branch master)
$ git branch -D teste
(remover no repositorio local)
```

***

   * Clonando Projetos:

  Na verdade isso é bem simple, é preciso apenas pegar a url do projeto que você que clonar e escrever:

```sh
$ git clone <link>
(clone o repositório tal)
```

  Não é possivel dar push já que você clonou um projeto que ja pertencia a alguem, se você quiser dar push em um projeto que não é seu, é preciso fazer um fork do projerto pronto, clonar ele e ai sim dar seu push.

***

Dicas Finais:

1. Se você quer excluir um arquivo ou renomear do repositorio remoto, pode fazer isso de seu terminal digitando o comando git remote, e após a ação que quer fazer, seja ela remover ou renomear.