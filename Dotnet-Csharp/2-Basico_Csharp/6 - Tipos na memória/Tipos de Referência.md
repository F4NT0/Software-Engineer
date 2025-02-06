#csharp
# Tipos de Referência
---

A memória é dividida em duas partes, a __Heap__ e __Stack__

- __Heap__ Armazena os dados.
- __Stack__ armazena a referência para os dados.

Qualquer tipo de dado no .NET é tratado como:
	- Tipo de Referência (_Reference Type_)
	- Tipo de Valor (_Value Type_)

Tipos de Referência (_Reference Types_) Armazenam o endereço do objeto que contém os dados.

Não são armazenados os dados em si, somente os objetos que contém os dados, esses objetos são salvos em um local da memória chamada __Heap__

Quando é assimilado uma variável, ele vai:
	- Criará uma referência
	- Aponta para a mesma informação
	- Não são independentes

Quando não mais utilizados são marcados para __exclusão__

O __Garbage Collector__ passa removendo todos eles

Tipos de estruturas assim são por exemplo as __Classes__, __Objects__ e __Arrays__.

Exemplos:

```csharp
var arr = new string[2];
arr[0] = "Item 1";

var arr2 = arr; // Não cria uma cópia, só cria uma referência

Console.WriteLine(arr[0]); // Item 1
Console.WriteLine(arr2[0]); // Item 1

arr[0] = "Item alterado" // Vai alterar nas duas listas ao mesmo tempo

Console.WriteLine(arr[0]); // Item alterado
Console.WriteLine(arr2[0]); // Item alterado