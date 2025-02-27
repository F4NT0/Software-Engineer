#minimal 

## Baixando o pacote do Swagger
---
Vá em __Tools -> Nuget Package Manager -> Manage Nuget Packages for Solution...__.

![[8-acessando-2.png]]

Procure por __Swashbuckle.AspNetCore__ na busca, você vai encontrar os seguintes pacotes.

![[10-install-swagger.png]]

Clique para instalar o __Swashbuckle.AspNetCore__ onde vai mostrar que temos que selecionar qual projeto iremos adicionar ele e a versão mais atual compatível com seu .NET.

![[10-install-swagger-2.png]]

O Visual Studio irá mostrar quais pacotes e dependências irão ser adicionados no programa, clique em __Apply__ para adicionar eles no seu projeto.

![[10-install-swagger-3.png]]

Depois ele vai lhe dizer sobre a licença da Microsoft para esse pacote, só precisa clicar em __I Accept_.

![[10-install-swagger-4.png]]

Com isso, o pacote Swagger do Nuget foi instalado no nosso projeto e foi configurado no nosso arquivo _.csproj_ do projeto que selecionamos ele para salvar

![[10-install-swagger-5.png]]

Podemos ver também as dependências pelo __Solution Explorer__ no Visual Studio

![[10-install-swagger-6.png]]

## Configurando o Swagger no Program.cs

Agora que temos o nosso Swagger instalado no nosso projeto, temos que configurar o uso dele em nosso _Program.cs_.
Primeiro comando que iremos adicionar é o seguinte:

```csharp
builder.Services.AddEndpointsApiExplorer();
```

Esse comando é utilizado em programas ASP.NET Core para registrar serviços que expõem informações sobre os Endpoints da API, ele adiciona um provedor de descrição de API que gera descrições de endpoints diretamente a partir de endpoints registrados, sem depender de nenhuma aplicação utilizado em APIs tradicionais.

Utilizamos esse comando para ajudar o Swagger garantir que possui todas as descrições de endpoints gerados corretamente.

Próximo comando é o seguinte:

```csharp
builder.Services.AddSwaggerGen();
```

Este comando vai adicionar e configurar nosso Swagger no projeto, ele vai criar uma documentação baseada no OpenAPI Specification, ele vai registrar o gerador Swagger na coleção de Serviços necessários para a API para que a documentação seja gerada automaticamente a partir de Controllers e Services criados no nosso projeto.

Quando queremos verificar as exceptions que ocorrem no projeto, podemos definir que quando o `Environment` definido no arquivo _launchSettings.json_ for do tipo __Development__ mostre as exceções que ocorreram no projeto, como mostra abaixo:

```csharp
// no launchSettings.json
https: {
	"environmentVariables": {
		"ASPNETCORE_ENVIRONMENT": "Development"
	}
}

// no Program.cs
if (app.Environment.IsDevelopment())
{
	app.UseDeveloperExceptionPage();
}
```

Vamos agora inicializar o Swagger em nosso projeto, onde utilizamos o seguinte comando:

```csharp
app.UseSwagger();
```

E por fim, devemos inicializar a visualização gráfica do Swagger no sistema com o seguinte comando:

```csharp
app.UseSwaggerUI();
```

Com esses comandos temos o Swagger definido em nosso projeto, então quando rodamos ele vai ser aberto uma nova tela onde vai ter todos os endpoints (tipos de requisição) que podemos fazer.

Agora por final, vamos no arquivo _launchSettings.json_ e adicionaremos a seguinte linha no JSON:

```json
"launchUrl": "swagger"
```

Colocaremos isso em todos os perfis de inicialização do nosso projeto.

![[10-install-swagger-7.png]]


