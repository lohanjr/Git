# Aprendendo a utilizar o Git/GitHub :)

Olá, irei colocar aqui alguns comandinhos, atalhos e dicas🤩 do que venho aprendendo com o Git.

A lógica que iremos seguir, será estabelecer uma conexão entre seu repositório local ao remoto do _Github.com_! Para nos possibilitar segurança, facilidade e versionamentos(alterações individuais ou em equipe) ao desenvolver o projeto.

> _PS: Vou me basear na situação em que você já possui o(s) arquivo(s) do seu projeto salvo no seu dispositivo..._

## - Criando um novo repositório

* Escolha um diretório em sua pasta de arquivos, onde você irá criar seu novo repositório.</br>Já dentro dela, clique com o botão direito e dê um `Git Bash Here` na pasta pai em que seus arquivos se encontram, o terminal irá se abrir já no caminho correto.

* Use o comando:
```
git init
```
Iniciando assim, um repositório vazio. O interessante é que se, no _Explorador de Arquivos_ clicarmos na opção "Vizualizar > Itens Ocultos". Poderemos ver que uma pasta oculta foi adicionada, com nome: <b>.git</b>
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

* Agora, basta fazermos o envio de fato, utilizando `git push -u origin main`. O _'-u'_ siginifica _upstream_, indica que, futuras mudanças necessitarão apenas do _git push_ para enviar as alterações locais para o repositório remoto.

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
Para isso, temos uma descrição detalhada do histórico de commits, quem o comitou e quando foi feita a alteração.

* Usaremos o comando `git log` para isso.

![git log no bash](./imgs/gitLogNoBash.png)

Assim, temos um controle amplo sobre o projeto.