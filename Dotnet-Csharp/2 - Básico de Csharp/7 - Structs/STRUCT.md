#csharp
# Entendendo Structs
---

- __Structs__ é um tipo de dado estruturado em C#.
- Ele é apenas uma estrutura, um esqueleto.
- Armazena apenas outros tipos de dados.
- Composto de propriedades e métodos.
- Nome sempre deve ser maiúsculo, tanto para propriedades e métodos.
- Um __struct__ é sempre criado a partir da palavra _new_ e então nesse momento teremos valores no nosso Struct.

## Estrutura base

Dentro de um struct sempre terá as __propriedades__ e os __métodos__ definidos

```csharp
struct Name
{
	// Propriedades

	// Métodos
}
```

## Exemplo de produtos

Agora vamos criar um struct completo, onde queremos definir propriedades para um produto, onde teremos o ID do produto e o preço.

Além das propriedades, iremos criar um método para transformar o preço do produto para o dólar.

```csharp
struct Product
{
	// Propriedades
	public int Id;
	public float Price;

	// Métodos
	public float PriceInDolar(floar dolar)
	{
		return Price * dolar;
	}
}	
```

Agora que criamos o nosso struct, devemos iniciar ele em uma classe o método utilizando a palavra reservada _new_ e chamando o struct criado.

```csharp
static void Main(string[] args)
{
	var product = new Product(); // Cria um novo produto
}
```

Podemos colocar valores dentro de nosso struct agora que ele foi criado, onde cada propriedade pode ser invocada e um valor ser salvo dentro.

```csharp
static void Main(string[] args)
{
	var product = new Product();
	product.Id = 1;
	product.Price = 191.23f;

	Console.WriteLine(product.Id); // 1
	Console.WriteLine(product.Price); // 191.23
}
```

## Método construtor

Podemos criar um método construtor mostrando os atributos que nosso struct precisa, para podermos definir os valores de todos os dados ou alguns uma única vez, assim fica fácil de definir os valores quando cria uma nova instância do struct.

==Deve ter o mesmo nome do struct para ser considerado método construtor==

```csharp
struct Product
{
	public Product(int id, float price)
	{
		Id = id;
		Price = price;
	}
}
```

Agora que definimos o construtor, na hora de criarmos uma nova instância dele com _new_ já podemos passar os valores esperados.

```csharp
static void Main(string[] args)
{
	var product = new Product(1,128.25f);
	Console.WriteLine(product.Id); // 1
	Console.WriteLine(product.Price); // 128.25
	Console.WriteLine(product.PriceInDolar(5.70f)); // 
}
```

## Apresentação completa

==Os structs não podem ser criados dentro de uma classe, deve ser criado fora==

Um exemplo completo:

```csharp
using System;

namespace MeuApp
{
	// Aqui se cria um struct
	struct Product
	{
		// Propriedades
		public int Id;
		public float Price;

		// Métodos
		public Product(int id, float price)
		{
			Id = id; // Id é propriedade, id é parâmetro
			Price = price;
		}

         public float PriceInDolar(floar dolar)
		{
			return Price * dolar;
		}
	}

	class Program
	{
		static void Main(string[] args)
		{
			var product = new Product(1,123.4f);

			Console.WriteLine(product.Id);
			Console.WriteLine(product.Price);
			Console.WriteLine(product.PriceInDolar(5.70f));
		}
	}
}