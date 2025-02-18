#OO
## Conteúdo
---
- [[#Partes de uma classe Orientada a Objetos|Partes de uma classe Orientada a Objetos]]
	- [[#Partes de uma classe Orientada a Objetos#Método Construtor:|Método Construtor:]]
	- [[#Partes de uma classe Orientada a Objetos#Métodos Getters|Métodos Getters]]
	- [[#Partes de uma classe Orientada a Objetos#Métodos Setters|Métodos Setters]]
	- [[#Partes de uma classe Orientada a Objetos#Método toString|Método toString]]

## Partes de uma classe Orientada a Objetos

Uma classe Java possui os seguintes métodos:
- Método Construtor
- Métodos Getters
- Métodos Setters
- Método toString

### Método Construtor:

- Um método construtor é um método que é utilizado para **iniciar um objeto dessa classe**.
- quando você inicia um método construtor em outra classe se chama **Instanciar um objeto**.
- esse método pode ter _quantos parâmetros forem necessários_.
- esses parâmetros são as variareis necessárias para iniciar o método construtor.
- quando se inicia uma variável de objeto, será um objeto criado anteriormente que pode ser chamado nessa classe
- o **this** serve para podermos utilizar o nome da variável mais de uma vez, sendo usado no construtor para que o valor de entrada no construtor seja armazenado na variável de mesmo nome.

```java
// Método construtor
public nomeDaClasse(parametros){
   this.parametro = parametro;
}

//iniciando em outras classes:
nomeDaClasse novo1 = new nomeDaClasse(valor do parametro); 
```

Exemplo real:

```java
public class Carro
{
	private String marca;
	
	public Carro(String marca)
	{
		this.marca = marca;
	}
}

public class App
{
	public static void main(String[] args)
	{
		Carro novoCarro = new Carro("Volvo");
	}
}
```

### Métodos Getters

Todos os atributos de uma classe são __privadas__ , ou seja , não podem ser chamadas de fora da classe, por isso temos os métodos _getters_ que pegam esses valores e os chamam para fora da classe em qualquer outra classe desejada.

```java
// Exemplo de um inteiro
private long iCard;

// Método Getter
public Long getiCard()
{
	return iCard;
}
```

- Todos os atributos devem ter o método Getter se deseja que ele seja visto externamente.
- Os getters não necessitam ter parâmetros.
- retorna somente o atributo, não faz nenhuma lógica.

### Métodos Setters

Esses métodos servem para __alterar__ o valor de um dos atributos, assim podemos controlar os valores que entram e saem de uma classe.

Como os atributos são privados, somente utilizando os _setters_ podemos alterar o valor de um atributo.

Podemos utilizar o _this_ aqui também para não precisar alterar o nome do atributo.

```java
private long iCard;

// Método Setter
public void setiCard(long iCard)
{
	this.iCard = iCard;
}
```

### Método toString

Esse método serve para construir uma saída personalizada para outras classes.

Como já existe um método de mesmo nome no Java, toda vez que for utilizar ele deve utilizar a anotação __@Override__ para poder sobrescrever o método como deseja.

```java
@Override
public String toString()
{
	return ""; // Coloque aqui como deseja visualizar os dados
}
```

