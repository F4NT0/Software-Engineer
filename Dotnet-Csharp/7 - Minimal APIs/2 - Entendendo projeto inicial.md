#minimal 

- [[#Estrutura|Estrutura]]
- [[#Solution 'MinimalApi'|Solution 'MinimalApi']]
- [[#MinimalApi.csproj|MinimalApi.csproj]]
- [[#appsettings.json|appsettings.json]]
- [[#launchSettings.json|launchSettings.json]]
- [[#Program.cs|Program.cs]]

### Estrutura
---
Todo projeto .NET é feito dentro de uma solution, como podemos ver pelo visual studio 2022:
![[6-entendendo-solution.png]]
Vamos ver com detalhes essa estrutura.
![[7-minimal-estrutura.png]]
### Solution 'MinimalApi'
- Uma Solution em .NET é um contêiner lógico que agrupa um ou mais projetos relacionados.
- Usada para organizar e gerenciar o desenvolvimento de aplicativos que podem conter vários projetor
- Um uso comum de uma Solution é para se ter um projeto ASP.NET e outro de testes.
- Podemos ter projetos como biblioteca de classes, aplicativos web, aplicativos de console, testes unitários, etc...
- Cada projeto é uma unidade independente.
### MinimalApi.csproj
- MinimalApi é um projeto web do tipo SDK _Microsoft.NET.Sdk.Web_.
- Clicando em cima do nome __MinimalApi__ ele vai abrir um arquivo do tipo _.csproj_
- Nesse arquivo estão as configurações do projeto em si, assim como as dependências e referências necessárias para construir o aplicativo.
- Esse arquivo é escrito em XML e tem a seguinte estrutura
```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net8.0</TargetFramework>
    <Nullable>enable</Nullable>
    <ImplicitUsings>enable</ImplicitUsings>
  </PropertyGroup>

</Project>

```
### appsettings.json
- Arquivo de configuração onde armazena configurações de aplicação em formato JSON.
- Aqui colocamos a configuração de conexão com banco de dados, configurações de logging,etc.
- Aqui possui um exemplo básico
```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}

```
### launchSettings.json
- Arquivo de configuração das formas de iniciar o projeto.
- Fica dentro de um diretório chamado _Properties_
- Aqui definimos a porta de conexão e as URLs para rodarmos o projeto
- Este é o arquivo que o programa vai utilizar para rodar o projeto tanto pelo Visual Studio quanto por console.
- Exemplo básico de launchsettings
```json
{
  "$schema": "http://json.schemastore.org/launchsettings.json",
  "iisSettings": {
    "windowsAuthentication": false,
    "anonymousAuthentication": true,
    "iisExpress": {
      "applicationUrl": "http://localhost:42138",
      "sslPort": 44323
    }
  },
  "profiles": {
    "http": {
      "commandName": "Project",
      "dotnetRunMessages": true,
      "launchBrowser": true,
      "applicationUrl": "http://localhost:5223",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    },
    "https": {
      "commandName": "Project",
      "dotnetRunMessages": true,
      "launchBrowser": true,
      "applicationUrl": "https://localhost:7078;http://localhost:5223",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    },
    "IIS Express": {
      "commandName": "IISExpress",
      "launchBrowser": true,
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    }
  }
}
```
### Program.cs
- Este é o arquivo principal em C# do projeto .NET
- Este arquivo contém o ponto de entrada da aplicação, onde tem o primeiro método a ser executado ou como no caso após o C# 9 ele possui os códigos em C# que vão ser executados primeiro.
- Este arquivo possui as configurações que serão usadas pelo programa.
- Abaixo o arquivo de exemplo inicial quando criamos pela primeira vez um projeto.
```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "Hello World!");

app.Run();
```
