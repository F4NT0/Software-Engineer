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

Para instalação do SQLite e outras informações veja [[Home SQLite]]

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

Vamos adicionar agora o método construtor que iremos precisar para configurar o banco de dados no __Program.cs__ 

```csharp
public class AppDbContext : DbContext
{
	public AppDbContext(DbContextOptions<AppDbContext> options) : base(options){}  
}
```

Nesse comando está sendo definido que o parâmetro _options_ está esperando um objeto da classe publica chamada __AppDbContext__ usando nossa classe e depois chamando o construtor da classe base (chamada DbContext) com o novo parâmetro options, isso serve para iniciar a conexão com o banco de dados personalizado utilizando o EntityFrameworkCore.

### Configurando SQLite no Program.cs

Agora podemos chamar o serviço do SQLite no Program, onde iremos utilizar a configuração do nosso __applicationsettings.json__ e a configuração feita na nova classe __AppDbContext__.

Iremos chamar o serviço __AddDbContext__ e iremos configurar nosso SQLite com o método __UseSqlite__ 

```csharp
/// Configuring the database
builder.Services.AddDbContext<AppDbContext>(options => {
options.UseSqlite(builder.Configuration.GetConnectionString("DefaultConnection"));
});
```
Nesse comando iremos utilizar nossa classe de configuração do banco de dados chamada _AppDbContext_ e iremos utilizar a nossa configuração do _appsettings.json_ da __ConnectionString__ chamada __DefaultConnection__ onde vai buscar o nosso banco de dados especificado.

