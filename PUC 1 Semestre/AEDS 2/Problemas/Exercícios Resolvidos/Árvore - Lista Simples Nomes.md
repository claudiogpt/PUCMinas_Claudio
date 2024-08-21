```c
//Dados do Contato
struct Contato {
	String nome;
	String telefone;
	String email;
	String cpf;
}

//Lista Simplesmente Encadeada
struct CelulaLista {
	CelulaLista dir;
	Contato contato;
}

struct NoArvore {
	NoArvore esq, dir;
	//Lista que está encadeada
	CelulaLista lista;
	//valor salvo
	char inicial;
}

Contato Pesquisa (NoArv raiz, String nome){
	//Árvore Vazia -> Retorna nulo
	if (raiz == Null) {
		return Null;	
	}
	//Se inicial menor, desce pela esquerda
	if (inicial(nome) < raiz.inicial) {
		return pesquisa(raiz.esq, nome);
	}
	//Se inicial maior, desce pela direita
	if(inicial(nome) > raiz.inicial) {
		return pesquisa(raiz.dir, nome);
	}
	return pesquisaLista(raiz.lista, nome);
}

//Esse paradigma diminui o escopo de contato, evitando Bugs
Contato pesquisaLista(CelulaLista lista, String nome){
	for (CelulaLista w = lista; w.dir != null; w = w.dir){
		if (w.dir.nome == nome){
			return w.dir;
		}	
	}
	return null;
}

//versão errada contato lista 
Contato pesquisaLista(CelulaLista lista, String nome){
	Contato contato = null;
	for (Contato w = contato; w.dir != null; w = w.dir){
		if (w.dir.nome == nome){
			contato = nome;
			break; // aumenta o escopo do contato, aumentando a chance de BUG
		}	
	}
	return contato;
}

// Função para inserir na lista
NoArvore inserirArv(NoArv raiz, Contato contato){
	if(raiz == null){
		return new NoArvore(contato);
	}
	if(inicial(contato.nome) < raiz.inicial){
		raiz.esq = inserir.Arv(raiz.esq, contato);	
	}
	if(inicial(contato.nome) > raiz.inicial){
		raiz.dir = inserirArv(raiz.dir, contato);	
	}
	inserirLista(raiz.lista, contato);
	return raiz;
}

void inserirLista(CelulaLista lista, Contato contato){
	for (CelulaLista w = lista; w.dir != null; w = w.dir){
		if (w.dir.nome  == contato.nome) {
			throw exception("Erro");	
		}
	}
	CelulaLista novaCelula = new CelulaLista(contato);
	novaCelula.dir = lista.dir;
	lista.dir = novaCelula;
}
```
### Revisão Árvore
**Caso Médio**
- Inserir na Arv: O(log_2 n)
### Estrutura de Dados
**Definição:** formas de organizar os dados para facilitar operações.
- Tem algoritmos para operações
### C e C++
- Setinha é para acessar ponteiros (derreferência).