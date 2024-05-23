
Podemos trabalhar com entrada de dados fornecidos pelo usuário à nossa aplicação por meio da class Scanner do Java.

Fazemos o import de 
java.util.Scanner 

e instanciamos um objeto dessa classe. 
Ex: Scanner sc = new Scanner(System.in);

Faça sc.close() quando não precisar mais do objeto sc

#### Para ler uma palavra(texto sem espaços)
```java
String x;
x = sc.next();`
```


#### Para ler um número inteiro
``` java
int x;
x = sc.nextInt();
```
#### Para ler um número com ponto flutuante
```java
double x;
x = sc.nextDouble();`
```

Para considerar o separador de decimais como ponto antes da declaração do Scanner, faça:

Locale.setDefault(Locale.US);

Sem essa declaração, caso você use um . como separador decimal ao invés de uma vírgula, sua aplicação lançaria uma exception java.util.InputMismatchException.

#### Para ler um caractere
``` java
char x;
x = sc.next().charAt(0);`
```

charAt(0) retornar um char baseado no valor do índice passado para o método.

#### Para ler vários dados na mesma linha
``` java
string x;
int y;
double z;

x = sc.next();
y = sc.nextInt();
z = sc.nextDouble;`
```


#### Para ler um texto ATÉ A QUEBRA DE LINHA

``` java
import java.util.Scanner;

public class Main{
	
	public static void main(String[] args) {
		
		Scanner sc = new Scanner(system.in);

		String s1, s2, s3;

		s1 = sc.nextLine();
		s2 = sc.nextLine();		
		s3 = sc.nextLine();

		System.out.println("DADOS DIGITADOS:");
		System.out.println(s1);
		System.out.println(s2);
		System.out.println(s3);

		sc.close();
	}
}
```

#### Atenção: Quebra de linha pendente

``` java
int x;
String s1, s2, s3;

x = sc.nextInt();
s1 = sc.nextLine();
s2 = sc.nextLine();
s3 = sc.nextLine();

System.out.println("DADOS DIGITADOS:");
System.out.println(s1);
System.out.println(s2);
System.out.println(s3);
````
``` 
SAÍDA:

DADOS DIGITADOS:

30

Bom dia

Boa tarde
```
Quando você usa um comando de leitura diferente do nextLine() e dá alguma quebra de linha, essa quebra de linha fica pendente na entrada padrão. Se você então fizer um nextLine(), aquela quebra de linha pendente será absorvida pelo nextLine().

Uma das formas de evitar isso é usando nextLine()antes da próxima entrada de tipo diferente.

``` java
x = sc.nextInt();
sc.nextLine();
s1 = sc.nextLine();
s2 = sc.nextLine();
s3 = sc.nextLine();

```

