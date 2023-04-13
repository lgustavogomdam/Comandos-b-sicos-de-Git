
# Tutorial Git
Autor: Luiz Gustavo Gomes Damasceno

Instagram: <https://www.instagram.com/recurscire/>

Linkedin: <https://www.linkedin.com/in/lgustavogomdam/>

GitHub: <https://github.com/lgustavogomdam>

#### Comandos Básicos de Git para facilitar seu dia-a-dia :)

## Comandos de Inicialização


> **git init**
```
Inicia um arquivo Git no diretório.
```


> **git clone <URL_do_repositório>**
```
Clonar um repositório
```


## Commit's

> **git add <nome_arquivo>**
```
adiciona apenas o arquivo mencionado
```

> ** git add . ** 
```
adiciona todos os arquivos existentes na pasta que o Git foi iniciado 
```

> **git status**
```
 Verifica quais arquivos estão visíveis ao Git (quais foram adicionados e quais não foram)
```

> **git commit "**
```
Grava as alterações feitas no repositório.
```
> **git commit -m "< mensagem >"**
```
Acrescenta-se a funcionalidade de você conseguir passar uma mensagem no commit (geralmente utilizada para indicar a ação realizada).
```
> **git commit -C   < commit >**
```
Acrescenta-se a funcionalidade de você conseguir reutilizar a mensagem que já exista em outro commit (passa-se o log do commit desejado).
```

> **git commit -C   < commit > --reset-author**
```
Funciona como o -C normalmente mas acrescenta-se a possibilidade de setar um novo autor para o commit (utilizado quando você usa a mensagem de commits de outros autores). 
```

## Restaurar

> **git restore**
```
Restaura os arquivos das árvores de trabalho.
```

> **git restore -s**
```
Restaure arquivos da árvore de trabalho com o conteúdo da árvore informada.
É comum especificar a árvore de origem nomeando um commit, ramo ou tag
associado com ela.

Caso não seja definido, o conteúdo será restaurado a partir de  `HEAD`  
caso  `--staged`  seja informado, caso contrário, a restauração será a
partir do índice.
```

> **git restore -S**
```
Especifica o local da restauração. É predefinido que caso nenhuma opção 
seja utilizada a árvore de trabalho será restaurada. Ao usar a opção
`--staged` apenas a índice será restaurado. A utilização de ambas as
opções faz a restauração de ambos.
```

> **git reset**
```
Redefine o `HEAD` atual para a condição especificada.
```

> **git reset --soft**
```
Não toca no arquivo de índice ou na árvore de trabalho (mas redefine o 
cabeçalho para `<commit>`, assim como todos os modos fazem). Isso deixa
todos os seus arquivos alterados como "Changes to be committe" (Alterações
onde serão realizados os commits), como o `git status` colocaria.
```

> **git reset --mixed**
```
Redefine o índice, mas não a árvore de trabalho (ou seja, os arquivos alterados são preservados, mas não marcados para um commit) e relata o que não foi atualizado. Esta é a ação predefinida.
Caso  `-N`  seja especificado, os caminhos removidos serão marcados como uma intenção de adicionar (consulte  [git-add[1]](https://git-scm.com/docs/git-add/pt_BR)).
```

> **git reset --hard**
```
Redefine o índice e a árvore de trabalho. Quaisquer alterações nos arquivos rastreados na árvore de trabalho desde `<commit>` serão descartados.
```

> **git reset --merge**
```
Redefine o índice e atualiza os arquivos na árvore de trabalho que sejam diferentes entre o  `<commit>`  e o  `HEAD`, mas mantém aqueles que são diferentes entre o índice e a árvore de trabalho (ou seja, que têm alterações que não foram adicionadas). Caso haja um arquivo diferente entre  `<commit>`  e o índice tiver alterações sem etapas, a redefinição será abortada.

Em outras palavras,  `--merge`  faz algo como um  `git read-tree -u -m <commit>`, mas carrega as entradas do índice não mescladas adiante.
```
## Remover

> **git  rm**
```
Remove os arquivos da árvore de trabalho e do índice.

Variações: https://git-scm.com/docs/git-rm/pt_BR
```

> **git  rm --cached < nome_arquivo >**
```
Remove os arquivos em cachê da árvore de trabalho e do índice (utilizado para remover os arquivos da visibilidade do git depois de usar o git add).

Variações: https://git-scm.com/docs/git-rm/pt_BR
```
## Mover

> **git  mv**
```
Move ou renomeia um arquivo, um diretório ou um link simbólico.

Variações: https://git-scm.com/docs/git-mv/pt_BR
```

## Branch's

> **git  branch**
```
Lista, cria ou exclui branchs(ramificações).

Variações: https://git-scm.com/docs/git-branch/pt_BR
```

> **git  branch -a**
```
Liste ambas as ramificações rastreadas remotamente e as ramificações locais.

Variações: https://git-scm.com/docs/git-branch/pt_BR
```

> **git  branch -d**
```
Exclua uma ramificação.

Variações: https://git-scm.com/docs/git-branch/pt_BR
```

> **git  branch -r**
```
Liste ou exclua (se utilizado com -d) as ramificações rastreadas remotamente.

Variações: https://git-scm.com/docs/git-branch/pt_BR
```

> **git  branch -m**
```
Mover / renomear uma ramificação e o reflog correspondente.

Variações: https://git-scm.com/docs/git-branch/pt_BR
```

> **git  branch -c**
```
Copie uma ramificação e o reflogo correspondente.

Variações: https://git-scm.com/docs/git-branch/pt_BR
```

## Navegação entre branch's

> **git  checkout < nome_branch >**
```
Usado para navegar entre as branchs.

Variações: https://git-scm.com/docs/git-checkout/pt_BR
```

> **git  checkout -b < nome_branch >**
```
Caso a opção `-b` seja utilizada, então um `<novo-ramo>` é criado.
Caso a opção `-B` seja utilizada, então um `<novo-ramo>` é criado caso ainda não exista, senão, será redefinido.

Variações: https://git-scm.com/docs/git-checkout/pt_BR
```

> **git  switch < nome_branch >**
```
Alterna entre branchs.

Variações: https://git-scm.com/docs/git-switch/pt_BR
```

> **git  switch < nome_branch >**
```
Alterna entre branchs.

Variações: https://git-scm.com/docs/git-switch/pt_BR
```

## Mergear (Unir branch's)

> **git  merge < nome_branch >**
```
Une dois ou mais históricos de desenvolvimento.

Incorpora as alterações dos commits citados (desde o momento em que os seus históricos divergirem do ramo atual) para dentro do ramo atual. Este comando é utilizado pelo  _git pull_  para incorporar as alterações vindos de outro repositório e pode ser utilizado manualmente para mesclar as alterações do outro ramo para um outro.

Suponha que exista o seguinte histórico e o ramo atual seja  `master`:

          A---B---C  topic
	     /
    D---E---F---G  master

Em seguida, `git merge topic` repetirá as alterações feitas no ramo `topic` uma vez que ele divergiu de `master` (ou seja,`E`) até que o seu commit atual (`C`) no topo do `master` registrando o resultado em um novo commit junto com os nomes de dois commits relacionados em uma mensagem log vindo do usuário descrevendo as alterações.

          A---B---C  topic
	     /         \
    D---E---F---G---H  master

A segunda sintaxe ("`git merge --abort`") só pode ser executada após o resultado da mesclagem apresentar conflitos. O comando  _git merge abort_  abortará o processo de mesclagem e tentará reconstruir a condição anterior a mesclagem. No entanto, Caso haja alterações com commits não realizados quando a mesclagem for iniciada (e especialmente caso estas alterações forem modificadas posteriormente após o início da mesclagem), o  _git merge abort_  será, em alguns casos, incapaz de reconstruir as alterações originais (pré-mesclagem). Portanto:

**Aviso**: É desencorajado executar o comando  _git merge_  com alterações não-triviais dos commits que não foram feitos é desencorajado: enquanto possível, pode deixá-lo em uma condição difícil de sair no caso de haver um conflito.

A terceira sintaxe ("`git merge --continue`") só pode ser executada depois que a mesclagem apresentar conflitos.

Variações: https://git-scm.com/docs/git-merge/pt_BR
```


> **git  merge < nome_branch > --commit**
```
Une dois ou mais históricos de desenvolvimento e em seguida prepara o commit para envio.
```

## Push  (Enviar commit's)

> **git  push --set-upstream < nome_repositorio_remoto >  < nome_branch >**
```
Envia os commit's para o repositório remoto .

Variações: https://git-scm.com/docs/git-push/pt_BR
```

## Pull (Baixar dados)

> **git  pull < nome_repositorio_remoto >  < nome_branch >**
```
Baixa os dados e commits do repositório remoto para o repositório local.

Variações: https://git-scm.com/docs/git-pull/pt_BR
```

## Remote (Gerenciar Repositórios)

> **git  remote**
```
Lista os repositórios abertos ou iniciados.

Variações: https://git-scm.com/docs/git-remote/pt_BR
```

> **git  remote add < nome_repositorio > < URL_do_repositório >**
```
Adiciona um repositório remoto ao projeto git (define para qual repositório enviar os commit's).

Variações: https://git-scm.com/docs/git-remote/pt_BR
```

> **git remote rename < nome_antigo > < nome_novo >**
```
Renomeia o repositório X para repositório Y (X e Y são exemplos).

Variações: https://git-scm.com/docs/git-remote/pt_BR
```

> **git remote remove < nome_repositório >**
```
Exclui o repositório especificado.

Variações: https://git-scm.com/docs/git-remote/pt_BR
```

> **git remote set-url < nova_URL >**
```
Altera a URL padrão de envio, substitui a antiga pela especificada caso haja uma antiga.

Com --add, em vez de alterar as URLs existentes, uma nova URL é adicionada.

Com --delete, em vez de alterar as URLs existentes, todas as URLs coincidentes à expressão regular <url> são excluídas para o ramo remoto <nome>. Tentar excluir todas as URLs não push é um erro.

Variações: https://git-scm.com/docs/git-remote/pt_BR
```

> **git remote show< nome_repositório >**
```
Fornece informações sobre o repositório especificado.

Variações: https://git-scm.com/docs/git-remote/pt_BR
```

## Inspecionar Commit's

> **git  log**
```
Exibe os registros log do commit.

Variações: https://git-scm.com/docs/git-log/pt_BR
```

> ** git diff **   
```
Mostra mudanças entre commits, commit e árvore de trabalho, etc (recomenda-se ler e aprofundar-se mais pois é um tanto quanto complexo).Variações: https://git-scm.com/docs/git-diff/pt_BRLink de estudo didático (Sugestão): https://www.youtube.com/watch?v=cJwKvQv4gTA
```

> ** git reflog **  
```
Mostra informações dos commits de forma sucinta.Variações: https://git-scm.com/docs/git-reflog/pt_BR
```

## Administração


> ** git clean ** 
```
Remove arquivos não rastreados da árvore de trabalho.

Limpa a árvore de trabalho removendo recursivamente arquivos que não estão sob controle de versão, iniciando no diretório atual.

Normalmente, apenas os arquivos desconhecidos pelo Git são removidos, porém caso a opção  `-x`  seja utilizada, os arquivos ignorados também serão removidos. Isso pode, por exemplo, ser útil para remover todos os produtos da compilação.

Caso a opção '-X' seja utilizada, remove apenas os arquivos ignorados pelo Git. Isto pode ser útil para reconstruir tudo do zero, porém mantém os arquivos que foram criados manualmente.

Se algum argumento opcional  `<caminho>...`  for dado, somente esses caminhos serão afetados.

Variações: https://git-scm.com/docs/git-clean/pt_BR
```

> **touch gitignore**
```
Cria o arquivo gitignore no diretório.

Variações: https://git-scm.com/docs/git-gitignore/pt_BR
```

> **git config --global user.email "< seuEmail@dominio.com >"**
```
Define seu email como o email especificado(nos commits aparecerá seu email e seu nome).

Variações: https://git-scm.com/book/pt-br/v2/Começando-Configuração-Inicial-do-Git
```

> **git config --global user.name "< seu_nome >"**
```
Define seu nome como o nome especificado(nos commits aparecerá seu email e seu nome).

Variações: https://git-scm.com/book/pt-br/v2/Começando-Configuração-Inicial-do-Git
```

> **git config --global --unset user.email**
```
Exclui seu email que antes fora especificado.

Créditos: https://medium.com/@yuribrasil_73050/limpar-credenciais-72cf6cf29197
```

> **git config --global --unset user.name**
```
Exclui seu nome que antes fora especificado.

Créditos: https://medium.com/@yuribrasil_73050/limpar-credenciais-72cf6cf29197
```

> **git config --global --unset credential.helper**
```
Limpar as informações de credenciais globais guardadas.

Créditos: https://medium.com/@yuribrasil_73050/limpar-credenciais-72cf6cf29197
```

> **git config --system --unset credential.helper**
```
Apagar as informações de credenciais contidas no sistema(se fizer isso terá que fazer login novamente no github ao enviar um projeto).

Créditos: https://medium.com/@yuribrasil_73050/limpar-credenciais-72cf6cf29197
```
