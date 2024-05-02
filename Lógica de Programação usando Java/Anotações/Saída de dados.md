Saída de dados é quando o programa exibe, entrega ou retorna dados que foram processados após a entrada para o usuário. (Entrada -> Processamento -> Saída).


**Para escrever na tela um texto qualquer**

**Sem quebra de linha ao final**
System.out.print("Bom dia!");

**Com quebra de linha ao final**
System.out.println("Bom dia!");


**Para escrever o conteúdo de uma variável de algum tipo básico**

int y = 32;
System.out.println(y);


**Para escrever o conteúdo de uma variável com ponto flutuante**

double x = 10.35784;
System.out.printf("%.2f%n", x);
System.out.printf("%.4f%n", x);



**Para concatenar um elemento em um comando de escrita**

System.out.println("Resultado= " + variavel);




**Para concatenar vários elementos em um mesmo comando de escrita formatada**

System.out.printf("Resultado = %.2f metros%n", x);



**Para concatenar vários elementos em um mesmo comando de escrita formatada**

String nome = "Maria";

int idade = 31;

double renda = 4000.0;

System.out.printf("%s tem %d anos e ganha R$ %.2f reais%n", nome, idade, renda);











