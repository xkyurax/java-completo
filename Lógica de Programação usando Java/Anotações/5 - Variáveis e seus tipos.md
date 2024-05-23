
**Definição informal:** Em programação, uma variável é uma porção de memória(RAM) utilizada para armazenar dados durante a execução dos programas.

**Sintaxe para declarar uma variável:**
tipo nome = valor inicial;
					   |
                    Opcional

**Exemplo:**
	int idade = 25;
	double altura = 1.68;
	char sexo  = 'F';

**Uma variável possui:**
* Nome(ou identificador)
* Tipo
* Valor
* Endereço


## Tipos primitivos

![[img/Pasted image 20240502001201.png]]
![[Pasted image 20240502001331.png]]

## Nomes de variáveis

* Não pode começar com dígito: use uma letra ou _
* Não pode ter espaço em branco
* Não usar acentos ou til
* Sugestão: use o padrão "camel case" ex: int salarioDoFuncionario

| Errado                      | Certo                     |
| --------------------------- | ------------------------- |
| int 5minutos;               | int _5minutos;            |
| int salário;                | int salario;              |
| int salário do funcionario; | int salarioDoFuncionario; |
|                             |                           |

**É boa prática**

Sempre indique o tipo do número, se a expressão for de ponto flutuante(não inteira).

para double use:
0.
ex: 6.0


para float use:
f
ex: 6f
