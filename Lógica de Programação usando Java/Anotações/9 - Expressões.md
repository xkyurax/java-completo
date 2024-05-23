
#### Expressões comparativas

São expressões usadas para fazer comparações entre dados, o resultado desse tipo de expressão retorna uma resultado true ou false.

| Operador | Significado    |
| -------- | -------------- |
| >        | maior          |
| <        | menor          |
| >=       | maior ou igual |
| <=       | menor ou igual |
| ==       | igual          |
| !=       | diferente      |

#### Expressões lógicas

Assim como expressões comparativas, são expressões que quando avaliadas retornam true ou false.

| Operador | Significado |
| :--: | :-----------: |
| &&       | E           |
| \|\|     | OU          |
| !        | Não         |
* **&& -** Todas as condições devem retornar true

| A   |  B  | A&&B |
| :-: | :-: | :-: |
| F   |  F  |    F |
| F   |  V  |    F |
| V   |  F  |    F |
| V   |  V  |    V |

* **|| -** Pelo menos uma condição deve ser true

| A   |  B  | A&&B |
| :-: | :-: | :-: |
| F   |  F  |  F   |
| F   |  V  |  V   |
| V   |  F  |  V   |
| V   |  V  |  v   |

* **! -** Inverte a condição

ex:
(Supunha que x igual a 5)

!(x == 10);
resultado = true;







