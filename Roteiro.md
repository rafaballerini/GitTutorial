# Roteiro - Como usar o GIT
Roteiro para o vídeo no Youtube de como utilizar o git na prática

### Início do vídeo

Oie gente sejam bem vindos a mais um vídeo aqui do canal, eu sou a Rafaella Ballerini e hoje eu vou mostrar pra vocês como utilizamos o GIT na prática

No vídeo anterior eu expliquei os conceitos de alguns termos técnicos que utilizamos quando estamos usando o git (aponta p caixinha), então nesse vídeo vou mostrar na prática como isso acontece

### Instalando o GIT

* [Link com os downloads](https://git-scm.com/downloads)
* Bem tranquilo de instalar

### Criar um projeto novo

* Criar uma nova pasta no PC pra isso chamada "Git Tutorial"
* Abrir o VSCode nessa pasta
* Criar um novo arquivo "README.md"
* Explicar o que é Markdown e a importância de usarmos um ReadMe
* Escrever dentro dele "Olá, nesse projeto você aprenderá alguns comandos do Git"
* Salva o arquivo
* Agora então é hora de usarmos o Git
* Abre o git bash (fala que pode ser pelo terminal do VSCode mesmo)
* `git init` para inicializar o repositório
* Mostra que criou uma pastinha `.git` e é ali que toda a mágica acontece, então não apague
* `git add README.md` para colocar o arquivo na área de stagging 

<img src="https://i1.wp.com/www.markus-gattol.name/misc/mm/si/content/git_git_add.png">

* Esse add é necessário antes de darmos o commit de fato, mas por que isso? No final do vídeo explico para vocês

* `git commit -m "primeiro commit"` para de fato dar o commit no repositório

### Interfaces Git

* Beleza, recebemos a confirmação de que o commit aconteceu, mas isso tá um pouco abstrato ainda né?

* Existem algumas interfaces legais do git que você pode fazer o download para poder visualizar de fato como está o projeto, o que foi alterado em cada commit, quando foi alterado etc.

* Aqui eu vou mostrar pra vocês a usarem direto o Github, então vamos lá

### Repositório no Github

* Depois de você ter criado a sua conta na plataforma, você irá em `Criar novo repositório`
* Você vai preencher co as informações do projeto, então dar o nome do repositório, colocar uma breve descrição e criar
* Logo depois vai aparecer essa página um pouco cinza e confusa, mas o que você tem que fazer é bem simples
* Lembra do conceito de remote que eu expliquei pra vocês no último vídeo? Nós iremos utilizá-lo agora
* Para passar o commit do meu repositório local (da minha máquina) para um repositório na plataforma do Github, usamos o `git remote add <nome do repositório (origin)> <link do repositório>`

* Agora já temos o nosso repositório local conectado com o respositório do Github, porém o commit que damos na máquina não sobe automaticamente para a plataforma

* Para isso precisaremos empurrar, enviar para lá com o `git push -u origin master`

* Agora se recarregarmos a página iremos ver o nosso arquivo aqui na plataforma!

### Alterando e adicionando arquivo

* Beleza, agora que temos o nosso repositório no Github configurado direitinho, podemos usar e abusar do que o Git oferece, afinal é pra isso que estamos utilizando ele né

* Primeira coisa que faremos então é alterar esse arquivo que já commitamos

* Adiciona mais uma frase no arquivo `Essa é uma alteração`

* Além disso iremos criar um novo arquivo `Projeto.md`, onde escreveremos `Esse é o arquivo onde desenvolverei o meu projeto`

* Agora então precisamos subir essa alteração, pra isso seguiremos os mesmos passos de `git add .` (agora ponto para explicar que adiciona todos) e `git commit -m "Primeira alteração"`

* Lembrando que para alterar algo no nosso respositório do Github precisamos dar o push, então `git push origin master` (sem o -u)

* Se olharmos agora o nosso código no Github, ele terá sido alterado, e não só isso, se clicarmos no nome do commit, podemos ver exatamente as alterações que foram feitas nele

* O verde com `+` e o vermelho com `-` mostra, os conteúdos que foram adicionados e editados dentro do código

* Aqui nesse botão poderemos ver todos os commits já feitos anteriormente, então se clicarmos em algum deles, veremos exatamente o que havia sido alterado, além de claro, vermos o código como era. Incrível né?

### Branch

* Até agora tudo o que fizemos de alterações e mandamos de commit, foi na nossa master, que é aquela linha do tempo principal

* Agora vou mostrar pra vocês como criamos uma branch e depois como que juntamos ela com o código que já está na master (lembrando que ela é uma linha cronológica adicional/alternativa a principal)

* Lembrem que eu estou aqui editando um arquivo markdown, porém isso tudo vale para qualquer tipo de arquivo com qualquer extensão

* E outra, a branch pode ser criada tanto para quando você for fazer uma alteração em um arquivo, quando para adicionar outro arquivo dentro do projeto ou mesmo excluir

* Nesse caso vamos adicionar um novo arquivo para desenvolver a nossa feature "Botão"

* Então a primeira coisa que fazemos é `git checkout -b "novo-botao"`, assim criando uma branch para ele

* Esse comando além de criar a branch já entra nela com o checkout

* Inclusive se olharmos agora aqui no meu VSCode, estamos dentro dela

* Vou então criar o arquivo, criar o botão.md "aqui eu crio o botão"

* E agora fazemos o passo a passo que já sabemos, colocamos a nossa alteração em stagging com o `git add .` e commitamos com o `git commit -m "novo botão"`

* Para enviarmos agora que vai ser diferente. Vocês lembram que utilizávamos o `git push orgin master` né? Porém master era aquela branch principal. Agora então usaremos `git push origin botao`

* Agora se olharmos o nosso Github, veremos que tem 2 branches, a master e a botao

* Vamos supor que eu ainda não tivesse terminado de desenvolver o botão, eu poderia continuar tranquilamente na branch `botao` até terminar

* Mas Rafa, e se eu precisasse por algum motivo voltar naquela branch `master` e desenvolver a partir do que deixei lá? Sem problemas, a única coisa que você precisa fazer nesse caso é `git checkout master`, e pra voltar depois é só `git checkout botao` novamente

* Beleza! Agora desenvolvi tudo o que queria aqui na branch `botao` 