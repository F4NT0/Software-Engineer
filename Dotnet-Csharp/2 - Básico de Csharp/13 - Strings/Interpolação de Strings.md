## O que é
---
Interpolação é unificar dois valores transformando em String, podendo esse valor ser qualquer um que será transformado em String.

## Interpolação simples

Podemos chamar qualquer variável não importa o valor somando com uma string como no exemplo abaixo

```csharp
var price = 10.2;

var text = "The price is " + price;

Console.WriteLine(text); // The price is 10.2
```

## Interpolação com Format

Podemos usar um método da classe string chamado de __Format()__ onde ele vai pegar a String e substituir onde tiver __{}__ pela ordem de valores que forem definidos no método, como o seguinte exemplo:

```csharp
var price = 10.2;
var text = string.Format("The price is {0}", price);
Console.WriteLine(text); // The price is 10.2
```

Podemos colocar quantos valores quisermos, só temos que colocar na ordem certa, __0__ vai ser o primeiro atributo e assim por diante:

```csharp
var name = "Gabriel";
var middleName = "Fanto"
var connect = string.Format("My name is {0} {1}",name,middleName);
Console.WriteLine(text); // My name is Gabriel Fanto
```

## Interpolação com $

Podemos interpolar como o string.Format() mas é bem mais simples e podemos colocar o nome da variável que queremos utilizar, podendo ser livre o uso sem pensar em ordem como no Format:

```csharp
var name = "Gabriel";
var middleName = "Fanto";
var connect = $"My name is {name} {middleName}"; 
Console.WriteLine(connect); // My name is Gabriel Fanto
```

## Saída sem caracteres de escape

Quando colocamos __\n__ ou __\t__ são chamados de caracteres de escape e se você estiver utilizando eles em uma String pode dar problema na hora de imprimir, como abaixo:

```csharp
var price = 10;
var info = $"Price of \n Cost is {price}";
Console.WriteLine(info); 
// Price of
// Cost is 10
```

Para evitar isso, podemos utilizar o símbolo __@__ que vai evitar de sofrer alterações na String na hora de utilizar ela:

```csharp
var price = 10;
var info = $@"Price of \n Cost is {price}";
Console.WriteLine(info); 
// Price of \n Cost is 10
```