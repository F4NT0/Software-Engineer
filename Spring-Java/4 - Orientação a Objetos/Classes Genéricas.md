#OO
## Convenção

- Programação genérica consiste na criação de estruturas que podem ser reutilizadas em vários tipos diferentes no projeto.
- Existem estruturas que podem ser instanciadas para coleções de diferentes tipos de dados.
- O tipo do objeto criado pela classe vai ser verificado durante a compilação do programa.
- Serve para evitar de escrever código repetitivo e sujeito a erros de execução do uso excessivo de conversores de tipos (casts).
- Usa-se letras maiúsculas individuais para especificar o parâmetro.

| Letra do tipo | Significado                |
| ------------- | -------------------------- |
| E             | Elemento de uma coleção    |
| K             | Chave de um mapa           |
| V             | Valor de um mapa           |
| T             | Tipo genérico              |
| S,U           | Tipos genéricos adicionais |
Todos os parâmetros de tipos são declarados entre _<_ e _>_ ao lado do nome da classe.
Uma vez declarado, um parâmetro de tipo pode ser usado no lugar de qualquer tipo de dado.

## Classe genérica simples usando o Tipo genérico

O tipo genérico é a letra _T_ que pode armazenar qualquer tipo de objeto, o tipo é especificado quando a classe é instanciada.

```java
public class Caixa<T>
{
	private T conteudo;

	public T getConteudo()
	{
		return conteudo;
	}

	public void setConteudo(T conteudo)
	{
		this.conteudo = conteudo;	
	}
}
```

## Classe genérica do tipo chave-valor

Utilizamos o _K_ como a chave(key) e o _V_ como o valor (value) para podermos controlar não importa o tipo a chave e o valor de algum objeto.

```java
public class Par<K, V>
{
	private K chave;
	private V valor;

	public Par(K chave, V valor)
	{
		this.chave = chave;
		this.valor = valor;
	}

	public K getChave()
	{
		return chave;
	}

	public V getValor()
	{
		return valor;
	}
}
```

## Classe genérica com limite de tipos

Podemos definir quais tipos um genérico pode utilizar para evitar que ocorra erros devido a algum tipo não definido, para isso devemos usar o _extends_ dos tipos possíveis de usar no genérico.

```java
public class NumeroCaixa<T extends Number>
{
	private T numero;

	public T getNumero()
	{
		return numero;
	}

	public void setNumero(T numero)
	{
		this.numero = numero;
	}
}
```

Nesse exemplo somente podem ser usados subclasses da classe Number como __Integer__, __Double__, etc...

## Métodos Genéricos

Podemos construir métodos que utilizam o genérico para não precisar definir o tipo, como por exemplo imprimir um array que não sabemos o tipo.

```java
public class Util
{
	public static <T> void imprimeArray(T[] array)
	{
		for (T elemento : array)
		{
			System.out.print(elemento + " ");
		}
		System.out.println();
	}
}
```

## Método genérico usando Wildcard

_Wildcard_ é o nome que damos ao uso do caractere __?__ onde é usado nos genéricos para representar um tipo desconhecido. Eles são úteis quando você deseja escrever métodos que podem operar em coleções de objetos de diferentes tipos.

```java
public void imprimirColecao(Collection<?> colecao)
{
	for (Object elemento : colecao)
	{
		System.out.print(elemento + " ");
	}
	System.out.println();
}
```
