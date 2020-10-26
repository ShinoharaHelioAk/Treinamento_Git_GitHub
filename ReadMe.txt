Arquivo de Readme - 26/10/2020 (segunda-feira) 16:23:50
Arquivo de Readme - 02/07/2020 (quinta-feira) 14:22:50

git init
- Cria um repositório local .git a partir da pasta que você estiver.

git add 'ReadMe.txt'
git add .
- Adiciona arquivos no repositório local.
- Você pode discriminar os arquivos que você quer adicionar ou adicionar todos de uma vez, usando '.'.

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

git push origin master
- Sobe arquivos novos ou alterados do repositório local .git para o repositório GitHub.
- Normalmente ele pede usuário e senha do GitHub.

git clone <caminho_do_repositorio_remoto> <pasta_que_sera_criada_para_guardar_o_repositorio__opcional>
- Exemplo: git clone /c/Users/ALURA/Documents/git-e-github/servidor projeto
- Comando utilizado para baixar um repositório do servidor.



Sobre a Aula 2: Branches e Merges
Arquivo de Readme - 26/10/2020 (segunda-feira) 17:02:55
Arquivo de Readme - 02/07/2020 (quinta-feira) 16:01:29

git branch <new branch name>
- Cria uma nova branch no repositório local .git

git checkout <branch name>
- Aponta o repositório para a branch especificada.

git checkout -b <new branch name>
- Cria uma nova branch no repositório local .git
- Aponta o repositório para a branch especificada.
- Duas ações no mesmo comando.

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

git log --graph
- Visualiza o log de forma gráfica no terminal.



git add .
git add 'ReadMe.txt'
- Adiciona arquivos no repositório local e na branch na qual está apontada.
- Nesse caso, será na branch master.
- Você pode discriminar os arquivos que você quer adicionar ou adicionar todos de uma vez, usando '.'.

git commit -m 'mensagem'

git push origin master

--Conteúdo Adicional
