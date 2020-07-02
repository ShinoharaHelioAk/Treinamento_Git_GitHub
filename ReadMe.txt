Arquivo de Readme - 02/07/2020 (quinta-feira) 14:22:50

git init
- Cria um repositório local .git a partir da pasta que você estiver.

git add 'ReadMe.txt'
git add .
- Adiciona arquivos no repositório local.
- Você pode discriminar os arquivos que você quer adicionar ou adicionar todos de uma vez, usando '.'.

git commit -m 'mensagem'
- Faz commit dos arquivos adicionados no repositório local.

git remote add origin <url_repository_github>
- Adiciona o repositório do GitHub no repositório Git para commits no GitHub.

git push origin master
- Sobe arquivos novos ou alterados do repositório local .git para o repositório GitHub.
- Normalmente ele pede usuário e senha do GitHub.



Sobre a Aula 2: Branches e Merges
Arquivo de Readme - 02/07/2020 (quinta-feira) 16:01:29

git checkout -b <new branch name>
- Cria uma nova branch no repositório local .git

git commit -m 'mensagem'

git push origin <new_branch_name>
- Sobe arquivos novos ou alterados do repositório local .git para o repositório GitHub, na branch especificada.
- Normalmente ele pede usuário e senha do GitHub.

git checkout master
git checkout teste_aula2
- Altera o apontamento da branch na qual você está trabalhando no repositório local .git .







