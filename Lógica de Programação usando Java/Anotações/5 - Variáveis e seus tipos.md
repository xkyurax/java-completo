
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

![img](https://github.com/xkyurax/java-completo/blob/main/L%C3%B3gica%20de%20Programa%C3%A7%C3%A3o%20usando%20Java/Anota%C3%A7%C3%B5es/img/Pasted%20image%2020240502001201.png?raw=true)
![img2](https://github.com/xkyurax/java-completo/blob/main/L%C3%B3gica%20de%20Programa%C3%A7%C3%A3o%20usando%20Java/Anota%C3%A7%C3%B5es/img/Pasted%20image%2020240502001331.png?raw=true)

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

