# Operadores condicionais
---

Operador condicional é um sistema de uma linha para verificar dois valores usando os operadores __?__ e __:__ para fazer a seguinte estrutura:

```csharp
<condição> ? <se for true, retorna esse valor> : <se for false, retorna esse valor>
```

Vamos ver o seguinte exemplo:

```csharp
int saleAmount = 1001;

int discount = saleAmount > 1000 ? 100 : 50;
```

No exemplo acima, caso o valor de __saleAmount__ for maior que 1000 ele vai salvar na variável __discount__ o valor de 100, caso não seja maior que 1000 ele vai adicionar o valor de 50.