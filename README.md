# O que é git
* Git é um sistema de versionamento (controle de versões) de arquivos de código aberto.
* O git é usado principalmente no desenvolvimento web porém pode ser usado para o controle e registro do histórico de edições de qualaquer arquivo.
* O git também ajuda a controlar o fluxo de modificações como novas funcionalidades, ajustes, solução de problemas e etc. 
* O git permite que vários desenvolvedores possam editar coisas no mesmo projeto, facilitando trabalhos em equipe.
* O git permite que você tenha maior segurança de seus projetos, podendo voltar para outras versões caso encontre algum problema em uma modificação.

### Como instalar o git
* Caso seu sistema operacional seja o windows, basta instalar o executável neste <a href="https://git-scm.com/download/win">link</a>.
* Caso seu sistema seja Unix/Linux, basta ver a instalação para sua distro clicando neste <a href="https://git-scm.com/download/linux">link</a>.
* Caso seu sistema seja MacOs, você precisará do gerenciador de pacotes "brew", para instalar o brew basta clicar neste <a href="https://brew.sh/">link</a>. Após instalar o brew poderá instalar o git clicando neste <a href="https://git-scm.com/download/mac">link</a>.
## Funcionamento do git
* Para que seus projetos não fiquem de uma forma fixa em uma única linha cronológica e fique mais organizado, utilizamos as ramificações que podemos fazer a partir da linha principal para podermos mudar nosso código de uma forma que tenha uma organização e seleção melhor do que vamos enviar para a linha de produção. Esta linha cronológica é chamada de Branch, a linha principal é a chamada master e você pode utilizar o nome que quiser para organizar as novas linhas cronológicas. Para criarmos uma branch Updates por exemplo, utilizaríamos o comando: ```git branch Updates ```<br>
	Exemplo:
    ```
           Updates
         /
     master
    ```
    Aqui temos uma representação de duas Branch's, a principal (master) e uma secundária (Updates).
<br>

* O que permite enviarmos as modificações para nossa Branch é chamado de commit, o commit é uma forma de publicar suas modificações e atualizações do projeto. Cada commit deve ter um comentário para manter a organização de suas modificações.
Exemplo de como faríamos esses commits:

    ```
    git commit -m "A" 
    git commit -m "B" 
    git commit -m "C" 
    git commit -m "D" 
    git commit -m "E" 
    git commit -m "F" 
    git commit -m "G" 

    OBS: (Já mostraremos como enviaríamos os commits para a branch Updates e master, mas fique com o exemplo ilustrativo.)
    ```

    Exemplo de como ficaria:

             A---B---C Updates
           /
        D---E---F---G master

    Se você entendeu como é o funcionamento das Branch's e dos Commit's já viu o que fizemos. Neste caso adicionamos um commit para a Branch Updates e mais 2 commit's para a branch master.
<br>

* O merge é a ação que vai juntar o seu commit de uma outra branch para sua Branch principal, seja a master ou qualquer outra que você criar.
Exemplo:
    ```
         A---B---C Updates
       /
    D---E---F---G master
    ```
    Pegando este exemplo novamente, utilizariamos o merge na linha cronológica secundária(updates) para aplicar todas essas modificações para a linha cronológica principal (master). Utilizando o comando : ``` git merge Updates```
    Exemplo do resultado:
    ```
          A---B---C Updates
	     /         \
    D---E---F---G---H master
    ```
<br>

* Para conectar o git ao Github (ferramenta que falaremos logo em seguida), precisamos de um remote. O remote permite que o repositório local na sua máquina possa ser publicado em alguma plataforma, no caso falaremos do GitHub. Normalmente usado com um link do seu repositório no Github.
Exemplo:
    ``` git remote add origin https://github.com/Seu_Usuário/repositório.git    ```
<br>

* Para você publicar de vez no seu GitHub pelo remote, utilizaremos o git push. O push vai enviar todas suas modificações (commits) para seu repositório externo (no caso o GitHub).
Exemplo:
    ```
    git push -u origin master
    ou
    git push Updates
    ```
* Para você verificar modificações do repositório externo e poder atualizar seu projeto, usaremos o git pull. O git pull verificará as mudanças no repositório externo e aplicará as mudanças em seu repositório local. Exemplo: ```git pull```.

    Digamos que seu repositório externo esteja assim:
  	```
           A---B---C Updates
	     /          \
      D---E---F---G---H---I master
   	```

    E o seu repositório local esteja assim:
    ```  
          A---B---C Updates
        /          \
     D---E---F---G---H master
    ```
    
   Após utilizar o ```git pull``` o seu repositório local ficaria assim:
   	```
               A---B---C Updates
	         /          \
          D---E---F---G---H---I master
 	```
---

# O que é GitHub
* O GitHub é um serviço que hospeda projetos pelo sistema de versionamento Git. 
* No GitHub, podemos hospedar nossos projetos de uma forma que outros desenvolvedores possam contribuir e permite que mais desenvolvedores colaborem e façam mudanças no mesmo projeto, mantendo a segurança com um registro de todo o progresso.
* O GitHub pode ser utilizado como portfólio, a maioria das empresas vão querer o GitHub do desenvolvedor para olhar os projetos que ele desenvolveu, contribuiu, o que ele sabe fazer, qual a frequência de desenvolvimento e etc...

---
# Resumo
* O Git é uma ferramenta que vai permitir diversos desenvolvedores trabalharem no mesmo projeto, mantendo uma segurança e controle de todas as versões.
* O GitHub é uma plataforma que hospedará os projetos do git, de uma forma que diversos desenvolvedores possam publicar suas alterações e também permitindo que mais desenvolvedores contribuam com o projeto de uma maneira segura e com controle detalhado de cada alteração.

### Criando um repositório do zero e publicando no GitHub

* Primeiro criaremos uma pasta para servir de repositório local.
* Agora vamos criar um repositório externo la no github. Basta acessar seu perfil e seguir os passos das imagens seguintes.

    <img src="https://i.imgur.com/8x2GWNX.png">
    <img src="https://i.imgur.com/BYeHVfh.png"><br>
Se tudo der certo, deve carregar esta página:
    <img src="https://i.imgur.com/H4KHKVT.png"><br>
OBS: Preste atenção no nome que você colocar, pois quando usarmos o git remote, deve colocar o nome no lugar de onde coloquei test!

* Agora criaremos um arquivo README em nossa pasta local, que servirá para apresentar o seu projeto, como rodar, e etc... (Este artigo que você está lendo agora é um README). Podemos criar pelo próprio terminal com o comando: ```echo "# exemplo" >> README.md```
* Após criar o primeiro arquivo, iniciaremos o repositório, com o comando: ```git init ```
* Após iniciar o repositório poderemos adicionar o README ao repositório, com o comando: ```git add README.md ```
* Agora podemos fazer o commit de nossas mudanças com o comando: ```git commit -m "Nosso primeiro commit" ```.
* Vamos adicionar agora uma branch nova para usar como Updates, assim como no nosso exemplo, com o comando: ```git branch Updates```
* Chegou a hora de fazer o remote para conectar ao GitHub, utilizando o comando: ```git remote add origin https://github.com/Seu_Usuário/test.git```
* Para publicaremos em nossa branch master, utilizaremos o comando: ```git push -u origin master```
* Agora para finalizar, faremos o push do último arquivo, então vamos criar com o comando ```echo "print('Olá mundo')" >> app.py``` adicionaremos ao repositório com: ```git add app.py```, faremos o commit com: ```git commit -m "add app.py"``` e publicaremos com o: ```git push -u origin Updates```. Por fim vamos aplicar as modificações da Branch Updates para master com o comando: ```git push```
