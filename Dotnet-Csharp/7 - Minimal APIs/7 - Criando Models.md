#minimal 

### Criando as classes Models

Agora podemos criar nosso Models em nosso projeto, onde precisamos utilizar a biblioteca __DataAnnotations__ da classe __ComponentModel__ do .NET.

Com essa biblioteca de anotações, podemos auxiliar o nosso EF Core o que ele precisa se preocupar de cada atributo da classe.

### Utilizando Annotations

Esta é a tela inicial da explicação dos Annotations: [System.ComponentModel.DataAnnotations Namespace | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations?view=net-8.0)

#### => Criando um atributo ID

Definimos um valor como um ID utilizando a anotação _Key_ para poder dizer ao nosso banco de dados e ao EF Core que esse valor é o _Unique Key_ do banco de dados.

```csharp
[Key]
public long Id { get; set; }
```

#### => Criando um atributo string

Podemos definir o tamanho máximo de uma String com a anotação _StringLength()_ , onde dizemos quantos caracteres nossa string pode ter.

```csharp
[StringLength(50)]
public string Name { get; set; }
```

#### => Definindo um valor obrigatório

Podemos mostrar ao nosso EF Core e no nosso código que um valor é obrigatório utilizando a anotação _Required_ e utilizamos o _required_ adicionado no C# 10 também para que o .NET reconheça que esse valor não pode ser nulo quando inicializado.

Podemos utilizar essas anotações em qualquer tipos de dados.

```csharp
[StringLength(50)]
[Required]
public required string Name { get; set; }
```

#### => Definindo um tamanho específico para um valor

Para tipos _int_ ou _double_ podemos definir um tamanho máximo na hora de salvar no banco de dados.

Para isso, usamos a anotação _Range(min,max)_ para definirmos um valor específico

```csharp
[Range(0, double.MaxValue)]
public double Price { get; set; }
```

### Exemplo de Model completo

Agora que vimos algumas anotações, devemos criar nosso model, que pode ser uma __classe__ ou um __struct__

```csharp
// Exemplo de uma classe
using System.ComponentModel.DataAnnotations;

namespace MinimalAPI.Models
{
    public class Product 
    {
        [Key]
        public long Id { get; set; }
        
        [StringLength(50)]
        [Required]
        public required string Name { get; set; }

        [Range(0, double.MaxValue)]
        [Required]
        public double Price { get; set; }
    }
}
```

```csharp
// Exemplo de uma struct
using System.ComponentModel.DataAnnotations;

namespace MinimalAPI.Models
{
    public struct Product 
    {
        [Key]
        public long Id { get; set; }
        
        [StringLength(50)]
        [Required]
        public required string Name { get; set; }

        [Range(0, double.MaxValue)]
        [Required]
        public double Price { get; set; }
    }
}
```

##### Quando usar Struct

-> Copiado para um valor
-> Mais leve
-> Alocação de memória de Stack, ver ([[Tipos de Valor (Stack)]])
-> Sem suporte para herança
-> Ideal para dados simples, como Models
-> Otimizado até 16 bytes

##### Quando usar Classe

-> Copiado por referencia
-> Suporta herança
-> Alocação de memória de Heap, ver ([[Tipos de Referência (Heap)]])
-> Ideal para objetos complexos
-> Possui encapsulação, herança, polimorfismo
-> Implementa interfaces


