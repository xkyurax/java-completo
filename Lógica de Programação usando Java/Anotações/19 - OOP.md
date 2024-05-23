#### Classe
* **É um tipo estruturado que pode conter**(membros)
	* Atributos(dados/campos)
	* Métodos(funções/operações)

 * **A classe também pode prover muitos outros recursos, tais como:**
	 * Construtores
	 * Sobrecarga
	 * Encapsulamento
	 * Herança
	 * Polimorfismo

* **Exemplos:**
	* Entidades: Produto, Cliente, Triangulo
	* Serviços: ProdutoService, ClienteService, StorageService
	* Controladores: ProdutoController, ClienteController
	* Utilitários: Calculadora, Compactador
	* Outros(views, repositórios, gerenciadores, etc.)


#### Instanciação
(alocação de memória)

Variáveis declaradas são armazenadas em uma área da memória chamada Stack, quando um objeto é instanciado nessa variável ele é armazenado em outra área da memória chamada Heap. 

Ex:
```java
Triangle x;
//armazenada na memória stack

Triangle x = new Triangle();
// ainda está na stack porém é apenas uma referência
// contendo o endereço de memória que aponta para o objeto dentro da memória Heap

```
* Classe: é a definição do tipo
* Objetos: instâncias da classe
* Cada classe é responsável por si mesma. Ex: A classe triangle deve ser responsável por saber calcular a área de um triângulo, pois seus objetos são triângulos. A lógica da área do não deve estar em outro lugar...
* Métodos em uma classe permite o reaproveitamento de código


**this**: Palavra reservada do Java usada para se referir a um atributo da classe quando usado dentro de um método em que o parâmetro tem um mesmo nome do atributo de uma classe.

ex:

```java
public class Product {

  

	public String nome;
	public double price;
	public int quantity;


	public void addProduct(int quantity) {
		this.quantity= quantity;	
	}

}
```

## Object e ToString()

**Object**
* Toda classe Java é uma subclasse da classe Object

**Object possui os seguintes métodos:**
* getClass - retorna o tipo do objeto
* equals - compara se o objeto é igual a outro
* hashCode - retorna um código hash do objeto
* toString - converte o objeto para string

## Membros estáticos

* Também chamados membros de classe
	* Em oposição a membros e instâncias

* São membros que fazem sentido independentemente de objetos. Não precisam de objeto para serem chamados. São chamados a partir do próprio nome da classe.

* **Aplicações comuns:**
	* Classes utilitárias
	* Declaração de constantes

* Uma classe que possui somente membros estáticos, pode ser uma classe estática também. Esta classe não poderá ser instanciada.

**Métodos estáticos não podem conter chamadas de métodos não estáticos em seu bloco de código.**

## Construtores

* **É uma operação especial da classe, que executa no momento da instanciação do objeto**

* **Usos comuns:***
	* Iniciar valores dos atributos
	* Permitir ou obrigar que o objeto receba dados/dependências no momento de sua instanciação(injeção de dependências)

* Se um construtor customizado não for especificado, a classe disponibiliza um construtor padrão

```java
	Product p = new Product();	
```

É possível especificar mais de um construtor na mesma classe (sobrecarga)

Quando o construtor padrão (ou um construtor sem parâmetros) é chamado ele inicia o objeto e seus campos recebem o valor padrão do seu tipo.

## This

* **É uma referência para o próprio objeto**

* Usos comuns:
	* Diferenciar atributos de variáveis locais
	* Passar o próprio objeto como argumento na chamada de um método ou construtor


## Sobrecarga

É um recurso que uma classe possui de oferecer mais de uma operação com o mesmo nome, porém com diferentes listas de parâmetros.

Também é possível criar um construtor padrão que não recebe argumentos.


## Encapsulamento

* É um princípio que consiste em esconder detalhes de implementação de uma classe, expondo apenas operações seguras e que mantenham os objetos em um estado consistente.

* **Regra de ouro:** o objeto deve sempre estar em um estado consistente, e a própria classe deve garantir isso.

**Regra geral básica:**

* Um objeto **NÃO** deve expor nenhum atributo(modificador de acesso **private**)

* Os atributos devem ser acessados por meios de métodos get e set
	* Padrão JavaBeans


Getter e Setters por conversão ficam abaixo dos construtores e seus nomes devem conter sua função seguido do atributo que interagem ex: getName e setName


## Modificadores de acesso

* **rivate:** o membro só pode ser acessado na **própria classe**
* (nada): o membro só pode ser acessado nas classes do **mesmo pacote**
* **protected:** o membro só pode ser acessado **no mesmo pacote,** bem como em **subclasses de pacotes diferentes**
* **public:** o membro é acessado por todas as classes (ao menos que ele resida em um módulo diferente que não exporte o pacote onde ele está)













