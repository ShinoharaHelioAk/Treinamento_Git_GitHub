Arquivo de Readme - 04/02/2020 (quinta-feira) 16:30:59

Comandos básicos para um bom desempenho no terminal:
- Windows                                          |  - Unix
--- cd                                             |  --- cd
--- dir                                            |  --- ls
--- mkdir                                          |  --- mkdir
--- del (remove apenas arquivos) / rmdir /S /Q
 (remove a pasta e todos os arquivos dentro dela)  |  --- rm -rf (remove a pasta e todos os arquivos dentro dela)
--- cls                                            |  --- CTRL+L
--- echo hello > hello.txt                         |  --- echo hello > hello.txt
--- cd ..                                          |  --- cd ..

openssl sha1 <file.extension>
- Comando para verificar o código sha1 de um arquivo, e suas modificações:

Objetos internos do Git
- BLOBS
--- echo 'conteudo' | git hash-object --stdin
--- echo 'conteudo' | openssl sha1
- TREES
- COMMITS


- Criando arquivos na linha de comando do Git Bash:
touch <filename>


git init
- Cria um repositório local .git a partir da pasta que você estiver.
git init --bare
- Cria um repositório que vai servir como um servidor de arquivos.

git status
- Comando para verificar o estado em que o reposítório se encontra.

*** Descartando alterações antes do "git add":
git checkout -- index.html
git checkout -- .
git restore index.html
git restore .
- Esses comandos descartam alterações feitas antes de ter sido feito o comando "git add <arquivo(s)>".
- Observação: "git checkout -- <arquivo(s)>" e "git restore <arquivo(s)>" fazem a mesma coisa.
***

git add 'ReadMe.txt'
git add .
- Adiciona arquivos no repositório local.
- Você pode discriminar os arquivos que você quer adicionar ou adicionar todos de uma vez, usando '.'.
git rm --cached <arquivo(s)> ou . para dar unstage para todos os arquivos do repositório.

*** Revertendo arquivos já adicionados para commit (git add):
git reset HEAD index.html
git restore --staged index.html
- Esses comandos revertem os efeitos do comando "git add <arquivo(s)>", mas não desfaz as alterações.
- Para desfazer as alterações, é preciso executar o comando do tópico "*** Descartando alterações antes do "git add"".
- Observação: "git reset HEAD <arquivo(s)>" e "git restore --staged <arquivo(s)>" fazem a mesma coisa.
***

git commit -m 'mensagem'
- Faz commit dos arquivos adicionados no repositório local.

git -a -m 'mensagem'
- Adiciona TODOS os arquivos no repositório local.
- Faz commit dos arquivos adicionados no repositório local.
- Duas ações no mesmo comando.

git remote add origin <url_repository_github>
- Adiciona o repositório do GitHub no repositório Git para commits no GitHub.
git remote
- Lista todos os repositórios remotos que o meu repositório local conhece.
git remote -v
- Lista todos os repositórios remotos que o meu repositório local conhece, mais o caminho deles.
git remote add local C:/Users/ALURA/Documents/git-e-github/servidor
git remote rename origin local
- Altera o nome dado a um repositório remoto.
git remote remove <name>
- Remove o repositório remoto apontado no repositório local.


git config --local user.name "Seu nome aqui"
git config --local user.email "seu@email.aqui"
git config --global
git config user.name
- Comando usado para verificar o nome cadastrado no repositório.
git config user.email
- Comando usado para verificar o e-mail cadastrado no repositório.
git config --list
- Lista todas as configurações do repositório GIT.
git config --global --unset <configuration>
- O parâmetro --unset vai retirar a configuração definida.


git push origin master
- Sobe arquivos novos ou alterados do repositório local .git para o repositório GitHub.
- Normalmente ele pede usuário e senha do GitHub.

git clone <caminho_do_repositorio_remoto> <pasta_que_sera_criada_para_guardar_o_repositorio__opcional>
- Exemplo: git clone /c/Users/ALURA/Documents/git-e-github/servidor projeto
- Comando utilizado para baixar um repositório do servidor.



Sobre a Aula 2: Branches e Merges
Arquivo de Readme - 27/10/2020 (terça-feira) 19:06:44

git branch <new branch name>
- Cria uma nova branch no repositório local .git

git checkout <branch name>
- Aponta o repositório para a branch especificada.

git checkout -b <new branch name>
- Cria uma nova branch no repositório local .git
- Aponta o repositório para a branch especificada.
- Duas ações no mesmo comando.

git branch <-d/-D> <branch_name>
- Remove uma branch do repositório. Sendo -D para --force.

git commit -m 'mensagem'

git push origin <new_branch_name>
- Sobe arquivos novos ou alterados do repositório local .git para o repositório GitHub, na branch especificada.
- Normalmente ele pede usuário e senha do GitHub.

git checkout master
git checkout teste_aula2
- Altera o apontamento da branch na qual você está trabalhando no repositório local .git .



git merge teste_aula2
- Com o git apontando para a branch master, o comando executa um merge das alterações feitas na outra branch.

git rebase titulo
- Pega os commits de uma branch criada e atualiza a branch master com os dados desses commits.
- Adicionalmente, se a branch master também tiver commits de após a branch titulo ter sido criada, esse comando faz a mescla de todos os commits da branch titulo, mais o(s) commits da branch master no log de commits.


git log --oneline
- Mostra dados de commits em apenas uma linha.
git log -p
- Mostra com mais detalhes as alterações do commit.
git log --pretty="format:%H"
- Mostra somente o hash do commit.
git log --pretty="format:%h %s"
- Mostra somente o hash reduzido e a mensagem do commit.
git log --pretty="format:%h %s %ae"
- Mostra somente o hash reduzido, a mensagem e o e-mail do autor do commit.
git log -n 2
- Mostra APENAS os 2 últimos commits.
git log --graph
- Visualiza o log de forma gráfica no terminal.



git add .
git add 'ReadMe.txt'
- Adiciona arquivos no repositório local e na branch na qual está apontada.
- Nesse caso, será na branch master.
- Você pode discriminar os arquivos que você quer adicionar ou adicionar todos de uma vez, usando '.'.

git commit -m 'mensagem'

git push origin master

- Guardando alterações (temporariamente) não adicionadas (git add) e nem comitadas no repositório:
git stash
git stash list
- Lista todos os estados não comitados salvos.
git stash apply 0
- Recupera e faz merge do estado que estava guardado na memória do repositório.
git stash drop 0
- Remove o estado da lista de stash.
git stash pop
- Retira a última alteração guardada na memória stash e aplica no projeto, já fazendo os merges.

- Viajando no tempo:
git checkout <commit_code>
- Para gerar uma nova branch com os dados desse commit, usar:
-- git checkout -b <new_branch> OU
-- git switch -c <new_branch>



...Vendo as alterações:
git diff 31eac1e..c707756
git diff <commit_code>..<other_commit_code>
- Mostra as alterações feitas a partir de um determinado commit até outro determinado commit.

git diff
- Mostra as alterações atuais do repositório, desde que essas alterações ainda não estejam adicionadas (git add <arquivo(s)>) ou comitadas (git commit -m 'mensagem').



git tag -a v0.1.0 -m 'Lançando a primeira versão (BETA) da aplicação de cursos'
- Cria uma tag de versão da aplicação.
git tag
- Lista as tags criadas.
git push local v0.1.0
- Envia as informações da tag para o servidor.
- Observação: Ao subir a tag gerada para o repositório do Github, ela será apresentada na guia "Releases".


--Conteúdo Adicional
