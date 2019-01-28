## Dicas de Git

Git Reset é usado para branchs separadas, pois evita commits sujos, porém, com isso, é perdido o histórico de rastreio do Git

Git Revert é usado para casos em que é desejado que se mantenha o histórico de rastreio do git, ele cria um commit de revert, assim, mantendo o histórico de rastreio.

git commit --amend é ótimo alterações em nomes de commits, em casos criamos commits com nomes errados e queremos edita-lo. e também que inserir arquvios ou alterações em um commit anterior (Casos em que esquecemos algum arquivo no commit) !!IMPORTANTE: Em casos de alerações enviadas para o repositório na nuvem, seja ele qual for, devemos usas outras estratégias

git cherry-pick ${hash-commit} é ótimo para pegar apenas alguma alteração específica, pegar apenas alterações de um commit ao invés de fazer merge uma branch inteira só para isso