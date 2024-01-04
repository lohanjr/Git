# Aprendendo a utilizar o Git/GitHub :)

Olá, irei colocar aqui alguns comandinhos, atalhos e dicas🤩 do que venho aprendendo com o Git.

A lógica que iremos seguir, será estabelecer uma conexão entre seu repositório local ao remoto do _Github.com_! Para nos possibilitar segurança, facilidade e versionamentos(alterações individuais ou em equipe) ao desenvolver o projeto.

> _PS: Vou me basear na situação em que você irá criar um repositório novo, um que não tenha arquivos..._

## - Criando um novo repositório

* Ao acessar sua conta do GitHub, na página inicial, você irá clicar no botão _New._

![tela inicial GitHub](imgs/gitHubHomePage.png)

* Após isso, você terá que nomear o seu novo repositório e, caso queira, adicionar uma descrição a ele.

![tela de criação de repo git](imgs/repositorioGitExemplo.png)

> Não iremos marcar a opção de _Add a README file_ agora, pois iremos abordar esse assunto posteriormente.

Sendo assim, já criamos o repositório remoto no servidor do GitHub, basta conectarmos os arquivos que iremos criar na nossa máquina a ele. E para fazer isso, vamos utilizar a linha de comandos Git Bash e seguir alguns passos que o GitHub nos fornece.

![link do repositório](imgs/RemotePartGrifado.png)

O link grifado em vermelho, é o URL do repositório Git remoto no GitHub, que é usada para fazermos a conexão entre o local e remoto, sendo super importante.</br>
E iremos utilizar os comandos que foram contornados em verde, para conluirmos a conexão e envio de arquivos.</br>Vamos agora, para a área de trabalho, para termos um ambiente visualmente limpo para iniciarmos.

![link do repositório](imgs/openingGitBashCommandLine.png)

* Use o botão direito do mouse e clique em _Git Bash Here_, a linha de comando então será aberta. Agora, você terá que escolher ou criar uma pasta, onde iremos criar nossos arquivos e dar ínicio ao repositório local.

![link do repositório](imgs/fileManagerPath.png)

* Após decidir o diretório, basta copiar o caminho e colá-lo no Git Bash, com o comando:
```bash
cd "C:\Lohan\Estudo\gitExemplo"
```

![link do repositório](imgs/changingDirectoryBash.png)

> `pwd` nos mostra em qual caminho nos encontramos no momento

Note que o meu caminho será C:\Lohan\Estudo\gitExemplo, basta substituir pelo seu!



<!-- * Dê um `git init`, para assim, inicializarmos um repositório vazio. O interessante é que se, no _Explorador de Arquivos_ clicarmos na opção "Vizualizar > Itens Ocultos". Poderemos ver que uma pasta oculta foi adicionada, com nome: <b>.git</b>
> _PS: Ela será responsável pela conexão, não a modifique._

* Com o comando
```
git status
```
Poderemos ver a situação atual da configuração, nesse momento, irá aparecer os arquivos filhos presentes na pasta, com a situação: "Untracked" ou 'Não Rastreado', pois ainda não os adicionamos.

* Iremos fazer esse passo, com o comando: 
```
git add filename
```
Caso haja mais de um arquivo, e você queira adicionar todos, use o comando:
```
git add .
```
Caso tenha vários arquivos mas você queira adicionar somente algum deles, insira o nome dos respectivos arquivos um por um, separados por espaço, até chegar ao último arquivo.
```
git add filenameone filenametwo filenamethree
```

* Após isso, os arquivos adicionados entram em um modo de _"standing"_, sendo similar à uma sala de espera, apenas aguardando ser chamado, veremos o responsável por essa ação é o `git commit -m "here goes the title of your commit"`, sendo assim salva as alterações *localmente*, o _"-m"_ serve para adicionarmos um título/descricção do que está sendo feito e(ou) alterado.

*  Agora iremos nos atentar à nomenclatura do repositório. Podemos perceber no final do caminho de arquivos, o termo em parênteses "(master)", isso significa que, o ramo principal do projeto ou _branch_, está nomeada como 'master', como padrão, mas isso vem sendo mudado por X questões que você pode posteriormente se aprofundar caso queira. Portanto, usaremos o comando `git branch -M "main"`

Agora precisamos criar um novo repositório em seu perfil do GitHub por algum navegador, no caminho: https://github.com/yourGitHubUserName?tab=repositories, basta você adicionar seu nome neste lugar: _"yourGitHubUserName"_, no botão verde *NOVO*.

Após isso, teremos:
![tela de criação de repo git](imgs/repositorioGitExemplo.png)

Como podemos ver, devemos criar um repositório dessa forma.

Então chegaremos ao próximo passo:
![link do repositório](imgs/RemotePartGrifado.png)

Sendo assim, podemos avançar a próxima etapa.

> _PS: Se atente ao link grifado em vermelho._

* Com o link copiado, iremos novamente abrir o Git Bash e utilizar o código `git remote add origin https://github.com/lohanjr/GitExemplo.git`, esse comando irá indicar o caminho do seu diretório para a conexão remota, como o nome já diz.

> _PS: Para copiar a URL, use shift+insert ou dê 'right click' e depois clique na opção 'colar'._

* Agora, basta fazermos o envio de fato, utilizando `git push -u origin main`. O _'-u'_ siginifica _upstream_, indica que, futuras mudanças necessitaram apenas do _git push_ para enviar as alterações locais para o repositório remoto.

Com isso, temos o primeiro commit aplicado com **sucesso!!** --!>