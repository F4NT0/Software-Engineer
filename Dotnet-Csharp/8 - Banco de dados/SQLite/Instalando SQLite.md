#db 

## Baixando SQLite

Acesse o site [SQLite Download Page](https://sqlite.org/download.html)

Escolha a versão do Windows que possui o nome _tools_ junto porque possui as configurações necessárias para terminal também.

![[1-site-sqlite.png]]

Baixe o _.zip_ e coloque na pasta de Downloads, extraia os documentos e renomeie para __sqlite__

![[2-extract-sqlite.png]]

Agora abra um terminal powershell na pasta _Downloads_ e rode o seguinte comando:

```powershell
Move-Item -Path "$env:USERPROFILE\Downloads\sqlite" -Destination "C:\"
```

Esse comando vai movimentar o projeto __sqlite__ para a pasta principal do seu computador.

## Testando instalação

Agora abrimos um novo terminal no diretório _C_ do seu computador e acessamos o diretório _sqlite_ e depois rodamos o comando __.\sqlite3.exe__ para ver se está funcionando.

![[3-test-sqlite.png]]

## Criando um database

Vamos criar um novo diretório dentro do diretório __sqlite__ chamado __db__ onde iremos colocar todos os banco de dados criados.

![[4-create-db1.png]]

Agora vamos usar o seguinte comando no diretório __sqlite__ para criar um banco de dados

```powershell
.\sqlite db/exampleDB.db
```

Esse comando vai criar um banco de dados com extensão _.db_ e vai iniciar o SQLite pelo terminal para podermos verificar, onde rodando o comando __.database__ mostra todos os banco de dados criados e salvos, mostrando também as permissões possíveis.

![[4-create-db2.png]]

![[4-create-db3.png]]

## Utilizando o database pelo DBeaver

Agora vamos usar um Administrador de banco de dados chamado DBeaver, onde vamos conectar o nosso banco de dados por CLI nele.

Para adicionar o banco de dados nele é simples, vamos clicar no menu com uma tomada e um mais verde e iremos selecionar a opção de conexão com o SQLite.

![[5-connect-dbeaver1.png]]

Agora abrimos o nosso arquivo _.db_ no projeto e criamos em __Test Connection__ onde podemos instalar os drives necessários do SQLite que o DBeaver talvez não tenha.

![[5-connect-dbeaver2.png]]

Caso a conexão seja bem sucedida, vai acontecer a seguinte mensagem:

![[5-connect-dbeaver3.png]]

