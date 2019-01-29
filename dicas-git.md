## Dicas de Git

Git reset: É usado para branchs separadas, pois evita commits sujos, porém, com isso, é perdido o histórico de rastreio do Git.

Git revert: É usado para casos em que é desejado que se mantenha o histórico de rastreio do git, ele cria um commit de revert, assim, mantendo o histórico de rastreio.

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


