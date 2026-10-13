link: udemy.com/course/git-e-github-ninja/

# Curso git e github ninja

# Seção 1

## Introdução

`git --version` -> Mostra a versão do git

`git` -> Lista todos os comandos que dá pra fazer com git.

`ls -la` -> Verificar o que tem dentro do diretório

`clear` -> Limpar a tela

`git init` -> Iniciar repositório

`git status` -> Verifica o status da minha árvore do git atual. Mostra o status atual, controle de versão.

## Adicionando arquivos e fazendo as configurações iniciais do git

`3 Estágios do git` -> Working Directory, Staging Area e .git directory

`git add` -> Adiciona arquivos para o staging area

`git config --global user.name` -> Configura o meu nome na hora de fazer o commit

`git config --global user.email` -> Configura o meu e-mail na hora de fazer o commit

`git config --list` -> Listar todas as configurações que eu setei do git.

`git commit` -> Marcamos um ponto na linha do tempo, onde salvo o código a partir daí. É como se fosse um save em um jogo.

`working directory` -> É onde trabalhamos no código. Ou seja, tenho arquivos não commitados. Posso estar alterando arquivos, criando novos arquivos ou removendo arquivos. 

`staging area` -> É quando eu adiciono para o git add, ou seja, não estou mais trabalhando nele. Acabo limpando o working directory. Untracked files são arquivos que não estão na staging area.

`git directory` -> É onde fica os commits. Quando dou git commit, ele fica nessa parte.

## git log

`git log` -> Mostra uma lista de todos os commits que foram feito dentro de diretório, seja ele meu ou de outras pessoas que trabalharam no mesmo projeto.
Ele vai te dar uma hash do meu commit, vai mostrar o nome da pessoa, o e-mail e a data.

`git diff` -> Com esse comando, consigo visualizar as alterações que fiz no meu arquivo.

Esses comandos, sao comandos básicos do git. Pratique bastante.

## Trabalhando com mais arquivos.

`git add .` -> Adiciona todos os arquivos de uma só vez para o staging area.

`git diff --staged` -> Verifica todas as alterações que estão no staging area comparando com o que está no git directory.

`git diff <nome do arquivo>` -> Serve para visualizar a alteração do arquivo específico.

## Voltando no tempo - Diff de commits

`git log --name-status` -> Consigo visualizar o nome dos arquivos que foram alterados. Consigo ver quando que eles foram adicionados, modificados ou deletados.

`git diff <commit1 commit2>` -> Dando esse comando, o git vai fazer uma comparação entre esses dois commits. Para isso preciso pegar a hash de cada commit.

`git rm` -> Remove o arquivo da árvore no diretório do git.

# Seção 2

## Adicionar arquivos

`git add --all ou git add -A` -> Todas as ações que estiver no nosso working directory, ele vai adicionar para a árvore do git. Se tiver arquivos novos, modificados ou deletados, todos serão adicionados.

## .gitignore

O gitignore serve basicamente para ignorar alguns arquivos no meu repositório.
Tenho arquivos que não quero commitar, mas preciso deles no meu projeto.
Então pego os arquivos e coloco eles no gitignore.
Esse é caso do node_modules. Ele tem vários arquivos e vai acabar deixando meu projeto muito grande caso eu subir para o repositório remoto. Para o git, esse node_modules deve ser ignorado.

## .gitignore - Parte 2

O que foi mostrado nessa aula: Posso remover arquivos da árvore do git ou adicionar arquivos que estão na staging area.

`git rm -rf <nome do arquivo>  --cached` -> Com esse parâmetro --cached, ele vai fazer a remoção do git, removendo a node_modules voltando pra untracked, só que não remove ela do meu arquivo original. 
Esse comando é bem interessante, porque consigo remover a node_modules que estava na staging area, só que não quero remover do próprio diretório. Assim não deixa ele remover do meu local.

## .gitignore - Parte 3

*O git trabalha com modificações de forma completamente separada.*

`git commit -am "Mensagem"` -> Aqui eu pulo a parte de git add . e já vai para o .git directory. *Devo tomar cuidado porque posso ter informações que posso não querer adicionar e acabar adicionando informação a mais. Sempre dar um git status para verificar o que está acontecendo no meu working directory.*

`git config core.excludesfile ~/.gitignore` -> Configurar o .gitignore para todos os projetos instalados na máquina. *Mas esse tipo de configuração só vai funcionar em linux ou mac. Para windows preciso pesquisar.*

## Commit sem parâmetros

`git commit` -> Dando o git commit sem mensagem, posso escrever e detalhando melhor a mensagem. Ele vai abrir o editor de texto que está configurado no git.
Porém, precisa configurar o git para aparecer no vscode. Olhar a aula caso esqueça as configurações.

`git config core.editor` -> Editar o editor de código a sua escolha, caso você não deseja o vim.

`git config core.editor code` -> Colocar o vscode na hora de abrir com git commit.

## git log

`git log --pretty=oneline` -> Mostra o histórico de commits em uma única linha.

`git log --abbrev-commit` -> Vai abreviar a mensagem de commit.

Posso juntar os dois parâmetros se quiser para ver o git log: `git log --pretty=oneline --abbrev-commit`

`git log --stat` -> Com esse parâmetro, ele vai dar estatisticas de cada commit.

`git log -p` -> Ele mostra a alteração que foi feita no arquivo.

`git log -p -3` -> Mostra a alteração que foi feita nos três últimos commits.
Não preciso ver todos os commits. Posso colocar números se necessário.

# Seção 3

## git branch(Ramificação)

`git branch` -> Mostra a lista que tenho de branch no meu projeto.

Uma branch serve para um propósito específico. 
Quando eu preciso criar alguma nova feature no meu projeto exemplo, eu crio essa feature para modificar o que quero. 
Quero criar o header da minha aplicação. Então vou e crio uma branch para o header.
Crio um ambiente separado do meu ambiente principal(branch main ou master(Atualmente é main.))

`git branch <nome da branch>` -> Crio uma branch

*Branches são criadas com base na branch atual.*

`git checkout <nome da branch>` -> Acesso a branch

Reforçando: Cada branch tem um ambiente separado de produção.

## git branch - parte 2

`git merge <nome da branch>` -> Estando na branch main ou master, dou esse comando para unir as alterações feitas em outras branchs. Posso unir o CSS com o HTML que fiz.

*É sempre importante nunca trabalhar na branch principal(master ou main).*

Mesmo trabalhando com várias pessoas ou sozinho, é interessante eu manter essa separação das branchs e fazer com que cada branch seja uma feature que vou adicionando ao longo do projeto.
Assim consigo manter a branch main com o conteúdo mais atualizado possível.

*A branch main é a branch principal do meu projeto.*

Crie uma branch para desenvolvimento antes de colocar tudo na branch master.

## git branch - parte 3

`git checkout -b <nome da branch>` Crio e acesso a branch ao mesmo tempo. *É o comando mais utilizado no dia a dia.*

`git branch -m <nome da branch>` -> Serve para renomear a branch

`git branch -D <nome da branch>` -> Serve para remover uma branch

*Só toma cuidado para não se perder nas branchs. Crie um workflow da forma como eu achar melhor. Treine bem os comandos de branchs.*

`git checkout --orphan <nome da branch>` -> Consigo criar branchs vazias com esse comando
Branchs criadas a partir do orphan, não são compartilhadas do histórico de outras branchs.

## Criando repositórios

Ter um repositório para que? Para que outras pessoas possam colaborar com o meu projeto.

`git init --bare` -> Com esse comando, crio um repositório no git.

`git remote add <origin> <repository>` -> Serve para linkar o repositório local com o remoto.

`git remove -v` -> Serve para verificar quais são os repositórios que estão listados ou que são criados no nosso projeto. 

## Sincronizando ambiente local com o repositório

`git push <origin> <branch>` -> Serve para linkar o repositório local com o remoto

PAREI NO VÍDEO 3:44