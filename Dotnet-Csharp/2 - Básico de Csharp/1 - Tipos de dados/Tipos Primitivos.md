#csharp
# Tipos primitivos de dados
---

- nome em inglês: `built-in types`
- Armazenam o valor e não a referência para um item na memória
- São classificados em:
    - Tipos Simples (Simple Types)
    - Enumeradores (Enums)
    - Estruturas (Structs)
    - Tipos Nulos (Nullable Types)

## Byte

- O tipo `byte` são 8 bits, só aceita valores positivos
- O tipo `sbyte` permite valores negativos (quando possui o símbolo _-_ são chamados de signed)
- `byte` (8 bits) = de 0 até 255
- `sbyte` (8 bits) = de -128 até 127

```csharp
byte meuByte = 127;
```

## Números inteiros

- `short`
    - tem 16 bits
    - de -32768 até 32767
- `ushort` 
    - pega somente valores positivos
    - tem 16 bits
    - de 0 até 65535
- `int`
    - tem 32 bits
    - de -2147483648 até 2147483647
- `uint`
    - pega somente valores positivos
    - tem 32 bits
    - 0 até 4294967295
- `long`
    - tem 64 bits
    - de -9223372036854775808 até 9223372036854775807
- `ulong`
    - pega somente valores positivos
    - tem 64 bits
    - de 0 até 18446744073709551615

```csharp
uint idate = 25;
short idade = 25;
long idade = 25;
```

## Números reais

- `float`
    - Pode ser positivo ou negativo
    - Aceita no máximo 32 bits
    - de **-3.402823e38** até **3.402823e38**
    - Ex: 23,5 é mostrado como **23.5f**
    - Devemos colocar um f no final do valor
- `double`
    - Pode ser positivo ou negativo
    - Aceita no máximo 64 bits
    - de **-1.79769313486232e308** até **1.79769313486232e308**
    - Tipo padrão que é pego de um valor decimal
    - Ex: 23,5 é mostrado como **23.5**
- `decimal`
    - Pode ser positivo e negativo
    - Aceita no máximo 128 bits
    - de **1.0 x 10e-28** até **7.9 x 10e28**
    - Ex: 23,5 é mostrado como **23.5m**
    - Devemos colocar um m no final do valor

```csharp
double salario = 2.500;
var salario = 2.500; // var pega automaticamente o double
float salario = 2.500f;
decimal salario = 2.500m;
```

## Booleanos

- Armazena somente __true__ ou __false__
- usamos a palavra reservada __bool__ como booleano

```csharp
bool usuarioCadastrado = false;
bool usuarioCadastrado = true;
var usuarioCadastrado = false; // Já reconhece como Booleano
```

## Char

- Armazena somente um caractere no formato unicode
- usamos a palavra reservada __char__ para definir o valor
- atribuimos o valor de um char com aspas simples
- Possui 16 bits que entra em qualquer caractere

```csharp
char valor = 'a';
var valor = 'd'; // Já reconhece como um Char
```

## String

- Armazena uma cadeia de caracteres
- Definido pela palavra reservada __string__
- O tamanho depende do tamanho do string
- é atribuido utilizando aspas duplas

```csharp
string umaLetra = "C"; // podemos colocar uma letra só
string variasLetras = "Caracteres";
var variasLetras = "1234"; // Já reconhece como String
```

## Var

- Utilizado para substituir o nome de um tipo
- Será definido o tipo do primeiro valor atribuido, não altera durante o projeto
- Se utiliza o var quando já dominar os tipos existentes
- Devemos principalmente usar quando criamos tipos especiais, assim evitamos de reutilizar várias vezes nomes longos

```csharp
// Com tipos especiais
IEnumerable<MeuTipoComplexo> aluno = new IEnumerable<MeuTipoComplexo>();
var aluno = new IEnumerable<MeuTipoComplexo>();
```

## Object

- Tipo genérico que recebe qualquer valor ou objeto
- Caso não saiba o tipo da informação ou sela seja de vários tipos diferentes
- Não possui intelisense (ajuda de editores) por ser um tipo desconhecido
- Evite usar Object se não for para classes genéricas ou desnecessário
- Usamos quando não queremos definir um valor inicial

```csharp
object quantidade; // podemos definir sem valores
quantidade = 1;
quantidade = 2.5; // como recebe qualquer coisa, podemos alterar seu valor que o programa não reclama
```

## Nullable Types

- __Null__ significa que o valor é vazio ou inexistente
- Diferente de zero ou string vazia
- Tipos primitivos ou complexos podem receber o valor null
- O tipo deve ser marcado como Nullable Type
- Podemos atribuir __null__ a um objeto
- Usamos __?__ junto com o tipo para definir que ele é Nullable Types
- Se uma chamada a um valor nulo for feito, vai dar um erro no projeto

```csharp
int? idade = null;
byte? valor = 123;
```

## Alias

- É um apelido que todos os tipos do .NET possuem.
- Todos os tipos que foram mostrados até agora são Alias.
- Como o C# é __Case Sensitive__ , não importa qual usarmos, mas recomendado usar os alias.

| Alias  | Tipo Original |
| ------ | ------------- |
| string | System.String |
| int    | Int32         |

## Valores Padrões

- Todos os tipos primitivos do C# já vem com um valor default
- nunca são iniciados como nulos
- Se nenhum valor for informado, seu valor padrão será usado

| Tipo    | Valor Padrão |
| ------- | ------------ |
| int     | 0            |
| float   | 0            |
| decimal | 0            |
| bool    | false        |
| char    | '0'          |
| string  | ""           |
