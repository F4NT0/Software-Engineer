# Entendendo Enums
---

__Enum__ significa Enumerador.

- Utilizamos __Enum__ para fornecer uma melhor visualização do código.
- Substituímos o uso de inteiros com o enum.
- Usado muito em listas curtas.
- Usado em dados fixos, onde tem valores pré-definidos.
- Um __enum__ sempre começa em maiúsculo e começando com a letra __E__

## Estrutura base

==Enum deve ser criado fora de uma classe==

definimos um Enumerador da seguinte forma:

```csharp
enum EEstadoCivil
{
	// Enumeradores
}
```

Com o nosso exemplo podemos definir os seguinte valores de estados civil:
- Solteiro, representado pelo numero 1.
- Casado, representado pelo numero 2.
- Divorciado, representado pelo numero 3.

```csharp
enum EEstadoCivil
{
	// Enumeradores
	Solteiro = 1,
	Casado = 2,
	Divorciado = 3
}
```

## Utilizando o Enum

Podemos utilizar o Enum em qualquer lugar do projeto, mas um exemplo bom seria utilizar com o struct de um cliente, onde teremos o nome dele e o estado civil:

```csharp
// Estrutura do struct
struct Cliente
{
	public string Nome;
	public EEstadoCivil EstadoCivil;

	public Cliente(string nome, EEstadoCivil estadoCivil)
	{
		Nome = nome;
		EstadoCivil = estadoCivil;
	}
}
```

Podemos chamar o Enum em nosso struct dentro do método Main assim:

```csharp
// Sem enumerador
var cliente = new Cliente("Joao", 2); // 2 significa casado

// Com enumerador
var cliente = new Cliente("Joao", EEstadoCivil.Casado);
```

Caso queremos imprimir dados de um enumerador, podemos fazer de duas formas, ou imprimimos o nome salvo ou imprimimos o valor salvo, olhe o exemplo:

```csharp
var cliente = new Cliente("Joao", EEstadoCivil.Casado);

Console.WriteLine(cliente.Nome); // Joao
Console.WriteLine(cliente.EstadoCivil); // Casado (escreve o nome)
Console.WriteLine((int)cliente.EstadoCivil); // 2 (escreve o número)
```

## Exemplo completo

Abaixo temos o exemplo completo do Enum acima:

```csharp
namespace MeuApp
{
    // ENUM
    enum EEstadoCivil
    {
        Solteiro = 1,
        Casado = 2,
        Divorciado = 3
    }

    // STRUCT
    struct Cliente
    {
       public string Nome;
       public EEstadoCivil EstadoCivil;
  
       public Cliente(string nome, EEstadoCivil estadoCivil)
       {
            Nome = nome;
            EstadoCivil = estadoCivil;
        }
    }

  

    // CLASS

    class Program
    {
      public static void Main(string[] args)
      {
        var cliente = new Cliente("João", EEstadoCivil.Casado);

        Console.WriteLine($"Nome: {cliente.Nome}");
        Console.WriteLine($"Estado Civil: {cliente.EstadoCivil}");
        Console.WriteLine($"Estado Civil Numero: {(int)cliente.EstadoCivil}");
      }
    }
}