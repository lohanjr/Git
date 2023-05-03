# Aprendendo a utilizar o Git/GitHub :)

Olá, irei colocar aqui alguns comandinhos e atalhos como dicas que venho aprendendo.

A lógica que iremos seguir será, estabelecer ua conexão entre seu repositório local ao remoto do _Github.com_! Para nos possibilitar segurança e versionamentos(alterações individuais ou em equipe) ao desenvolver o projeto.

- PS: Vou me basear na situação em que você já possui o(s) arquivo(s) do seu projeto salvo no seu dispositivo...

## Criando um novo repositório...

* Dê um `Git Bash Here` na pasta pai em que seus arquivos se encontram, o terminal irá se abrir já no caminho correto.

* Dê um `git init`, para assim, inicializarmos um repositório vazio. O interessante é que se, no _Explorador de Arquivos_ clicarmos na opção "Vizualizar > Itens Ocultos". Poderemos ver que uma pasta oculta foi adicionada, com nome: <b>.git</b>
- PS: Ela será responsável pela conexão, não a modifique.

* Com o comando `git status`, poderemos ver a situação atual da configuração, nesse momento, irá aparecer os arquivos filhos presentes na pasta, com a situação: "Untracked" ou 'Não Rastreado', pois ainda não os adicionamos.

* Iremos fazer esse passo, com o comando `git add <your_file>`, caso haja mais de uma pasta de arquivo, insira o nome da primeira e dê um espaço e assim sucessivamente, até chegar ao final.