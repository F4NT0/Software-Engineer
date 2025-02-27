#minimal 
### Entendendo o que é

__Entity Framework__ é uma ferramenta _ORM_ (Object-Relational Mapping) que permite ao desenvolvedor trabalhar com dados relacionais na forma de objetos.

O Entity Framework Core (EF Core) é uma versão leve, extensível e multiplataforma do Entity Framework. O EF Core introduz muitas melhorias e novos recursos quando comparado com o EF6.x. Ao mesmo tempo, o EF Core é uma nova base de código e um novo produto.

Permite aos desenvolvedores .NET trabalhar com um banco de dados usando objetos .NET. Ele elimina a necessidade da maior parte do código de acesso a dados que os desenvolvedores normalmente precisam escrever. O EF Core suporta muitos mecanismos de banco de dados.

### Instalando EF Core pelo Powershell

Vamos instalar o sistema básico primeiro, onde utilizamos o seguinte comando no terminal:

```powershell
dotnet tool install --global dotnet-ef
```

![[11-install-efcore1.png]]

Podemos testar se nossa instalação funcionou com o seguinte comando:

```powershell
dotnet-ef
```

![[11-install-efcore2.png]]


