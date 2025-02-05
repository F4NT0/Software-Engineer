# Operadores de Incremento e Decremento
---

==Podemos alterar o valor de uma variável a cada vez que é chamado==

No C# como em qualquer linguagem de alto nível podemos alterar o valor de uma variável toda vez que a chamamos em algum processo.

| Simbolo | O que faz       |
| ------- | --------------- |
| **++**  | Incrementa em 1 |
| **--**  | Decrementa em 1 |

- Podemos incrementar o valor __antes__ de chamar a variável

```csharp
int x = 5;
Console.WriteLine(++x); // 6
```

- Podemos incrementar o valor __depois__ de chamar a variável

```csharp
int x = 5;
Console.WriteLine(x++); // 5
Console.WriteLine(x); // 6
```

- Podemos decrementar o valor __antes__ de chamar a variável

```csharp
int x = 5;
Console.WriteLine(--x); // 4
```

- Podemos decrementar o valor __depois__ de chamar a variável

```csharp
int x = 5;
Console.WriteLine(x--); // 5
Console.WriteLine(x); // 4