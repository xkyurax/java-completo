
**Garbage Collector**

* É um processo que automatiza o gerenciamento de memória de um programa em execução

* O garbage collector monitor os objetos alocados dinamicamente pelo programa (no heap), desalocando aqueles que não estão mais sendo utilizados

```java
Product p1, p2;
p1 = new Product()
p2 = new Product()
p1 = p2;

//p1 perde a referência, o garbage collector desaloca o objeto da memória e p1 passa a apontar para o objeto de p2
```

* Objetos alocados dinamicamente, quando não possuem mais referência para eles, serão desalocados pelo garbage collector. 

* Variáveis locais são desalocadas imediatamente assim que seu escopo sai de execução

``` java
Product p = method();

void method() {
	Product prod = new Product();
	return prod;
}
```

No exemplo acima, prod se encontra em um sub escopo na memória stack, ao final da execução do método, prod seria desalocada da stack mas como sua referência é retornada ela não é desalocada da memória heap e p passa guarda a referência.