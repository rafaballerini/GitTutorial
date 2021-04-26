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

### Alterando o arquivo

* Beleza, agora que temos o nosso repositório no Github configurado direitinho, podemos usar e abusar do que o Git oferece, afinal é pra isso que estamos utilizando ele né

* Primeira coisa que faremos então é alterar esse arquivo que já commitamos

* Adiciona mais uma frase no arquivo `Essa é uma alteração`

* Agora então precisamos subir essa alteração, pra isso seguiremos os mesmos passos de `git add .` (agora ponto para explicar que adiciona todos) e `git commit -m "Primeira alteração"`

* Lembrando que para alterar algo no nosso respositório do Github precisamos dar o push, então `git push origin master` (sem o -u)

