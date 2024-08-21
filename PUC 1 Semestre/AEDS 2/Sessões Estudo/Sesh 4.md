1. **Interface:** Uma interface em programação é uma coleção de métodos abstratos (sem implementação real) que definem um conjunto de ações ou comportamentos que uma classe deve fornecer. As interfaces geralmente não contêm variáveis de instância, apenas a assinatura dos métodos (nome, parâmetros e tipo de retorno).
```java
// Exemplo de uma interface interface 
Animal {
	void fazerSom();
	void mover();
}
```
1. **Implementação:** Para utilizar uma interface, você cria uma classe que "implementa" essa interface. Isso significa que a classe deve fornecer implementações reais para todos os métodos definidos na interface. Isso é feito usando a palavra-chave `implements` em Java.
	Implementação real de tipos abstratos.
```java
class Cachorro implements Animal {
	@Override 
	public void fazerSom() {
		System.out.println("O cachorro faz latidos."); 
	} 
	@Override 
	public void mover() {
		System.out.println("O cachorro se move correndo."); 
	} 
}
```
1. **Contrato:** A implementação de interface garante que a classe que a implementa cumpra um contrato específico. Isso significa que a classe deve ter os métodos especificados na interface, e esses métodos devem fazer o que a interface descreve.
	Neste exemplo, a classe `Cachorro` implementa a interface `Animal` e fornece implementações concretas para os métodos `fazerSom()` e `mover()`, cumprindo assim o contrato da interface.

## Programação Modular
Dizer que o código é "modular" significa que ele foi projetado e estruturado de forma a ser dividido em módulos ou unidades independentes e interconectadas. Cada módulo tem uma responsabilidade específica e se comunica com outros módulos por meio de interfaces bem definidas. 
**Vantagens:**
1. **Facilita a Manutenção:** Quando o código está dividido em módulos, é mais fácil localizar e corrigir problemas ou fazer melhorias em partes específicas do sistema, sem afetar o restante do código.
2. **Reutilização de Código:** Módulos bem definidos podem ser reutilizados em diferentes partes de um programa ou até em projetos diferentes, economizando tempo e esforço de desenvolvimento.
3. **Colaboração:** Diferentes desenvolvedores podem trabalhar em módulos diferentes simultaneamente, desde que as interfaces entre os módulos sejam respeitadas. Isso facilita o desenvolvimento em equipe!!!!!!!!!
4. **Testabilidade:** Módulos independentes são mais fáceis de testar, pois suas funcionalidades podem ser testadas isoladamente antes de serem integradas ao sistema como um todo.
5. **Legibilidade:** Um código modular é geralmente mais legível, pois cada módulo se concentra em uma tarefa específica, tornando mais claro o propósito de cada parte do código.
**OBS:** Em programação, a modularidade é uma prática recomendada que promove a organização e a eficiência do código, tornando-o mais flexível e escalável. Para alcançar a modularidade, é comum utilizar conceitos como classes, funções, bibliotecas e a divisão lógica das responsabilidades em unidades coesas e independentes.

### Kernel
Em computação, o termo "kernel" se refere a uma parte fundamental do sistema operacional. O kernel é a parte do sistema operacional que atua como uma camada intermediária entre o hardware do computador e os programas de software em execução. Ele desempenha várias funções críticas:
1. **Gerenciamento de Recursos:** O kernel é responsável por gerenciar os recursos de hardware, como CPU, memória, dispositivos de armazenamento e periféricos. Ele aloca e libera recursos conforme necessário para garantir que os programas sejam executados de maneira eficiente e justa.
2. **Controle de Processos:** O kernel gerencia os processos em execução no sistema. Isso inclui a criação, destruição e escalonamento de processos. Ele garante que múltiplos programas possam ser executados simultaneamente em um sistema de maneira coordenada.
3. **Gestão de Memória:** O kernel controla a alocação de memória para programas em execução, garantindo que eles não acessem áreas de memória de outros programas e evitando vazamentos de memória.
4. **Gerenciamento de Dispositivos:** O kernel lida com a comunicação entre software e hardware. Ele fornece drivers para dispositivos de hardware e permite que os programas acessem esses dispositivos de maneira consistente.
5. **Segurança:** O kernel desempenha um papel crucial na segurança do sistema, controlando o acesso a recursos críticos e garantindo a integridade dos dados.
6. **Comunicação entre Processos:** O kernel também fornece mecanismos para a comunicação entre processos, como pipes, sockets e semáforos.
Em sistemas operacionais modernos, como o Linux, Windows e macOS, o kernel é uma parte essencial e altamente otimizada do sistema. Ele opera em um nível de privilégio mais alto do que os aplicativos de usuário, o que significa que tem acesso direto ao hardware e controle total sobre os recursos do sistema. Isso permite que o kernel supervisione e coordene todas as operações no computador, garantindo o funcionamento adequado do sistema operacional e dos programas que são executados nele.

## Manipulação de Dados:
- Usar o Pandas,  perfeito para manipulação e filtragem no geral.
