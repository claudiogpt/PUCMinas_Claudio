## Redirecionamento
- Se **java Exemplo.MyIO** - lê teclado e escreve na tela.
- Se **java Exemplo.MyIO < in.txt** - lê o arquivo in.txt e escreve na tela.
- Se **java Exemplo.MyIO > out.txt** - lê o teclado e escreve em out.txt
- Se **java Exemplo.MyIO < in.txt > out.txt** - ele lê de in.txt e escreve em out.txt 
### Arquivos(Java)
**Classes:**
	**Arq:** arquivos em modo texto, acesso sequencial **(no material da aula)**.
		Arquivos escritos desse modo podem ser lidos em editores de texto e vice e versa.
	**RandomAccessFile:** trabalha com arquivos em modo binário, acesso aleatório **(no material da aula)**. 
		-> Permite o acesso aleatório de leitura e escrita de arquivos.
		-> Manipula arquivos em modo binário.
		-> Considera que cada arquivo é um array de bytes indexado por um cabeçote (ponteiro cursor).
		-> Próximo local de leitura e escrita é indicada pela posição atual.
		->**long getFilePointer()** -> posição corrente
		->**void seek(long)** -> altera valor da posição corrente.
		**Dois Construtures(RAF):**
			Referência para o arquivo + modo de operação indicando leitura ou escrita.
			**RandomAccessFile(File file, String mode)**
			**RandomAccessFile(String name, String mode)**
				**"r"** -> apenas leitura, ler um arquivo não existente envia um erro.
				**"rw"** -> leitura/escrita, se o arquivo não existir ele é criado
				**"rws" e "rwd"** -> leitura/escrita com sincronizações.
	**Para escrita e leitura:**
		Formatter e Scanner.

**Notes:**
	**Charset:** codificação de binário em letras (como **UTF-8**).
	**RAF:** podem gerar exceções e não são extáticos.
### Introdução ao Java
- **JVM** -> processador virtual que interpreta os bytecodes e gera instruções que serão executadas pelo processador.
	**Interpretação** faz com que Java não seja tão rápido, mas multiplataforma.
	**Soluções para lentidão:**
		**Just in time compiler(JIT)** -> traduz os bytecodes para instruções de máquinas nativas, contudo, perde a multiplataforma e tem aumento na velocidade do código(provávelmente melhor usar outra linguagem se possível).
		**JVM em Hardware** -> picoJava, microJava e UltraJavaTM
- Métodos e Arrays == Funções e Vetores.
- **javac myFile.java** -> to compile.
- **java myFile** -> to run.
- **Regra para nomes de variáveis:**
	Primeiro caractere é uma letra ("\_" e "$" são letras),
	O restante pode conter letras ou dígitos,
	Java diferencia letras maiúsculas de minúsculas,
	Palavras reservadas e nomes de funções não são permitidos.
		**Ex(reservadas):** class, for, while, if, else, int, double, char
		**Ex(erros):** 1cont, oi!gente, Sao...Joao,\_size-int, if
		**Ex(acertos):** cont, Teste23, Sao_Joao, \_\_sizeint, $cont, \_if
	**Classes:** começam com letras maiúsculas, **varíaveis:** minúsculas.

### Ponteiros 
- Java e C tem somente a passagem de parâmetros por valor
	**Escopo:** Ao chamar uma função ou método e passar argumentos para ele, o que é realmente passado é uma cópia do valor do argumento, em vez do próprio valor original. Isso significa que qualquer modificação feita aos parâmetros dentro da função não afeta os valores originais fora dela.
- Um **array é um ponteiro**, **ponteiro é uma variável que armazena endereço de memória**(ou seja, nem toda variável é um ponteiro). **Ex:** int inteiro(inteiros), double double(reais), tipoPonteiro \*nomeVariável(endereço).
	**Array como parâmetro:** passamos a primeira posição da área referenciada, e a sequência vem de forma contínua. O endereço não se altera após o método ser chamado (apenas o conteúdo pode ser).
##### Obs
- Os símbolos usados para notação de ponteiros em C/C++ não são tão claros como deveriam ser.
- Descuido com ponteiros ⇒ problemas 
- Atenção: Sempre inicialize os ponteiros
**Exemplos**
	• **p1 = p2:** 
		faz com que eles apontem para o mesmo local.
	**• \*p1 = \*p2:** 
		Atribui o conteúdo apontado por p2 a p1.
	**• p++, p--, p=p+5 e p+=3** 
		Incrementa e decrementa o valor do endereço apontado pelo ponteiro, fazendo com que o ponteiro ande sizeof(tipoPonteiro) bytes na memória.
	• (\*p)++ e (\*p) --
		 Incrementa/decrementa o conteúdo da variável apontada pelo ponteiro p. 
	• Os testes relacionais como >, <, >=, <=, == ou != são aceitos apenas para ponteiros do mesmo tipo e eles comparam os endereços.
**Java**
	**Tipos primitivos:** a passagem é por valor (cópia dele).
		**Objetos:** é passada uma cópia da referência que aponta para o objeto, não criado um novo (modificações feitas nos atributos do objeto dentro da função são refletidas fora dela).
**C**
	**Sempre por valor:** em C essa passagem é sempre por valor tanto em tipos primitivos tanto quanto em ponteiros(que podem ser usados para simular passagem por referência).
### Construtores
- **Criação de Objetos:** Invocado quando objetos são criados. Aloca memória para o objeto e inicia seus atributos.
- **Nome do Construtor:** O nome de um construtor deve ser o mesmo que o nome da classe em que está definido. Assim o compilador associa o construtor a novos objetos daquela classe.
- **Parâmetros:** Um construtor pode receber parâmetros que são usados para inicializar os atributos do objeto.
- **Sempre será público.
- **Não apresenta tipo de retorno.**
- **Tipos**
	**Default:** São construtores que não têm parâmetros ou que têm parâmetros com valores padrão. Eles são fornecidos automaticamente se nenhum construtor é explicitamente definido na classe.
	**Parametrizados:** São construtores que recebem parâmetros e são usados para configurar os atributos do objeto com base nos valores fornecidos.
	**Inicialização:** Os construtores são usados para inicializar os atributos do objeto com valores apropriados. Isso pode incluir alocação de memória, atribuição de valores iniciais e execução de outras ações necessárias.
	**Sobrecarga de Construtores:** Assim como outros métodos, os construtores podem ser sobrecarregados, o que significa que uma classe pode ter vários construtores com diferentes listas de parâmetros. Isso oferece flexibilidade ao criar objetos com diferentes conjuntos de inicializações.
#### Exemplo
```java
public class Pessoa {
    private String nome;
    private int idade;

    // Construtor padrão
    public Pessoa() {
        nome = "Sem nome";
        idade = 0;
    }

    // Construtor parametrizado
    public Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }
    // Outros métodos e atributos da classe
}
```
### Introdução OOP
- **Classe:** um tipo, conjunto de regras.
	**Objeto:** variável do tipo classe.
- **Atributos Privados:**
	**Get:** _getNomeDoAtributo_ -> retorna o conteúdo do atributo privado.
		retorna o mesmo tipo do _atributo_, não recebe parâmetros.
	**Set:** _setNomeDoAtributo_ -> altera o conteúdo do atributo privado.
		retorna **void**, parâmetro de entrada do mesmo tipo do _atributo_.
- **Estático:** 
	**Atributos e métodos estáticos** podem ser chamados sem que um objeto seja instanciado (por **Ex:** IO.println).
	**Valor:** compartilhado por todos os objetos da classe.
	**Acesso:** somente os métodos ou atributos estáticos da classe.
- **Operador This:** 
	**Explicita:** método ou atributo pertence ao objeto corrente.
	-> Também pode ser utilizado para explicitar o objeto corrente.
### Exception Handling
- **Exception:** Evento que ocorre durante a execução de um programa e deturpa o fluxo normal de instruções.
	Divisão por zero,
	Abrir um arquivo inexistente,
	Leitura de um tipo inesperado, 
	Acesso a posição inválida de um array,
	Erro de hardware,
- **Try/Catch**
	Se ao executar um código ele tiver a possibilidade de falhar por uma entrada você o testa com **Try**.
	Se falhar, lida com ele com **Catch**.
	**Finally:** executado de qualquer forma ao fim do programa.
##### Exemplo
```java
public class TratamentoExcecao02 { 
	public static void main(String[] args) { 
		try {
			Integer i = new Integer(args[0]); 
			MyIO.println("A variável i vale " + i);
		 } catch (ArrayIndexOutOfBoundsException e) { 
			 MyIO.println("Erro na passagem de parâmetros!!!");
		 } finally { 
			 MyIO.println("FIM DE PROGRAMA!!!"); 
		 } 
	} 
}
```
#### Múltiplas Excessões
- Podem ser tratadas em um mesmo bloco com vários Catchs.
#### Exemplo
```java
public class TratamentoExcecao03 { 
	public static void main(String[] args) { 
		try { 
			Integer i = new Integer(args[0]);
			MyIO.println("A variável i vale " + i);
		} catch (NumberFormatException e) {
			MyIO.println("Erro de formatação!!! "); 
		} catch (ArrayIndexOutOfBoundsException e){ 
			MyIO.println("Erro na passagem de parâmetros!!!"); 
		} finally { 
			MyIO.println("FIM DE PROGRAMA!!!"); 
		} 
	} 
}
```
#### Throws 
- Tratar as exceções passando-as para frente.
- **throw new** _Exception()_ -> cria exceções.
##### Exemplo
```java
public class ExemploExcecaoThrow {
    public static void main(String[] args) {
        try {
            int resultado = dividir(10, 0);
            System.out.println("Resultado: " + resultado);
        } catch (ArithmeticException e) {
            System.out.println("Erro: Divisão por zero!");
        }
    }

    public static int dividir(int numerador, int denominador) {
        if (denominador == 0) {
            throw new ArithmeticException("Divisão por zero não é permitida.");
        }
        return numerador / denominador;
    }
}
```