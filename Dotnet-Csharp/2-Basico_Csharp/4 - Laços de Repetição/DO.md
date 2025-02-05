# Laço de Repetição DO
---

==Verifica a condição após ter executado pelo menos uma vez==

Palavras reservadas __do while__

Essa estrutura checa a condição do while __DEPOIS__ de executar

Estrutura base de um DO WHILE:

```csharp
var valor = 0;
do
{
    Console.WriteLine(valor);
    valor++;
} while (valor <= 5);

// SAÍDA
// 0
// 1
// 2
// 3
// 4
// 5
```