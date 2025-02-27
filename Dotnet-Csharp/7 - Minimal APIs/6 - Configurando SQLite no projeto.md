#minimal 

### Instalando os pacotes necessários

Agora que instalamos o EF Core, devemos instalar em nosso projeto 4 pacotes necessários para usar o EF Core dentro de nosso projeto minimalista.

1. Microsoft.EntityFrameworkCore
2. Microsoft.EntityFrameworkCore.Sqlite
3. Microsoft.EntityFrameworkCore.Design
4. Microsoft.EntityFrameworkCore.Tools

Iremos instalar como foi feito a instalação do Swagger, pelo _Nuget Package Manager_

![[12-nuget-efcore-sqlite.png]]

Iremos salvar os 4 pacotes pedidos que irão aparecer assim na aba de instalados:

![[12-nuget-all-efcore.png]]
### Criando banco de dados inicial

Para instalação do SQLite veja a página [[Instalando SQLite]]

Vou criar um novo banco de dados pelo console:

![[13-created-db-sqlite.png]]

O comando `.\sqlite3 db/minimalapi.db` no diretório _C:/_ vai criar um banco de dados vazio para podermos utilizar do SQLite.
### Configurando o appsettings.json

Agora que temos um banco de dados do SQLite, devemos configurar ele em nosso projeto, para isso devemos atualizar o _appsettings.json_ para criarmos nossa conexão com o __ConnectionStrings__ 

```json
"ConnectionStrings": {
  "DefaultConnection": "Data Source=minimalapi.db"
}
```

### Criando diretório do banco de dados

Vamos criar um novo diretório chamado __Data__ em nossa API, para isso clicamos com o botão direito em cima do nome da API e vamos em __Add__ e depois em __New Folder__.

![[14-new-folder-data.png]]

Alteramos o nome para __Data__ e vamos criar um arquivo chamado __AppDbContext__ onde vamos fazer uma classe em C#, clicando com o botão direito em cima da pasta e selecionando __Add__ e depois em __Class__.

![[14-creating-data-class.png]]

Definimos que será do tipo __Class__ e que o nome será __AppDbContext__ , este arquivo vai ser a entrada principal de informações de banco de dados em nosso projeto.

![[14-new-data-class.png]]

Esta é a estrutura base dessa nova classe:

```csharp
namespace MinimalAPI.Data
{
    public class AppDbContext
    {
    }
}

```

Agora vamos conectar nossa classe recebendo de herança a classe __DbContext__ do EntityFrameworkCore:

```csharp
using Microsoft.EntityFrameworkCore;

namespace MinimalAPI.Data
{
    public class AppDbContext : DbContext
    {
    }
}
```

