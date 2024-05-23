
**Estrutura condicional:** É uma estrutura de controle que permite definir que um certo bloco de comandos somente será executado dependendo de uma condição.

Sintaxe da estrutura condicional:

**Simples:** Executa o bloco de código caso a condição seja true, pula o bloco de código e não o executa caso seja false.
```java
if(<condição>){
	<comando 1>
	<comando 2>
}
```

**Composta:** Executa somente o bloco if se for true e caso seja false executa o else.
``` java
if(<condição>){
	<comando 1>
	<comando 2>
} 
else {
	<comando 3>
	<comando 4>
}
```
Podemos usar o encadeamento de estruturas condicionais para tratar mais de 2 condições.

```java
if(<condição>){
	<comando 1>
	<comando 2>
} 
else {
	if(<condição2>){
		<comando 3>
		<comando 4>
	} 
	else {
		<comando 5>
		<comando 6>
	}
}
```