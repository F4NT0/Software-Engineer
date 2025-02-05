# Entendo vetores (arrays)
---

As arrays podem ser usadas para armazenar vários valores do mesmo tipo em uma só variável. Os valores armazenados em uma array geralmente estão relacionados entre si. Por exemplo, uma lista de nomes de alunos pode ser armazenada em uma array de cadeia de caracteres chamada `students`.

Seu trabalho no departamento de segurança se concentra em encontrar um padrão para os pedidos fraudulentos. Você deseja que seu código revise os pedidos de clientes anteriores e identifique marcadores associados a pedidos fraudulentos. Sua empresa espera que os marcadores possam ser usados no futuro para identificar possíveis ordens de compra fraudulentas antes de serem processadas. Como você nem sempre sabe com antecedência quantos pedidos será preciso analisar, não é possível criar variáveis individuais para conter cada ID de pedido. Como você pode criar uma estrutura de dados para conter diversos valores relacionados?

Neste exercício, você irá usar arrays para armazenar e analisar uma coleção de IDs de pedido.

## O que é uma array?

Uma array é uma coleção de elementos de dados individuais acessíveis por meio de um único nome de variável. Use um índice numérico baseado em zero para acessar cada elemento de uma array. As arrays permitem que você crie uma coleção de valores de dados que compartilhe uma finalidade ou características comuns em um único nome de variável para facilitar o processamento.

## Como declarar arrays e acessar os elementos delas

Uma array é um tipo especial de variável que pode conter vários valores do mesmo tipo de dados. A sintaxe da declaração é ligeiramente diferente para uma array porque você precisa especificar o tipo de dados e o tamanho da array.

### Declarar uma nova array

1. Para declarar uma nova array de cadeias de caracteres que possa conter três elementos, insira o seguinte código:
```csharp
string[] fraudulentOrderIDs = new string[3];
```

2. Reserve um minuto para analisar seu código.

    O operador `new` cria uma instância de uma array na memória do computador que pode conter três valores de cadeia de caracteres. Para saber mais sobre a palavra-chave `new`, confira o módulo "Chamar métodos da Biblioteca de Classes .NET usando C#".
    
    Observe que o primeiro conjunto de colchetes `[]` simplesmente indica ao compilador que a variável de nome `fraudulentOrderIDs` é uma array. Já o segundo conjunto de colchetes `[3]` indica o número de elementos que a array conterá.
    
     Observação
    
    Esse exemplo demonstra como declarar uma array de cadeias de caracteres. No entanto, é possível criar arrays de qualquer tipos de dados – inclusive os tipos primitivos, como `int` e `bool`, e tipos mais complexos como classes. Este exemplo usa a simplicidade das cadeias de caracteres para minimizar o número de novas ideias que você precisa entender para começar.
    

### Atribuir valores aos elementos de uma array

A esta altura, você já declarou uma array de cadeias de caracteres, mas todos os elementos dela estão vazios. Para acessar um elemento de uma array, use um índice numérico baseado em zero dentro de colchetes. Você pode atribuir valores aos elementos da array usando `=`, como se fosse uma variável normal.

1. Para atribuir valores de IDs de pedido aos elementos da sua array `fraudulentOrderIDs`, atualize o código da seguinte maneira:
```csharp
    string[] fraudulentOrderIDs = new string[3];
    
    fraudulentOrderIDs[0] = "A123";
    fraudulentOrderIDs[1] = "B456";
    fraudulentOrderIDs[2] = "C789";
```
    
2. Reserve um minuto para analisar seu código.
    
    Observe que você usa o nome da array para acessar os elementos dela. Cada elemento é acessado individualmente, especificando dentro dos colchetes o número do índice, que começa no zero.
    
    Como sua array é declarada como uma array de cadeia de caracteres, os valores atribuídos aos elementos da array devem ser cadeias de caracteres. Nesse cenário, você está atribuindo IDs de pedido aos elementos da array.
    
### Tentar usar um índice fora dos limites da array

Talvez não pareça intuitivo, a princípio, mas é importante lembrar que você declara o número de elementos da array. No entanto, você acessa os elementos da array começando no zero. Portanto, para acessar o segundo item da array, você usa o índice `1`.

É muito comum que iniciantes se esqueçam que o índice das arrays começa no zero e acabar tentando acessar um elemento que não existe. Se você cometer esse erro, será gerada uma exceção de Runtime informando que você tentou acessar um elemento que está fora dos limites da array.

Para "interromper" intencionalmente seu aplicativo, tente acessar o quarto elemento da array usando o valor de índice `3`.

1. Na parte inferior do seu arquivo de código, insira a seguinte linha:
```csharp
    fraudulentOrderIDs[3] = "D000";
```

2. Verifique se o seu código corresponde ao seguinte exemplo:

```csharp
    string[] fraudulentOrderIDs = new string[3];
    
    fraudulentOrderIDs[0] = "A123";
    fraudulentOrderIDs[1] = "B456";
    fraudulentOrderIDs[2] = "C789";
    fraudulentOrderIDs[3] = "D000";
```
    
3. No prompt de comando do Terminal, para compilar seu código, digite **dotnet build** e pressione Enter.
    
    Você deverá ver a seguinte mensagem:
    
    ```text
    Build succeeded.        
        0 Warning(s)        
        0 Error(s)
    ```
    
4. No prompt de comando do Terminal, para executar seu código, digite **dotnet run** e pressione Enter.
    
    Ao executar o aplicativo, você recebe a seguinte mensagem de erro de Runtime:
    
```text
    Unhandled exception. System.IndexOutOfRangeException: Index was outside the bounds of the array.     
       at Program.<Main>$(String[] args) in C:\Users\someuser\Desktop\CsharpProjects\TestProject\Program.cs:line 6
```
    
	Observe as seguintes partes do erro:
    
    - Mensagem de erro: `System.IndexOutOfRangeException: Index was outside the bounds of the array.`
    - Local do erro: `Program.cs:line 6`
    
5. Comente a linha que gerou o erro de Runtime.
    
```csharp
    // fraudulentOrderIDs[3] = "D000";
```

Você viu como atribuir um valor a um elemento da array. Agora, veja como acessar um valor que está sendo armazenado em um elemento da array.

### Recuperar valores dos elementos de uma array

Acessar o valor de um elemento da array funciona da mesma forma que atribuir um valor a um elemento da array. Basta especificar o índice do elemento cujo valor você deseja recuperar.

1. Para escrever na saída o valor de cada ID de Pedido fraudulento, atualize seu código da seguinte maneira:
    
```csharp
    string[] fraudulentOrderIDs = new string[3];
    
    fraudulentOrderIDs[0] = "A123";
    fraudulentOrderIDs[1] = "B456";
    fraudulentOrderIDs[2] = "C789";
    // fraudulentOrderIDs[3] = "D000";
    
    Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
    Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
    Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");
```
    
2. No prompt de comando do Terminal, digite **dotnet run** e pressione Enter.
    
    Você deverá ver a seguinte mensagem:
    
    ```
    First: A123
    Second: B456
    Third: C789
    ```

### Reatribuir o valor de uma array

Os elementos de uma array são como qualquer outra variável. Você pode atribuir, recuperar e reatribuir valores a cada elemento da array.

1. Ao final do seu arquivo de código, para reatribuir e imprimir na saída o valor do primeiro elemento da array, insira o seguinte código:
    
```csharp
    fraudulentOrderIDs[0] = "F000";
    
    Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}");
```

2. Verifique se o seu código corresponde ao seguinte exemplo:
    
```csharp
    string[] fraudulentOrderIDs = new string[3];
    
    fraudulentOrderIDs[0] = "A123";
    fraudulentOrderIDs[1] = "B456";
    fraudulentOrderIDs[2] = "C789";
    // fraudulentOrderIDs[3] = "D000";
    
    Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
    Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
    Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");
    
    fraudulentOrderIDs[0] = "F000";
    
    Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}");
```
    
3. No prompt de comando do Terminal, digite **dotnet run** e pressione Enter.
    
    Você deverá ver a seguinte mensagem
    ```
    First: A123
    Second: B456
    Third: C789
    Reassign First: F000
    ```
    

### Inicializar uma array

Você pode inicializar uma array durante a declaração, assim como faria com uma variável comum.

1. Comente as linhas em que você declara a variável `fraudulentOrderIDs`.
    
    Você pode usar um comentário de várias linhas (`/* ... */`) para comentar a declaração de `fraudulentOrderIDs` e as linhas usadas para atribuir valores aos elementos da array.
    
2. Para declarar a array e inicializar os valores em uma única instrução, insira o seguinte código:

    
```csharp
    string[] fraudulentOrderIDs = [ "A123", "B456", "C789" ];
```
    
    Este exemplo usa a sintaxe de **expressão Collection**, que foi introduzida no C# 12.
    
    Você também pode ver uma sintaxe mais antiga usada para inicializar uma array.
    
```csharp
    string[] fraudulentOrderIDs = { "A123", "B456", "C789" };
```
    
    Observe que essa sintaxe mais antiga utiliza chaves `{}` para envolver os valores da array. Ambas as sintaxes são válidas.
    
3. Verifique se o seu código corresponde ao seguinte exemplo:
    
```csharp
    /*
    string[] fraudulentOrderIDs = new string[3];
    
    fraudulentOrderIDs[0] = "A123";
    fraudulentOrderIDs[1] = "B456";
    fraudulentOrderIDs[2] = "C789";
    // fraudulentOrderIDs[3] = "D000";
    */
    
    string[] fraudulentOrderIDs = [ "A123", "B456", "C789" ];
    
    Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
    Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
    Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");
    
    fraudulentOrderIDs[0] = "F000";
    
    Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}");
```
    
4. Reserve um minuto para analisar a instrução de declaração.
    
    Observe que essa sintaxe é compacta e fácil de ler. Ao executar o aplicativo, não deve haver alterações na saída.
    
7. No prompt de comando do Terminal, digite **dotnet run** e pressione Enter.
    
    Você deve ver a mesma mensagem que antes:
    
    ```
    First: A123
    Second: B456
    Third: C789
    Reassign First: F000
    ```
    

### Usar a propriedade Length da array

Dependendo de como a array é criada, talvez você não saiba com antecedência quantos elementos ela contém. Para determinar o tamanho de uma array, você pode usar a propriedade `Length`.

A propriedade `Length` de uma array não começa no zero.

1. Ao final do seu arquivo de código, para relatar o número de pedidos fraudulentos, insira o seguinte código:
    
```csharp
    Console.WriteLine($"There are {fraudulentOrderIDs.Length} fraudulent orders to process.");
```
    
    Esse código usa a propriedade `Length` da array, um inteiro, para retornar o número de elementos da sua array `fraudulentOrderIDs`.
    
2. Verifique se o seu código corresponde ao seguinte exemplo:
    
```csharp
    /*
    string[] fraudulentOrderIDs = new string[3];
    
    fraudulentOrderIDs[0] = "A123";
    fraudulentOrderIDs[1] = "B456";
    fraudulentOrderIDs[2] = "C789";
    // fraudulentOrderIDs[3] = "D000";
    */
    
    string[] fraudulentOrderIDs = [ "A123", "B456", "C789" ];
    
    Console.WriteLine($"First: {fraudulentOrderIDs[0]}");
    Console.WriteLine($"Second: {fraudulentOrderIDs[1]}");
    Console.WriteLine($"Third: {fraudulentOrderIDs[2]}");
    
    fraudulentOrderIDs[0] = "F000";
    
    Console.WriteLine($"Reassign First: {fraudulentOrderIDs[0]}");
    
    Console.WriteLine($"There are {fraudulentOrderIDs.Length} fraudulent orders to process.");
```
    
3. Salve as alterações no arquivo **Program.cs** e execute o aplicativo.
    
    Você deve ver o seguinte resultado:
    
```
    First: A123
    Second: B456
    Third: C789
    Reassign First: F000
    There are 3 fraudulent orders to process.
```