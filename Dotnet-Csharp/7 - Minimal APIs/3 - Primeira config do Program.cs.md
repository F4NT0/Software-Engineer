#minimal

- [[#Não precisa mais de using|Não precisa mais de using]]
- [[#Entendendo o Builder|Entendendo o Builder]]
- [[#Adicionando Pacotes (packages) com Nuget|Adicionando Pacotes (packages) com Nuget]]
- [[#Utilizando Nuget no Visual Studio|Utilizando Nuget no Visual Studio]]

## Não precisa mais de using
---
- Agora após o C# 9, é utilizado o sistema do __global using__ onde não precisamos mais especificar os using do projeto, porque eles são adicionados durante o processo de compilação.
- Para isso funcionar, precisamos colocar no nosso _MinimalAPI.csproj_ a seguinte tag:

```xml
<ImplicitUsings>enable</ImplicitUsings>
```

- Normalmente já vem com essa tag quando criamos um novo projeto pelo visual studio 2022.

## Entendendo o Builder
---
Todo arquivo _Program.cs_ começa com a seguinte linha de código:

```csharp
var builder = WebApplication.CreateBuilder(args);
```

- Utilizamos o método __WebApplication.CreateBuilder(args)__ para configurar um objeto da classe __WebApplication__ que possui os serviços e o pipeline de solicitação da aplicação, o parâmetro _args_ contém os argumentos de linha de comando passados para a aplicação.
- Com o _builder_ criado, podemos adicionar serviços, middlewares e outras configurações necessárias para a nossa aplicação.
Com o builder criado, podemos começar o nosso app, onde fazemos o _build_ do projeto, com o seguinte código:

```csharp
var app = builder.Build();
```

Agora com esse App, podemos criar nosso projeto, onde podemos definir o que quisermos na aplicação a partir desse código.
## Adicionando Pacotes (packages) com Nuget
---
- Agora queremos adicionar o swagger no nosso projeto, para isso vamos usar o __Nuget__ para gerenciar nossos pacotes.
- __Nuget__ é o gerenciador de pacotes oficial para o .NET, ele facilita a adição, atualização e remoção de bibliotecas e pacotes de projetos no .NET.
- Pode ser usado para compartilhar código de forma simplificada e reutilizar bibliotecas de terceiros.
- Todos os pacotes tem a extensão _.nupkg_ contendo o código compilado (DLLs) e todo o conteúdo que o pacote necessite.
- Os pacotes Nuget são armazenados em repositórios, como o __Nuget Gallery (nuget.org)__ onde se pode buscar e baixar esses pacotes.
- Pode ser usado a linha de comando (CLI) para gerenciar os pacotes ou pelo Visual Studio 2022
- Nuget gerencia automaticamente as dependências entre pacotes, garantindo que todas as bibliotecas estão instaladas.
## Utilizando Nuget no Visual Studio
- Podemos acessar facilmente o Nuget pelo Visual Studio com uma excelente UI para vermos todos os pacotes, para isso devemos acessar __Tools__ depois __Nuget Package Manager__ e por fim __Manage Nuget Packages for Solution__.

![[8-acessando-nuget.png]]
- Agora podemos ter uma visão dos pacotes que temos instalado e os pacotes que devemos instalar.
![[9-visual-nuget.png]]
