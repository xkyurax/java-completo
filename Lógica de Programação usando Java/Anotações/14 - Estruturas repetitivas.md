
## While
É uma estrutura de controle que repete um bloco de comandos enquanto uma condição for verdadeira.

**Quando usar:** quando não se saber previamente a quantidade de repetições que será realizada.

```java
while(condição) {
	comando1
	comando2
}
```

**Regra:** Se a condição for verdadeira, executa e voltar, se for falsa encerra a execução do while.



## For
É uma estrutura de controle que repete um bloco de comandos para um certo intervalo de valores.

**Quando usar:** quando se sabe previamente a quantidade de repetições, ou o intervalo de valores.

**Sintaxe**

```java
for(início; condição; incremento) {
	comando1
	comando2
}
```

**Importante**

A estrutura for é ótima para se fazer uma repetição baseada em CONTAGEM:

```java
for(int i = 0; i < 5; i++){
	System.out.println("Valor de i: " + i);
}
```
```
saída:
Valor de i: 0
Valor de i: 1
Valor de i: 2
Valor de i: 3
Valor de i: 4
```

## do-while
Menos utilizada, mas em alguns casos se encaixa melhor ao problema. O bloco de comandos executa pelo menos uma vez, pois a condição é verificada no final.

```java

do{
	comando1
	comando2
}while (condição)
```