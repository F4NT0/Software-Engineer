# Explicação do que é Função
---

Podemos segmentar nosso código em funções.

Funções e Métodos __são a mesma coisa__.

O __Main__ é um método muito utilizado.

A estrutura possui as seguinte partes:
    - Possui um nome.
    - Possui um ou mais parâmetros (variáveis que podemos usar dentro do método).
    - Possui um retorno que deve ser apresentado na estrutura o tipo.

Todos os métodos começam com letras maiúsculas.

## Passos de um método

Primeiro criamos o nosso método passando as informações que queremos:

- Nome do método: MeuMetodo.
- Parâmetros do método: string parâmetro (sempre defina o tipo do parâmetro).
- Tipo de retorno: void (não retorna nada para o projeto).
- Retorno: Console.WriteLine(parametro).

```csharp
static void MeuMetodo(string parametro)
{
    Console.WriteLine(parametro);
}
```

__static__ é um modificador de acesso.

__void__ não retorna nada, mas deve ser explícito a saída.

## Chamando o método

Devemos chamar o método em outro método ou podemos chamar direto no método principal __Main__.

```csharp
static void Main(string[] args)
{
    MeuMetodo("Hello World!");
}
```

## Pontos importantes

Podemos chamar quantos parâmetro quisermos, sempre definindo seu tipo.

Podemos definir o tipo de saída o tipo que quisermos.

Quando não é o tipo __void__ devemos sempre usar a palavra __return__ para retornar as informações para outros métodos. 

```csharp
static string RetornandoMetodo(string nome, int idade, boolean ativo)
{
    return nome + " " + idade + " " + ativo;
}
```

Quando um método tem um tipo, ele deve ser armazenado em uma variável, assim podemos usar a resposta do método no novo método onde ele foi invocado:

```csharp
static void Main(string[] args)
{
    var infos = RetornandoMetodo("Andre",12,true);
    Console.WriteLine(infos);
}
```

## Parâmetros opcionais

Podemos definir um valor default para um parâmetro, caso o cliente não passe essa informação podemos definir um valor inicial para ele.

Todos os valores opcionais devem vir por último na construção de um método

```csharp
// Idade é opcional, caso não passe a idade vai pegar o valor default
static string Dados(string nome, string sobrenome, int idade = 34)
{
    return nome + " " + sobrenome + " " + idade;
}

static void Main(string[] args)
{
    string dados = Dados("Gabriel", "Fanto"); // Saída: Gabriel Fanto 34
    string dados2 = Dados("Gabriel","Fanto",28); // Saída: Gabriel Fanto 28
}
```

## Métodos simples usando arrow functions

Quando um método somente tem uma linha, podemos simplificar utilizando arrow functions.

Arrow Functions em C# é uma forma concisa de escrever métodos ou expressões lambdas, servem para simplificar o código tornando o mais legível e compacto.

usamos o símbolo __=>__ para definir o corpo do método.

```csharp
// Forma Antiga
static string Dados(string nome, string sobrenome, int idade = 34)
{
    return nome + " " + sobrenome + " " + idade;
}

// Usando Arrow Functions
static string Dados(string nome, string sobrenome, int idade = 34) => nome + " " sobrenome + " " + idade
```

## Obervações

Não podemos ter métodos dentro de métodos, não podemos criar dentro de uma Main ou qualquer outro método um método interno.

Devemos ter um retorno, não importa se não passar pela condição de um IF, deve ter um retorno mesmo por default

```csharp
// ERRADO
static string RetornaNome(string nome)
{
    if (nome == "5")
    {
        return nome;
    }
}

// CERTO
static string RetornaNome(string nome)
{
    if (nome == "5")
    {
        return nome;
    }
    return ""; // Caso nennhum caso da condição é aceito
}