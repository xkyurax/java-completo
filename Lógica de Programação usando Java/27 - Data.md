#### Conceitos importantes

* **Data-[hora]local:** (armazenada sem fuso horário)
	* ano-mês-dia[hora] sem fuso horário
	* [hora opcional]
	Quando o momento exato não interessa a pessoas de outro fuso horário. Uso comum: sistemas de região única, Excel.
		ex: Data de nascimento "15/06/2001"
			Data-hora da venda "13/08/2002 às 15:32" (presumindo não interessar fuso horário)

* **Data-hora global:**
	* ano-mês-dia-hora com fuso horário
	Quando o momento exato interessa a pessoas de outro fuso horário. Uso comum: sistemas multi-região, web.
		ex: Quando será o sorteio "21/08/2022 às 20h(horário São Paulo)"
			Quando o comentário foi postado? "há 17 minutos"
			Quando foi realizada a venda? "13/08/2022 às 15:32(horário de São Paulo)"
			Início e fim do evento?"21/08/2022 às 14h até as 16h(horário de São Paulo)"


* **Duração:**
	* tempo decorrido entre duas datas-horas


#### Timezone(fuso horário)

* **GMT - Greenwich Mean Time**
	É como se fosse o marco zero de todos os fuso horários
	* Horário de Londres
	* Horário padrão UTC - Coordinated Universal Time
	* Também chamado de "Z" time, ou Zulu time

* **Outros fuso horários são relativos ao GMT/UTC:**
	* São Paulo: GMT-3 (3 horas atrás do horário de Londres)
	* Manaus: GMT-4 (4 horas atrás do horário de Londres)
	* Portugal: GMT+1 (1 hora a frente de Londres)

* **Muitas linguagens/tecnologias usam nomes para as timezones:**
	* US/Pacific
	* America/Sao_Paulo
	* etc.

#### Padrão ISO 8601
Esse padrão especifica como você deve representar data e hora em texto:

Data-[hora] local:
	2022-07-21
	2022-07-21T14:52
	2022-07-22T14:52:09
	2022-07-22T14:52:09.4073

Data-hora [global]_:
	2022-07-23T14:52:09Z
	2022-07-23T14:52:009.254935Z //	O Z representa o Timezone
	2022-07-23T14:52:09-03:00 // o - representa padrão no caso aqui o GMT - 3

#### Operações importantes com data-hora

*  **Instanciação**
	* (agora) -> Data-hora
	* Texto ISO 8601 -> Data-hora
	* Texto formato customizado -> Data-hora
	* dia, mês, ano, [horário] -> Data-hora local

* **Formatação**
	* Data-hora -> Texto ISO 8601
	* Data-hora -> Texto formato customizado

* **Obter dados de uma data-hora local**
	* Data-hora local -> dia, mês, ano, horário

* **Converter data-hora global para local**
	* Data-hora global, timezone(sistema local) -> Data-hora local

* **Cálculos com data-hora**
	* Data-hora +/- tempo -> Data-hora
	* Data-hora 1, Data-hora 2 -> Duração

#### Principais tipos Java(versão 8+)

* **Data-hora local**
	* LocalDate
	* LocalDateTime

* **Data-hora global**
	* Instant

* **Duração**
	* Duration

* **Outros**
	* Zoneld
	* ChronoUnit

```java
DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy");  
//define um padrão em que a hora pode ser instanciada  
//mas o Java internamente ainda via usar o padrão ISO também na hora printar  
  
DateTimeFormatter fmt2 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm");  
  
LocalDate d01 = LocalDate.now();  
//instancia a data local do momento da execução  
  
LocalDateTime d02 = LocalDateTime.now();  
//instancia a data e hora local do momento da execução  
  
Instant d03 = Instant.now();  
//instancia a data e hora global(GMT) do momento da execução  
  
LocalDate d04 = LocalDate.parse("2022-07-20");  
//instancia uma data local passada pelo usuário como argumento  
  
LocalDateTime d05 = LocalDateTime.parse("2022-07-20T01:30:26");  
//instancia uma data e hora local passada pelo usuário como argumento  
  
Instant d06 = Instant.parse("2022-07-20T01:30:26Z");  
//instancia a data e hora global(GMT) passada como argumento  
  
Instant d07 = Instant.parse("2022-07-20T01:30:26-03:00");  
//instancia a data e hora convertendo ela para o horário global no caso do exemplo o GTM-3  
  
LocalDate d08 = LocalDate.parse("20/07/2022", fmt1);  
//hora local instanciada passando um dos padrões definidos  
  
LocalDateTime d09 = LocalDateTime.parse("20/07/2022 01:30", fmt2);  
  
LocalDate d10 = LocalDate.of(2022, 7, 20);  
//instancia data com dados isolados passados como argumento  
LocalDateTime d11 = LocalDateTime.of(2022, 7, 20, 1, 30);  
//instancia data e horacom dados isolados passados como argumento
```

Outras formas de formatar Data e hora

```java

LocalDate d04 = LocalDate.parse("2022-07-20");  
LocalDateTime d05 = LocalDateTime.parse("2022-07-20T01:30:26");  
Instant d06 = Instant.parse("2022-07-20T01:30:26Z");  
  
DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy");  
DateTimeFormatter fmt2 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm");  
DateTimeFormatter fmt3 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm").withZone(ZoneId.systemDefault());  
//instancia um padrão com a timezone do sistema do usuário  
  
DateTimeFormatter fmt4 = DateTimeFormatter.ISO_DATE_TIME;  
//criar um padrão de formatação date-time já disponível no java  
DateTimeFormatter fmt5 = DateTimeFormatter.ISO_INSTANT;  
//criar um padrão de formatação para instant já disponível no java  
System.out.println("d04 " + d04.format(fmt1));  
//format(): usa o ofPattern definido pelo desenvolvedor ao invés do toString() padrão do Java  
  
System.out.println("d04 " + fmt1.format(d04));  
//uma segunda forma de chamar o ofPattern  
  
System.out.println("d04 " + d04.format(DateTimeFormatter.ofPattern("dd/MM/yyyy")));  
//uma segunda forma de chamar o ofPattern porém enquanto o escopo da variável fmt1  
//estiver disponível ela pode ser reaproveitada, neste caso a instância ocorre na chamada  
//após a execução o garbage collector desaloca o espaço usado por ela  
  
  
System.out.println("d5 " + d05.format(fmt1));  
System.out.println("d5 " + d05.format(fmt2));  
  
System.out.println("d06 " + fmt3.format(d06));  
//instant não tem format porque não tem uma data local, o dia e horário  
//vão depender do fuso horário, para isso você precisa de outro ofPattern  
//compatível com o tipo e chamar ele passando a data como argumento.  
//No exemplo acima convertemos o horário de Londres para o do Brasil (Fuso do usuário)  
  
System.out.println("d06 " + fmt3.format(d06));  
System.out.println("d06 " + fmt5.format(d06));  
System.out.println("d06 " + d06.toString());
```




```java
 LocalDate d04 = LocalDate.parse("2022-07-20");  
 LocalDateTime d05 = LocalDateTime.parse("2022-07-20T01:30:26");  
 Instant d06 = Instant.parse("2022-07-20T01:30:26Z");  
  
 ZoneId.getAvailableZoneIds();  
 //retorna uma collections com todas as zoneids disponíveis no java  
  
LocalDate r1 = LocalDate.ofInstant(d06, ZoneId.systemDefault());  
 //instancia uma local date,  contendo o horário global convertido para local usando a timezone  
 //do sistema em que a aplicação do usuário está rodando  
 LocalDate r2 = LocalDate.ofInstant(d06, ZoneId.of("Portugal"));  
 //instancia uma loal date, contendo um horário global convertido para a timezone de portugal  
  
 LocalDateTime r3 = LocalDateTime.ofInstant(d06, ZoneId.systemDefault());  
 LocalDateTime r4 = LocalDateTime.ofInstant(d06, ZoneId.of("Portugal"));  
  
 System.out.println("r1 " + r1);  
 System.out.println("r2 " + r2);  
 System.out.println("r3 " + r3);  
 System.out.println("r4 " + r4);  
  
 System.out.println("d04 dia = " + d04.getDayOfMonth());  
 System.out.println("d04 mês = " + d04.getMonthValue());  
 System.out.println("d04 ano = " + d04.getYear());  
  
 System.out.println("d05 hora = " + d05.getHour());  
 System.out.println("d05 hora = " + d05.getMinute());
```






