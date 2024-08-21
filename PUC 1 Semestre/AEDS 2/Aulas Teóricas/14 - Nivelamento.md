#### Revisão
- Sentinela, primeiro elemento vazio.
## Ordenação Acabou - Fazer TP2
## Alocação de Memória
```c
int main() {
	
	int x
	x = 10;
	
	int *py;
	py = malloc (size of(int));
	*py = 20;
	free(py);
}
```
#### C
- Aloca memória dinâmicamente (variáveis locais);
- Aloca memória do SO;
#### Java
- Aloca a memória em JVM (memória do SO gerenciada pela JVM);
```java
void main(){
	int x;
	x = 10;
	
	Integer y = new Interger(20);
	Integer y2 = y;
	Integer y3 = y;
}
```
- **JVM**
	- End. Memória 0x01
	- Referências 3
- **Garbage Colector**
	- Referências 0 -> Coleta de lixo, free(y);

### Estruturas de Dados Estáticas
- Sempre busca o próximo vetor, referências(ponteiros) dentro do vetor;
### Estruturas de Dados Flexíveis
- Ponteiros para lugares específicos que desejados na estrutura;
- Ponteiros variam de uma estrutura para outra (não seguem necessáriamente o paradigma de vetor).

### Próximas Aulas
- Pilha
	- Topo -> Cel -> Cel -> Cel -> Null
- Fila
	- Primeiro -> Cel -> Cel -> Cel (-> Null) <- Último
- Lista
	- Primeiro -> Cel -> Cel -> Cel -> Null
