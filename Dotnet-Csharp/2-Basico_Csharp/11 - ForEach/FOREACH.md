# Utilizando ForEach
---

## Executar um loop em uma matriz usando o foreach

Essa instrução **foreach** fornece uma maneira simples e limpa de iterar através dos elementos de uma matriz. A instrução **foreach** processa os elementos da matriz em ordem de índice crescente, começando no índice 0 e terminando no índice Comprimento - 1. Ela usa uma variável temporária para manter o valor do elemento da matriz associado à iteração atual. Cada iteração executará o bloco de código localizado abaixo da declaração **foreach**.

Confira um exemplo simples:

```csharp
string[] names = { "Rowena", "Robin", "Bao" };
foreach (string name in names)
{
    Console.WriteLine(name);
}
```

Abaixo da palavra-chave **foreach**, o bloco de código que contém `Console.WriteLine(name);` será executado uma vez para cada elemento da matriz `names`. Como o runtime do .NET executa um loop em cada elemento da matriz, o valor armazenado no elemento atual da matriz `names` será atribuído à variável temporária `name` para facilitar o acesso dentro do bloco de código.

Se você executar o código, verá o resultado a seguir.

```
Rowena
Robin
Bao
```

Use a instrução `foreach` para criar uma soma de todos os itens disponíveis em cada compartimento do depósito.

### Criar e inicializar uma matriz de int

1. Para criar uma matriz do tipo `int` que armazene o número de produtos prontos em cada compartimento, insira o seguinte código:
    
```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
```

### Adicionar uma instrução foreach para a iteração na matriz

1. Para criar uma instrução `foreach` que faça a iteração por cada elemento da matriz `inventory`, digite o seguinte código:
    
```csharp
    foreach (int items in inventory)
    {
    
    }
```
    
    Observe que a instrução `foreach` atribui temporariamente o valor do elemento da matriz atual a uma variável `int` chamada `items`.
    
2. Verifique se o código corresponde ao seguinte:
    
```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    
    foreach (int items in inventory)
    {
    
    }
```

### Adicionar uma variável para somar o valor de cada elemento na matriz

1. Posicione o cursor na linha de código em branco acima da instrução `foreach`.
    
2. Para declarar uma nova variável que represente a soma de todos os produtos prontos no depósito, insira o seguinte código:
    
```csharp
    int sum = 0;
```
    
    Lembre-se de declarar a variável **fora** da instrução foreach.
    
3. Posicione o cursor dentro do bloco de código da instrução **foreach**.
    
4. Para adicionar o valor atual armazenado em `items` à variável `sum`, digite o seguinte código:
    
```csharp
    sum += items;
```
    
5. Verifique se o código corresponde ao seguinte:
    
```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    int sum = 0;
    foreach (int items in inventory)
    {
        sum += items;
    }
```
    
### Exibir o valor final da soma

1. Crie uma linha de código em branco abaixo do bloco de código da instrução `foreach`.
    
2. Para relatar a soma final dos itens no estoque, insira o seguinte código:
    
```csharp
    Console.WriteLine($"We have {sum} items in inventory.");
```
    
3. Verifique se o código corresponde ao seguinte:
    
```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    int sum = 0;
    foreach (int items in inventory)
    {
        sum += items;
    }
    
    Console.WriteLine($"We have {sum} items in inventory.");
```
    
6. No prompt de comando do Terminal, digite **dotnet run** e pressione Enter.
    
    ```
    We have 1775 items in inventory.
    ```

### Criar uma variável para manter o número do compartimento atual e exibir o total acumulado

Para cumprir o requisito final do projeto de relatório de estoque, crie uma variável que conterá a iteração atual da instrução `foreach` a fim de permitir a exibição do compartimento e da contagem de itens prontos nele, além do total acumulado de todos os itens de compartimentos contabilizados até agora.

1. Crie uma linha de código em branco acima da instrução `foreach`.
    
2. Para declarar a variável `int` chamada `bin` inicializada para `0`, insira o seguinte código:
    
```csharp
    int bin = 0;
```
    
    Você usará `bin` para armazenar o número do compartimento que tem um estoque sendo processado no momento.
    
3. Dentro do bloco de código `foreach`, para incrementar `bin` a cada vez que o bloco de código for executado, insira o seguinte código:

```csharp
    bin++;
```
    
    Observe que você usa o operador `++` para incrementar o valor da variável em 1. Esse é um atalho para `bin = bin + 1`.
    
4. Para relatar o número do compartimento, o número de produtos prontos nele e o total acumulado de produtos prontos, insira o seguinte código dentro do bloco de código `foreach`, após `bin++;`:
    
```csharp
    Console.WriteLine($"Bin {bin} = {items} items (Running total: {sum})");
```
    
    Esse código usará a variável contadora `bin`, a variável `foreach` temporária `items` e a variável `sum` para relatar o estado atual do estoque em uma mensagem bem formatada.
    
5. Verifique se o código corresponde ao seguinte:
    
```csharp
    int[] inventory = { 200, 450, 700, 175, 250 };
    int sum = 0;
    int bin = 0;
    foreach (int items in inventory)
    {
        sum += items;
        bin++;
        Console.WriteLine($"Bin {bin} = {items} items (Running total: {sum})");
    }
    Console.WriteLine($"We have {sum} items in inventory.");
```
    
6. Salve as alterações no arquivo Program.cs e execute o aplicativo.
    
    Você deve ver o seguinte resultado:
    
    ```
    Bin 1 = 200 items (Running total: 200)
    Bin 2 = 450 items (Running total: 650)
    Bin 3 = 700 items (Running total: 1350)
    Bin 4 = 175 items (Running total: 1525)
    Bin 5 = 250 items (Running total: 1775)
    We have 1775 items in inventory.
