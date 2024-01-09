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
E iremos utilizar os comandos que foram contornados em verde, para concluirmos a conexão e envio de arquivos.

## Escolhendo o diretório

Vamos agora, para a área de trabalho, para termos um ambiente visualmente limpo para iniciarmos.

![link do repositório](imgs/openingGitBashCommandLine.png)

* Use o botão direito do mouse e clique em _Git Bash Here_, a linha de comando então será aberta. Agora, você terá que escolher ou criar uma pasta, onde iremos criar nossos arquivos e dar ínicio ao repositório local.

![link do repositório](imgs/fileManagerPath.png)

* Após decidir o diretório, basta copiar o caminho e colá-lo no Git Bash, com o comando:
```bash
cd "C:\gitExemplo"
```

![link do repositório](imgs/changingDirectoryBash.png)

> `pwd` nos mostra em qual caminho nos encontramos no momento

> `code .` abre o diretório em que estamos no Visual Studio Code

Note que o meu caminho será C:\gitExemplo, basta substituir pelo seu!

## Iniciando repositório git

* De volta ao console do Bash, iremos dividir a tela com o Explorador de Arquivos, ambos programas no mesmo caminho, para visualizarmos o que irá acontecer. 

![error not a git repository](imgs/errorNotAgitRepository.png)

> No Explorador de Arquivos, clique na opção "Vizualizar > Itens Ocultos"

No Bash, dê um:

```bash
git status
```

Com esse comando, recebemos o feedback do status geral do repositório, informações como: status de arquivos adicionados, branch atual etc.</br>E podemos ver na resposta grifada em amarelo, que o diretório ainda não é um repositório git.</br>Agora, iremos criar de fato o repositório, com o comando:

```bash
git init
```

Para assim, inicializarmos um repositório vazio.

![git init](imgs/gitInit.png)

* O interessante é que após esse comando, poderemos ver grifada em amarelo, que uma pasta oculta foi adicionada, com nome: <b>.git</b>
> _PS: Ela será responsável pela conexão, não a modifique._

## Criando os primeiros arquivos

Iremos agora, clicar em _New File..._ e escolher um nome para o arquivo e o tipo do arquivo, que no caso, será _.md_ 

![creating new file vs code](imgs/givingAnameToTheNewFile.png)

O nome que irei escolher será o padrão para esse tipo de arquivo, _README.md_.

> Perceba que ao nomear o arquivo, no _Explorar de Arquivos_ já irá aparecer o arquivo. 

Agora, iremos escrever um texto dentro desse MarkDown (md):

![adding content](imgs/addingFirstContentToTheFile.png)

Perceba que está aparecendo a letra em verde _U_, ela significa que o arquivo se encontra _Untracked_ ou "Não Rastreado", pois ainda não o adicionamos.

* Para isso, iremos utilizar o seguinte comando no Bash: 

```bash
git add filename
```

> O _filename_ no caso, é _README.md_, basta substituir.

* Agora, iremos usar o atalho: _Ctrl + L_ para limpar o console e em seguida, vamos adicionar os arquivos.

![git add readme](imgs/gitAddReadme.png)

---
### Dicas `git add`:

Caso haja mais de um arquivo, e você queira adicionar todos, use o comando:

```bash
git add .
```

Caso tenha vários arquivos mas você queira adicionar somente algum deles, insira o nome dos respectivos arquivos um por um, separados por espaço, até chegar ao último arquivo.

```bash
git add filenameone filenametwo filenamethree
```

---

* Após isso, os arquivos adicionados entram em um modo de _"standing"_, sendo similar à uma sala de espera, apenas aguardando serem chamados para o _commit_.</br>E, usando no Bash, o comando:

```bash
git commit -m "meu primeiro commit aprendendo git" 
```

![git add readme](imgs/gitCommit.png)

Sendo assim, salvo as alterações <b>localmente!</b> O _"-m"_ serve para adicionarmos uma descrição _"message"_ do que está sendo feito e(ou) alterado.

* Agora iremos nos atentar à nomenclatura do repositório.</br>Vemos no final do caminho de arquivos, o termo em parênteses "(master)", isso significa que, o ramo principal do projeto ou _branch_, está nomeada como 'master', como padrão, mas isso vem sendo mudado por X questões que você pode posteriormente se aprofundar caso queira.</br>Portanto, usaremos o comando:
 
```bash
git branch -M main
```

![git branch -M main](imgs/gitBranch-Mmain.png)

Perceba que, aonde está circulado em vermelho, vemos que o nome da branch foi alterada.

> O comando `git branch` é usado para sabermos em qual branch nos encontramos

* Agora, iremos voltar à página do GitHub e copiar a URL do repositório (basta substituir pela sua), pois precisamos indicar o caminho do diretório para a conexão remota.</br>Para isso, vamos utilizar, no Bash, o comando:

```bash
git remote add origin https://github.com/lohanjr/gitExemplo.git
```

> Para colar a URL no terminal, use _shift+Insert._

* Agora, basta fazermos o _push_.

```bash
git push -u origin main
```

![git branch -M main](imgs/gitPush-uOriginMain.png)


O _-u_ siginifica _upstream_, indica que, futuras mudanças necessitarão apenas do _git push_ para enviar as alterações locais para o repositório remoto.

Com isso, temos o primeiro commit aplicado com **sucesso!!**

## - Modificando e Atualizando
Iremos agora nos aprofundar nas técnicas de alteração de código. O estágio em que passamos mais tempo...

Considere que após alguns dias, você queira adicionar algum conteúdo ao seu projeto, para isso, devemos então seguir alguns passos. Como não sei os arquivos que você possa ter subido ao seu repositório, irei criar o seguinte exemplo:

![touch index e readme](imgs/criaçãoDeIndex_Readme.png)

Acima, criei 2 arquivos, um 'index.html' e um 'readme.md', ambos sem nada escrito. Perceba que existe um _U_ maiúsculo. Isso acontece pois estão "_Untracked_" ou não encontrados. Como podemos ver abaixo no GitBash também.

![untracked files](imgs/gitBashUntrackedFiles.png)

> `git status` nos dá as informações gerais desse repositório.

- Para adicionarmos ao _stading_, iremos usar o comando `git add .`
- Após isso, iremos comitar com uma frase descritiva `git commit -m "adição de arquivos html e readme"`
- Agora, basta aplicarmos o `git push origin main` para enviarmos as mudanças para o repositório remoto.

![add commit e push](imgs/first_addCommit_e_Push.png)

**Prontinho!** Atualize (F5) sua página do GitHub para ver a atualização.

## - Alterações de arquivo | `git diff`

### - Saved but not Staged

Quando salvamos remotamente um arquivo na nuvem, com o comando `push`, e posteriormente quisermos alterá-lo, podemos notar algumas informações do que foi, de fato, alterado.<br>Digamos que eu adicione o esqueleto padrão HTML com o atalho: _! + tab_.

![git diff](./imgs/ideIndex!.png)

> O '_M_' significa _modified_, agora vamos usar o comando no Git Bash.

Para visualizar as alterações, temos o comando:
```
git diff index.html
```
Que nos mostra o que foi mudado _"pré-commit"_ ou antes do staged (isso é importante!)<br>

![cmd git diff content](./imgs/cmdDiffImage.png)

Conseguimos visualizar todo o conteúdo alterado pela linha de comando, super explicativo.

> Para a próxima explicação, leve em conta que irei comitar e dar push à essa modificação.

### *Staged*

Ao alterar o arquivo e usar o comando `git add`, o arquivo se encontrará na área de stading. E o comando para compararmos as mudanças será um pouco diferente.

Irei adicionar um título h1 ao meu body:

![git diff -r HEAD](./imgs/gitDiff-rHEAD.png)

Basta usarmos o comando a seguir para identificarmos as mudanças no arquivo index.html, caso o seu arquivo tenha um nome diferente, basta colocá-lo no lugar.

```
git diff -r HEAD index.html
```

Temos então o mesmo resultado mostrado na command line.

![git log no bash](./imgs/gitDiff-rHEADcommandLine.png)

## - Histórico de commits e seus autores | `git log`

Quando falamos em ambientes de versionamento, o trabalho em equipe está incluso nisso, e para boas práticas de desenvolvimento de projetos, temos que manter um ambiente de codificação organizado.<br>
Com o uso desse comando, temos uma descrição detalhada do histórico de commits.

* Usaremos o comando `git log` para isso. Mostrando assim, todos os commits feitos no repositório, em ordem cornológica, começando pelo mais antigo. Nos mostra o commit hash, o autor, a data e a mensagem do commit.

![git log no bash](./imgs/gitLogNoBash.png)

Assim, temos um controle amplo sobre o projeto.