#csharp
## Método CompareTo

- Esse método da classe string é utilizado para comparar duas Strings.
- Retorna um valor numérico, se for __0__ significa que são iguais e __1__ se não forem iguais.
- Ele verifica se é _case sensitive_ ,ou seja, caso tenha uma letra diferente de tamanho já considera como não iguais.

```csharp
var text = "Testing";
Console.WriteLine(text.CompareTo("Testing")); // 0
Console.WriteLine(text.CompareTo("testing")); // 1
```

## Método Contains

- Esse método da classe string retorna um valor booleano.
- Ele pode verificar uma string inteira ou se existe uma palavra especifica dentro da string.
- Também é _case sensitive_ , mas pode ser ignorado utilizando __StringComparison__.

```csharp
var text = "Testing";
Console.WriteLine(text.Contains("Testing")); // True
Console.WriteLine(text.Contains("testing")); // False
```

- Para ignorar o _case sensitive_ podemos utilizar o __StringComparison__ chamando o __OrdinalIgnoreCase__.
- Ele vai encontrar a palavra e vai ignorar se ela possui alguma letra maiúscula ou minuscula diferente.

```csharp
var text = "This text is a Test";
Console.WriteLine(text.Contains("test", StringComparison.OrdinalIgnoreCase));
```