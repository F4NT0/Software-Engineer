#minimal 

### O que é DTO?

__DTO__ significa __Data Transfer Object__ e é um _Design Pattern_ (Padrão de Projetos) usado para transferir dados entre diferentes camadas de uma aplicação, especialmente entre a camada de apresentação (Front-end) e a camada de serviço (Back-end).

DTOs são simples objetos que não contém lógica de negócios, apenas propriedades para armazenar dados.

Eles servem para esconder estruturas de dados e detalhes de implementação, promovendo menos acoplamento.

### Utilizando Records com DTOs

__Records__ foram adicionados no C# 9 onde é um tipo de dado ideal para definir modelos de dados imutáveis, onde ele entrega funcionalidades que fazem sentido com os DTOs.

Os seguintes fatores ajudam a utilizar _Records_:

-> __Leitura e clareza__: providencia uma sintaxe limpa, fazendo a estrutura mais fácil de entender.
-> __Imutabilidade como padrão__: Imutabilidade garante que a integridade e prevenção de modificações não esperadas ocorram durante a transferência, mas é possível modificar caso necessário.
-> __Métodos Automáticos__: _Records_ automaticamente cria os métodos essenciais como _comparison_, _ToString_ e _deconstruction_, reduzindo o tamanho do código para mais fácil manutenção.

### Criando o nosso DTO

Temos o seguinte Model que implementamos anteriormente:

```csharp
public class Product 
{
	[Key]
	public long Id { get; set; }
        
	[StringLength(50)]
	[Required]
	public required string Name { get; set; }

	[Range(0, double.MaxValue)]
	[Required]
	public double Price { get; set; }
}
```

Agora vamos construir o DTO dele para utilizarmos em nosso projeto.

Para isso vamos criar um novo diretório chamado __DTOs__

![[15-dto-folder.png]]

Agora vamos criar uma nova classe chamada __ProductDTO__ que vai receber valores do Model __Product__ 

![[15-dto-class.png]]

![[15-dto-class2.png]]

Depois de criar a nova classe iremos definir como um _Record_ e iremos definir quais valores iremos utilizar do Model:

-> Usaremos o __Id__, __Name__ e __Price__.

Nosso Record ficará assim:

```csharp
public record ProductDTO
{
    public long Id { get; init; }
    public required string Name { get; init; }
    public double Price { get; init; }
}
```

__init__ significa que essa propriedade do _Record_ somente pode ser inicializada na criação e não pode ser alterado depois (como usamos o set no Model, ele pode ser alterado, o init evita isso).