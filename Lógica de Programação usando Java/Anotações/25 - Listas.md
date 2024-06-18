
* **Lista é uma estrutura de dados:**
	* Homogênea(dados do mesmo tipo)
	* Ordenada(elementos acessados por meio de posições)
	* Inicia vazia, e seus elementos são alocados sob demanda
	* Cada elemento ocupa um "nó"(ou nodo) da lista

* **Tipo(Interface): List**
	* Classes que implementam: ArrayList, LinkedList, etc.

* **Vantagens**
	* Tamanho variável
	* Facilidade para se realizar inserções e deleções

* **Desvantagens:**
	* Acesso sequencial aos elementos

``` java
List<Integer> list = new ArrayList<>();
						//Uma das implementações de List
```

* add() - adiciona um elemento à lista

* add(int, elemento) - sobrecarga do add que recebe um inteiro referente  a posição e o elemento que será adicionado.

* size() - retorna um inteiro correspondente ao tamanho da lista

* remove() - remove um elemento passado como argumento

* remove(int) - sobrecarga de remove que recebe inteiro referente a posição do elemento que será removido

* removeIf(predicate) - remove elementos conforme especificado no predicate.
	* ex: list.removeIf(x -> x.charAt(0) == 'M'); 
		* no exemplo acima, removemos todos os nomes que começam com M


* indexOf(elemento) - retorna um index do elemento passado como argumento, retorna um int correspondente a posição do elemento encontrado e -1 caso não

* stream() permite o uso de expressões lambdas como filter() para realizar operações em listas convertidas para streams. Filter recebe um predicate.
	* ex: list.stream().filter(x -> x.charAt(0)'A').collect(Collectors.toList())
	* findFirst() proca a primeira ocorrência especificada
		* ex: String name = list.stream().filter(x -> x.charAt(0) == 'A').findFirst().orElse(null);
			* orElse(null) retorno caso não seja encontrado será null