#csharp
# Tipos de Valor
---

A memória é dividida em duas partes, a __Heap__ e __Stack__

- __Heap__ Armazena os dados.
- __Stack__ armazena a referência para os dados.

Qualquer tipo de dado no .NET é tratado como:
	- Tipo de Referência (_Reference Type_)
	- Tipo de Valor (_Value Type_)

Tipos de valor (_Value Type_) armazenam dados, onde são armazenados em um local da memória chamada __Stack__

- Quando armazenamos um valor, a memória é alocada.
- Este espaço armazena o dado criado
- Nossa variável acessa esse dado diretamente
- Se assimilarmos uma variável do tipo de valor a outra, o valor será __copiado__ e ambas serão independentes.

Tipos de _Value Types_ vistos anteriormente são os tipos primitivos que vimos em Tipos de dados e outras duas estruturas chamadas de __Structs__ e __Enums__ que veremos no futuro.

O __Garbage Collector__ não acessa o Stack, então elas não são removidas.

O __Garbage Collector__ fica olhando a memória __Heap__ e verificando se tem algo que não esteja sendo utilizado e remove e limpa para otimizar o nosso programa, mas ele não mexe com os valores das variáveis salvas no __Stack__

Exemplos:

```csharp
int x = 1;
int y = x; // copia o valor em outra memória

Console.WriteLine(x); // 1
Console.WriteLine(y); // 1

x = 25; // Alterando o valor na memória da variável x

Console.WriteLine(x); // 25
Console.WriteLine(y); // 1
