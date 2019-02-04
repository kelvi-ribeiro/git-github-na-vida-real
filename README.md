# Dicas de Git
Esse projeto tem como objetivo ajudar com alguns comandos mais complexos do git e também servir como espécie de sumário, o Curso [Git e Github na Vida Real](https://www.udemy.com/git-e-github-na-vida-real/) foi usado na construção desse projeto, usando boas práticas e todos os comandos listados, fora os workflows do Git, como resolver alguns problemas no Github e etc.

## Comandos mais usados 

| O que faz ? | Comando |
|------| ------ |
|É usado para branchs separadas, pois evita commits sujos, porém, com isso, é perdido o histórico de rastreio do Git. | `git reset`|  
| É usado para casos em que é desejado que se mantenha o histórico de rastreio do git, ele cria um commit de revert, assim, mantendo o histórico de rastreio. | `git revert` |
| É ótimo alterações em nomes de commits, em casos criamos commits com nomes errados e queremos edita-lo. e também que inserir arquvios ou alterações em um commit anterior (Casos em que esquecemos algum arquivo no commit) !!IMPORTANTE: Em casos de alerações enviadas para o repositório na nuvem, seja ele qual for, devemos usas outras estratégias. | `git commit --amend` |
| É ótimo para pegar apenas alguma alteração específica, pegar apenas alterações de um commit ao invés de fazer merge uma branch inteira só para isso. | `git cherry-pick ${hash-commit}` |
| É usado para escolher trechos de um arquivo em que queremos jogar para o stage area, ou seja, permite que seja enviado para o stage area apenas trechos específicos de um mesmo arquivo, ao invés do arquivo inteiro. Depois que esse comando é executado, são exibidas algumas opções que ficará numa tabela específica logo abaixo | `git add -p`  |
| Faz um rabase interativo passando o número de commits que se deseja como parâmetro e então é exibido algumas opções que terá uma tabela específica logo abaixo. |  `git rebase -i HEAD~{numero-commits-deseja-ver}` |  
| Reseta todos os commits local até o commit da master na nuvem, ou seja, descarta todos os commits locais em relação a branch na nuvem. | `git reset --hard origin/master`
| Serve para fazer commits corretivos, assim que for feito todos os commits corretivos, é usado o seguinte comando. OBS: o hash do commit deve ser o commit no qual se deseja ser feita o commit corretivo. | `git commit --fixup {hash-commit}` |
| Serve para juntar todos os commits corretivos. É importante destatacar que o hash deve ser do commit anterior de que se deseja ser feita a correção. | `git rebase -i --autosquash {hash-commit}` |
 | Serve para resolver os conflitos com o repositório em nuvem. | `git pull origin {branch} --rebase` |
 | Após corrigir os conflitos, salvar e jogar arquivos com confilots para o stage area, deverá ser executado esse comando para seja feito o merge. | `git merge --continue` |
 | Serve para configurar o git para quando for feito algum comando com errado, por exemplo "git startus", será executado automaticamente um comando parecido, no caso seria "git status". | `git config --global help.autocorrect 1` |
 | Serve para transformar todos os arquivos de uma branch para um arquivo zipado, é usado para casos onde se deseja disponibilizar um projeto com git, mas algumas pessoas não sabem como usa-lo | `git archive {branch} --format={format} --output={nome-arquivo-saida}` |
| Serve para ver um log mais profundo, vendo os merges, resets, reverts, cherry-pick, git-checkout. E com isso, podemos fazer algo muito útil, por exemplo, recuperar commits perdidos com o comando `git reset --hard` | `git reflog` |
| Comando para após uma criação e finalização de um release, enviar para o repositório em nuvem. | `git push origin master --tags ` |

## Opções do comando `git add -p`

| Opção | Descrição |
| --- | ------- |
| y | Adicionar |
| n | Não adicionar |
| q | Não adicionar e sair imediatamente do menu de opções | 
| a | Adicionar o que está sendo exibido para ser feito a escolha e todos os outros posteriores |
| d | Não adicionar o trecho de código (modificado) que está sendo exibido e nem outros, igual a opção "q", porém, não sai imediamente |
| j | Passar para o próximo trecho de código (modificado)
| g | Passar para o trecho anterior de código (modificado) |
| s | Dividir trechos de código em partes (Dividindo por linha) |
| e | Adicionar manualmente |

## Opções do comando `git rebase -i HEAD~{numero-commits-deseja-ver}`
| Opção | Descrição |
| ----- | ----------|
| p: pick | Usar commit |
| r: rework | Usar commit, mas editar a mensagem do commit
| e: edit | Usar, mas altera-lo com "amending"
| f: fixup | Parecido o  "squash", mas descarta a mensagem do commit
| x: exec | Executar comando (o resto da linha) usando shell
| d: drop | Remover commit |

## Comandos de filtro de log

| Ação | Comando |
| ------- | ---- |
| Exibe um log mais simplificado, contendo apenas o hash do commit e a mensagem do commit. | `git log --pretty=oneline` |
| Além de exibir o hash e a mensagem do commit como no comando `git log --pretty=oneline`, exibe um pequeno de o que foi feito em relação as branch atual.  | `git log --pretty=oneline --graph` |
| Parecido com o comando `git log --pretty=oneline --graph`, com exceção que exibirá a relação de todas as branchs. | `git log --pretty=oneline --graph --all` |
| Serve para ver todos os commits desde aquela data, todos os anteriores serão ignorados. Exemplo de como por uma data:'Jan 1 2019'. | `git log --since='{data-commit}'`
| Serve para ver todos os commits até aquela data, todos os posteriores serão ignorados. Exemplo de como por uma data:'Jan 1 2019'. | `git log --until='{data-commit}'` |
| Os dois comandos acima podem ser usados em conjunto, para criar um intervalo de tempo por exemplo, um início e fim de como será o filtro baseado nas datas colocadas por parâmetro | `git log --until='{data-commit}' --since='{data-commit}'` | 
| Serve para filtrar todos os commits por Autor | `git log --author='{nome-autor}'`
| Serve para ter uma saída simplificada dos logs, mostrando apenas o author, números de commits e as mensagens de commits mais recentes. | `git shortlog` |
| Também é uma forma simplificada  dos logs, mostrando apenas o nome de cada author e o número total de commits, respectivamente. | `git shortlog -sn` |
| Traz apenas os 3 últimos commits feitos. | `git log -3` |

## Links úteis
| Link | Descrição |
| ---- | ----------- |
| [Detalhes do git log](https://git-scm.com/docs/git-log) | Link para ter mais detalhes sobre os comandos para ver o log |
| [Detalhes sobre git reflog ](https://git-scm.com/docs/git-reflog) | Link para ter mais detalhes sobre os comandos para ver o gitreflog |







