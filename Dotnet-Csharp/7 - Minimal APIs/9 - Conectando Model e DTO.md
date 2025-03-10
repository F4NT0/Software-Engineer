#minimal 

### Instalando Automapper

__AutoMapper__ é um pacote do Nuget que serve para conectar os dados do Model e do DTO de forma automática sem precisar configurar um por um.

Para utilizar, devemos baixar o pacote em nosso projeto, iremos fazer isso pelo Visual Studio 2022 da seguinte forma:

1 - Acesse o Nuget Package Manager pelo Visual Studio 2022

![[16-nugget-package-manager.png]]

Busque no Nuget pelo __AutoMapper__ e encontre a primeira opção, verifique se ele é o mais atualizado da lista.

![[16-automapper-search.png]]

Instale o pacote selecionando qual dos projeto ele vai ser adicionado e selecione a versão mais atual.

![[16-install-automapper.png]]

### Configurando AutoMapper

Agora vamos criar um novo diretório chamado __AutoMapper__ que vai ser criado uma classe chamada __MappingProfile__ que é a classe padrão esperado pelo AutoMapper.

Devemos instanciar a classe __Profile__ que vem junto com o pacote __AutoMapper__.

```csharp
using AutoMapper;
public class MappingProfile : Profile
{}
```

Agora iremos criar um método construtor para nossa classe e utilizaremos o método __CreateMap__ da classe __Profile__ para definirmos o mapeamento da nossa classe __Product__ com o __ProducDTO__ e vice versa.

```csharp
public class MappingProfile : Profile
{
    public MappingProfile() { 

       CreateMap<Product, ProductDTO>();
       CreateMap<ProductDTO, Product>();
    }
}
```

Agora vamos colocar em nossa classe __Program.cs__ a configuração do AutoMapper para podermos utilizar em nosso projeto.

Temos que iniciar um novo _MapperConfiguration_ utilizando a nossa classe _MappingProfile_ adicionando assim os tipos de mapeamento possíveis, depois iniciamos um objeto Mapper para podermos utilizar em nosso projeto.

```csharp
var mapperConfig = new MapperConfiguration(cfg => cfg.AddProfile<MappingProfile>());
var mapper = mapperConfig.CreateMapper();
```

Agora podemos usar o mapeamento entre DTO e Model em nossos controllers e requests.