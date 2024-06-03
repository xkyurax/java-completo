
**Classes são tipos referência**

Variáveis cujo tipos são classes não devem ser entendidas como caixas, mas sim tentáculos(ponteiros) para caixas.

Uma variável declarada que contém uma instância de objeto após o operador de atribuição deixa de armazenar o valor e passa a guardar uma referência do objeto que ela contém. A variável permanece na memória stack mas ela aponta para o local em que o objeto está na memória heap.

Tipos de referência aceitam o valor "null", que indica que a variável aponta para ninguém.

```java
Product p1 = new Product();
Product p2 = p1;
//p2 aponta para a mesma referência que p1
```

**Tipos primitivos são tipos de valor***

Em Java, tipos primitivos são tipos valor. Tipos valor são CAIXAS e não ponteiros.

```java
double x, y;
x = 10;
y = x;
// y recebe uma cópia de x
```
**Valores padrão**

* Quando alocamos(new) qualquer tipo estruturado(classe ou array), são atribuidos valores padrão aos seus elementos.
	* números: 0
	* boolean: false
	* char: caractere código 0
	* objeto: null

|                                        Classe                                        | Tipo Primitivo                                                                     |
| :----------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------: |
|                      Vantagem: usufrui de todos os recursos OOP                      | Vantagem: é mais simples e mais performático                                       |
|                               Variáveis são ponteiros                                | Variáveis são caixas                                                               |
| Objetos precisam ser instanciados usando new, ou apontar para um objeto já existente | Não instancia. Uma vez declarados, estão prontos pra uso.                          |
|                                  Aceita valor null                                   | Não aceita valor null                                                              |
|                    Y = X;<br>Y passa a apontar para onde x aponta                    | Y = X;<br>Y recebe uma cópia de X                                                  |
|                             Objetos instanciados no heap                             | "Objetos" instanciados no stack                                                    |
| Objetos não utilizados são desalocados em um momento próximo pelo garbage collector  | "Objetos" são desalocados imediatamente quando seu escopo de execução é finalizado |

