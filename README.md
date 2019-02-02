## Dicas de Git

git reset: É usado para branchs separadas, pois evita commits sujos, porém, com isso, é perdido o histórico de rastreio do Git.

git revert: É usado para casos em que é desejado que se mantenha o histórico de rastreio do git, ele cria um commit de revert, assim, mantendo o histórico de rastreio.

git commit --amend: É ótimo alterações em nomes de commits, em casos criamos commits com nomes errados e queremos edita-lo. e também que inserir arquvios ou alterações em um commit anterior (Casos em que esquecemos algum arquivo no commit) !!IMPORTANTE: Em casos de alerações enviadas para o repositório na nuvem, seja ele qual for, devemos usas outras estratégias.

git cherry-pick ${hash-commit}: É ótimo para pegar apenas alguma alteração específica, pegar apenas alterações de um commit ao invés de fazer merge uma branch inteira só para isso.

git add -p: É usado para escolher trechos de um arquvios em que queremos jogar para o stage area, ou seja, permite que seja enviado para o stage area apenas trechos específicos de um mesmo arquivo, ao invés do arquivo inteiro. depois que esse comando é executado, são exibidas as seguintes opções para cada trecho modificado:

y: Adicionar.
n:Não adicionar.
q:Não adicionar e sair imediatamente do menu de opções.
a: Adicionar o que está sendo exibido para ser feito a escolha e todos os outros posteriores.
d:Não adicionar o trecho de código (modificado) que está sendo exibido e nem outros, igual a opção "q", porém, não sai imediamente.
j:Passar para o próximo trecho de código (modificado).
g:Passar para o trecho anterior de código (modificado).
s:Dividir trechos de código em partes (Dividindo por linha).
e:Adicionar manualmente.

git rebase -i HEAD~{numero-commits-deseja-ver}: Ao executar esse comando, é listado as seguintes opções:
p:pick = use commit.
r:rework = use commit, but edit the commit message.
e:edit = use commit, but stop for amending.
f:fixup = like "squash", but discards this commit's log message.
x:exec = run command (the rest of the line) using shell.
d:drop = remove commit.

git reset --hard origin/master: Reseta todos os commits local até o commit da master na nuvem, ou seja, descarta todos os commits locais em relação a branch na nuvem.

git commit --fixup {hash-commit}: Serve para fazer commits corretivos, assim que for feito todos os commits corretivos, é usado o seguinte comando. OBS: o hash do commit deve ser o commit no qual se deseja ser feita o ommit corretivo.

git rebase -i --autosquash {hash-commit}: Serve para juntar todos os commits corretivos. É importante destatacar que o hash deve ser do commit anterior de que se deseja ser feita a correção.

git pull origin {branch} --rebase: Serve para resolver os conflitos com o repositório em nuvem.

git merge --continue ou git merge --continue: Após corrigir os conflitos, salvar e jogar arquivos com confilots para o stage area, deverá ser executado esse comando para seja feito o merge.

 git config --global help.autocorrect 1: Serve para configurar o git para quando for feito algum comando com errado, por exemplo "git startus", será executado automaticamente um comando parecido, no caso seria "git status".

 git archive {branch} --format={format} --output={nome-arquivo-saida}: Serve para transformar todos os arquivos de uma branch para um arquivo zipado, é usado para casos onde se deseja disponibilizar um projeto com git, mas algumas pessoas não sabem como usa-lo

 ['git log --pretty=oneline',
 'git log --pretty=oneline --graph',
 'git log --pretty=oneline --graph --all'
 ] São comandos usados para ter um saída mais personificada depdendendo da necessidade para ver o log dos commits.

 git log --since='{data-commit}': Serve para ver todos os commits desde aquela data, todos os anteriores serão ignorados. Exemplo de como por uma data:'Jan 1 2019'.

 git log --until='{data-commit}': Serve para ver todos os commits até aquela data, todos os posteriores serão ignorados. Exemplo de como por uma data:'Jan 1 2019'.

 git log --until='{data-commit}' --since='{data-commit}': Os dois comandos acima podem ser usados em conjunto, para criar um intervalo de tempo por exemplo, um início e fim de como será o filtro baseado nas datas colocadas por parâmetro.

 git log --author='{nome-author}': Serve para filtrar todos os commits por Author.

git shortlog: Serve para ter uma saída simplificada dos logs, mostrando apenas o author, números de commits e as mensagens de commits mais recentes.

git shortlog -sn: Também é uma forma simplificada  dos logs, mostrando apenas o nome de cada author e o número total de commits, respectivamente.

git log -3: Traz apenas os 3 últimos commits feitos.



https://git-scm.com/docs/git-log: Conteúdo para ter mais detalhes sobre os comandos para ver o log.


git reflog: Serve para ver um log mais profundo, vendo os merges, resets, reverts, cherry-pick, git-checkout. E com isso, podemos fazer algo muito útil, por exemplo, recuperar commits perdidos com o comando git reset --hard. Mais detalhes sobre esse comando em https://git-scm.com/docs/git-reflog




