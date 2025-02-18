#DS
## O que é uma Lista

- Lista é uma coleção de elementos que possuem uma Relação de ordem linear entre eles.
- Operações que se podem se fazer com Listas:
	- Inserção -> **add**
    - Remoção -> **remove**
    - Consulta sobre o valor de um elemento -> **get**
    - Alteração de um elemento -> **set**
- Uma lista, diferente de um arranjo(array),pode variar de tamanho, podendo aumentar ou diminuir
- Uma implementação bem conhecida é a __ArrayList__.

## Entendendo ArrayList
---

- Para implementar uma ArrayList, se deve importar o pacote do java:

```java
import java.util.ArrayList;
```

- Construtores do ArrayList:

```java
//para criar um ArrayList de posição definida(10 posições)
ArrayList<tipo> nomedoArrayList = new ArrayList<tipo>(); 

//para criar um ArrayList onde se define o tamanho
ArrayList<tipo> nomeArrayList = new ArrayList<tipo>(20); //criamos com 20 posições
```

- Para adicionar elementos ao ArrayList:
    - Utilizaremos o Método **add()** para adicionar valores e objetos ao ArrayList

```java
//cria-se um ArrayList:
ArrayList<Integer> numero = new ArrayList<Integer>(10);

//adicionar valores de variáveis direto no ArrayList

int valor1 = 5; //valor criado

numero.add(valor1);
```

- Para saber e utilizar o tamanho do ArrayList
    - Podemos usar o tamanho para controlar a pesquisa de informações
    - Utilizamos o Método **size()** para retornar o tamanho do ArrayList

```java
//iniciando um ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>(20);

//pegando o valor do ArrayList:
numero.size() //retorna o tamanho, que é 20
```

- Para pegarmos um valor dentro da ArrayList
    - podemos pegar um valor unico dentro de um ArrayList
    - podemos pegar todos os valores dentro de um ArrayList
    - Para isso usamos o Método **Get()** do ArrayList

```java
//iniciando um ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>();

int valor1 = 5;
int valor2 = 10;
int valor3 = 20;

numero.add(valor1);
numero.add(valor2);
numero.add(valor3);

//o Parâmetro do Get é a posição que deseja pegar o valor
//FORMA 1: pegar um valor de dentro do ArrayList
int saida = numero.get(1); //saida = 5

//FORMA 2: pegar todos os valores de dentro do ArrayList
for(int i = 0; i < numero.size() ; i++){ //vai varrer todo o tamanho do vetor
 numero aux = numero.get(i); //o valor do aux muda a cada posição
 System.out.println(aux); //vai saindo o valor do aux cada vez
}
//Saida: 
// 5
// 10
// 20
```

- Para alterar um valor de uma posição
    - podemos alterar o valor de uma posição a qualquer momento
    - Usamos o Método **set()** para fazermos isso
    - o método necessita que se diga a posição e qual valor que sera adicionado

```java
//iniciando uma ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>();

//colocando valores
int valor1 = 5;
int valor2 = 10
int valor3 = 20;

numero.add(valor1);
numero.add(valor2);
numero.add(valor3);

//alterando um valor de dentro do ArrayList
int valor4 = 30;
numero.set(1,valor4); // sai o valor1 e entra o valor4
```

- Remoção de um elemento de um ArrayList
    - se pode remover um elemento de uma posição especifica
    - todos os elementos dessa primeira opção depois são subtraidos um valor de seus indices
    - se pode remover um elemento de uma posição e o programa responde true ou false se tinha o elemento
    - utiliza os Métodos de **remove()**, que são dois que existem no pacote ArrayList

```java
//iniciando um ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>();

//iniciando os valores no ArrayList
int valor1 = 5;
int valor2 = 10;
int valor3 = 20;
numero.add(valor1);
numero.add(valor2);
numero.add(valor3);
//tamanho nesse momento do ArrayList
numero.size() //3

//removendo o valor da primeira posição
numero.remove(1);
numero.size(); //2

//removendo um valor especifico
boolean removeu = numero.remove(20); 
//vai procurar e ver se tem, se tiver = true, senão = false
numero.size(); //1
```

- Como descobrir a posição de um valor dentro da lista
    - Podemos descobrir a primeira posição desse valor que deseja descobrir
    - Podemos descobrir a ultima vez que esse valor foi adicionado no ArrayList
    - utilizamos para saber o primeiro usando o Método **indexOf()**
    - utilizamos para saber o ultimo usando o Método **lastIndexOf()**

```java
//iniciando um ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>();

//adicionando valores dentro do ArrayList
int valor1 = 5;
int valor2 = 10;
int valor3 = 5;
int valor4 = 20;

//procurando o valor 5:
//procurando a primeira vez que aparece
int indice = numero.indexOf(5); // indice = 0 
//como a primeira vez foi na primeira posição, então o indice é igual a Zero
int indice2 = numero.lastIndexOf(5); //indice = 2
//a ultima vez que o 5 foi adicionado foi na posição 2, que é a terceira posição
```

- Verificar se tem um elemento especifico dentro do ArrayList
    - Podemos saber se tem um elemento usando Método **contains()**

```java
//Criando um ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>();
//adicionando os valores
int valor1 = 5;
numero.add(valor1);
boolean resultado = numero.contains(5);
//se o elemento existir dentro do ArrayList, ele retorna o valor boolean true
```

- Verificar se a lista esta Vazia ou não
    - o Método **isEmpty()** serve para saber se existem valores dentro do ArrayList

```java
//iniciando um ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>();
//verificando se tem valores
boolean resultado = numero.isEmpty();
//ira retornar true se não tiver valores dentro do ArrayList
```

- Remover todos os Valores dentro do ArrayList
    - Podemos remover tudo com o Método **clear()**

```java
//iniciando um ArrayList
ArrayList<Integer> numero = new ArrayList<Integer>();
//adicionando valores:
int valor1 = 5;
int valor2 = 10;
int valor3 = 20;
numero.add(valor1);
numero.add(valor2);
numero.add(valor3);

//para deletar tudo
numero.clear();
```