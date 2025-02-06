#csharp
# Apresentação de classes .NET
---

## Métodos com estado vs. sem estado

Em projetos de desenvolvimento de software, o termo **estado** é usado para descrever a condição do ambiente de execução em um momento específico no tempo. Conforme seu código executa linha por linha, os valores são armazenados em variáveis. A qualquer momento durante a execução, o estado atual do aplicativo é a coleção de todos os valores armazenados na memória.

Alguns métodos não dependem do estado atual do aplicativo para funcionarem corretamente. Em outras palavras, os **métodos sem estado** são implementados para que possam funcionar sem referenciar ou alterar os valores já armazenados na memória. Os métodos sem estado também são conhecidos como **métodos estáticos**.

Por exemplo, o método `Console.WriteLine()` não depende de nenhum valor armazenado na memória. Ele executa sua função e termina sem afetar o estado do aplicativo de qualquer forma.

Outros métodos, contudo, devem ter acesso ao estado do aplicativo para funcionar corretamente. Em outras palavras, os **métodos com estado** são construídos de maneira que os torna dependentes de valores armazenados na memória por linhas de código anteriores já executadas. Ou eles modificam o estado do aplicativo atualizando valores ou armazenando novos valores na memória. Eles também são conhecidos como **métodos de instância**.

Os métodos com estado (instância) controlam seu estado em _campos_, que são variáveis definidas na classe. Cada nova instância da classe tem sua própria cópia desses campos nos quais o estado é armazenado.

Uma única classe pode dar suporte a métodos com e sem estado. No entanto, quando você precisa chamar métodos com estado, deve primeiro criar uma _instância_ da classe para que o método possa acessar o estado.

## Criando uma instância de uma classe

Uma instância de uma classe é chamada de um _objeto_. Para criar uma instância de uma classe, use o operador __new__. Considere a seguinte linha de código que cria uma instância da classe __Random__ para criar um objeto chamado __dice__:

```csharp
Random dice = new Random();
```

O operador `new` faz várias coisas importantes:

- Primeiro, ele solicita um endereço na memória do computador grande o suficiente para armazenar um novo objeto com base na classe `Random`.
- Ele cria o objeto e o armazena no endereço de memória.
- Retorna o endereço da memória para que possa ser salvo no objeto `dice`.

Desse ponto em diante, quando o objeto `dice` é referenciado no código, o .**NET Runtime** realiza uma pesquisa nos bastidores para dar a ilusão de que você está trabalhando diretamente com o próprio objeto.

Seu código usa o objeto `dice` como uma variável que armazena o estado da classe `Random`. Quando você chama o método `Next()` no objeto `dice`, o método usa o estado armazenado no objeto `dice` para gerar um número aleatório.

A versão mais recente do Runtime do .NET permite que você crie uma instância de um objeto sem ter que repetir o nome do tipo (invocação de construtor com tipo de destino). Por exemplo, o código a seguir criará uma nova instância da classe `Random`:

```csharp
Random dice = new();
```

A intenção é simplificar a legibilidade do código. Você sempre usa parênteses ao escrever uma expressão `new` do tipo de destino.

No nosso exemplo, podemos rodar novamente o dado com o método **Next()** que pode ser chamado em outra variável:

```csharp
Random dice = new Random();
int roll = dice.Next();
```

## Retornando valores

Podemos retornar valores de diferentes formas no C#, onde podemos salvar os valores em uma variável ou apresentar esse resultado direto no console.

```csharp
// Método Next da classe Random
dice.Next(1,7); // Pegar o próximo valor aleatório de 1 á 7

// Podemos salvar em uma variável
int roll = dice.Next(1,7);

// Podemos enviar ao console diretamente
Console.WriteLine(dice.Next(1,7));