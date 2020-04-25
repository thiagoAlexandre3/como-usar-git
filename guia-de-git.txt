		**Guia de ferramenta de versionamento Git**


* Introdução:

Neste documento falará um pouco da ferramenta de versionamento git, e mostrara os comandos basicos que se precisa dominar para poder utilizar o git. Se você não sabe nada sobre o git acesse o site: (https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control), pois nele você verá uma breve história do git, o que é essa ferramenta, porque ela é importante, e assim, só lendo o primeiro capitulo estará pronto para saber seus principais comandos.

* Desenvolvimento:

Agora que você, se não sabia, já sabe o que é o git, está pronto para continuar e ver os prinipais comandos que se deve saber sobre o git, que irão facilitar a sua vida, seja você um simples úsuario afim de tal ferramenta, ou até mesmo um programador junior ou experiente.

	* Fazendo algumas configurações e criando um repositório:

Você precisara fazer algumas configurações em seu git apos instalar em sua maquina, e para começar os seus projetos, você precisara de uma pasta para guardar seus projetos. Este guia estara sempre mostrando comandos no terminal para o Linux, se quisar usar outro sistema terá que dar uma pesquisada mais aí.

...

$ git config --global user.name "seu nome"
(configurar seu nome)
$ git config --global user.email seu email
(configurar seu email)
$ git config --global core.editor "seu editor"
(configurar seu editor padrão como o VSCode ou Sublime)
$ mkdir <nome do diretório> 
(Diretório de progetos)
$ git init <nome do repositório criado>
(Aqui o git é iniciado em seu repositório com uma pasta .git)
md <nome do diretorio>
(aqui nos entramos no diretorio que você ira salvar seus arquivos)
...

Pronto! Agora você tem o git configurado com seu nome, email, editor e em sua pasta, assim poderá começar seus projetos, para ver suas configuração digite o comando:

...

$ git config --list
clear
(Para apagar tudo e começar a trabalhar, comando opcional)

...

	* Criando nossos arquivos: 

Agora vamos criar nossos arquivos, todo repositório tem como padão, criar um README.md e um LICENSE. No README.md, você descreve seu projeto, colocando para que ele serve, e algumas informações adicionais, e o LICENSE, para escrever qual sua licença quado for jogar isso em uma máquina remota como o github, e provavelmente você ira escoher a licensa MIT.

...

$ touch README.md
(criar um arquivo chamado README, você tambem pode trazer um arquivo ja pronto)
$ touch LICENSE
(criar um arquivo chamado LICENSE)
$ git add README.md
$ git add LICENSE
(até agora o repositório estava apenas em seu diretório, agora você o adicionou ao git)

...

Pronto! agora você tem os dois arquivos padrão e agora adicione os arquivos que você quiser como seu projeto, seu site, ou somente seus lembretes mesmo se quiser.

	* Primeiro commit:

Agora vamos salvar esses arquivos em seu git, pois até agora você criou dois arquivos e os adicionou ao git, porem para salvar esses arquivos no git é necessário dar o commit, que salva as alterações, se você quiser ver o status de seu git digite ... git status ... e agora você vê que tem arquivos não salvos e para salva-los vamos fazer nosso commit.

...

$ git commit -m "Primeiro commit"
(fazendo commit)
$ git status
(ver que não ha mais alterações)
$ git log
(ver seus commits)

...

Você pode adicionar os arquivos no git e na mesma linha já criar um commit com o comando ... $ git commit -am "Primeiro commit", e esse a atrás do m vem de adicionar e o m de minimizar, ou seja, um commit simples com descrição.

	** Modificando arquivos:

Se você quiser adicionar um arquivos, ou modificalos, tera que fazer um novo commit, para que ele carregue essas modificações para o git.
E você pode modificar, abrindo seu editor, ou por comando mesmo, vamos supor que você queira acressentar algo em seu README.md, pois por enquanto você só adicionou ele mais não colocou nada:

...

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

...

Pronto! Agora você pode adicionar, renomear e modificar os seus arquivos e após isso é só gerar um commit para salvar.
*Obs: o README.md pode ser escrito em markdown, que é uma linguagem de hipertexto para documentos.


