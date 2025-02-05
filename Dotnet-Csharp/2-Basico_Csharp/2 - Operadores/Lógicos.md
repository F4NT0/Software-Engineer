# Operadores Lógicos
---

Retorna valores booleanos

Usado para operações condicionais

- `&&` = AND lógico
    - Todas as condições devem ser verdadeiras
- `||` = OR lógico
    - Se pelo menos uma for verdadeira
- `!` = NOT lógico
    - Nega o valor, se for true vira false e vice versa

```csharp
int x = 12;
bool valor = (x > 25) && (x < 40); // False
bool valor = (x > 25) || (x < 40); // True
bool valor = !(x > 25) && (x < 40); // True