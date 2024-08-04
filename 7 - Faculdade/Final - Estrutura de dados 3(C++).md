> Algoritmo é uma sequencia finita de passos bem definidos para realizar uma tarefa ou resolver um problema

# 1° Ciclo
## Slide 1 - Algoritmos e Estruturas Básicas
Para um algoritmo eficiente
- Definir ações simples e sem ambiguidade;
- Organizar as ações de forma ordenada;
- Estabelecer as ações dentro de uma sequência finita de passos.

Para realizar tarefas como 
- Ler e escrever dados
- Tomar decisões com base nos resultados da expressões avaliadas.

Um algoritmo possui as seguintes características:
- Precisão: Formulado de maneira inequívoca, sem ambiguidades
- Finitude: Deve encerrar após um número finito de passos, para não entrar em loop
- Entrada: Dados e informações ou variáveis que são fornecidos durante a execução
- Saída: Resultado ou as informações após o processamento dos dados de entrada
- Eficácia: A capacidade de atingir seus objetivos de maneira eficiente

Programa normal para soma de números
```cpp
#include <iostream>
using namespace std;
    int main() {
        double numero1, numero2; //precisão
        cout << "Digite o primeiro número: ";//entrada
        cin >> numero1;
        cout << "Digite o segundo número: ";//entrada       
	    cin >> numero2;
	    
        double soma = numero1 + numero2;
        cout << "A soma de " << numero1 << " e " << numero2 << " é: " << soma<< endl;// saída/eficacia    
return 0;
}
```

Estrutura básica de um algoritmo
- Sequência: Uma serie ordenada e lógica de instruções ou comando que são executados sequencialmente
- Seleção(ou condicional): Tomada de decisões com base em condições.
- Repetição(ou iteração): É a execução repetida de um conjunto específico de instruções ou bloco de código.

Programa simples para saber se o número é positivo ou negativo e fazer uma contagem regressiva
``` cpp
#include <iostream>
using namespace std;

int main(){
    int number;
    cout << "Digite o número de 1 a 10: ";
    cin >> number;
    
    if(number >= 0) {
        cout << " O número é positivo" << endl;
    } else if(number < 0){
        cout << "O número é negativo" << endl;
    } else {
        cout << "O número é zero" << endl;
    }
    
    if(number >0){
        while(number >= 0){
        cout << number << endl;
        number--;
        }    
    }else{
        cout << "Programa Terminado";
    }
return 0;
}
```

Objetivos da estrutura de dados:
- Eficiência: Acesso rápido e eficiente aos dados
- Organização: Facilita a organização lógica
- Facilidade de manutenção: Código legível e fácil de manter
- Reusabilidade: Utilizar o código em outras aplicações 

Tipos de estruturas de dados
- Dados Lineares: Elementos dispostos em sequência linear, cada elemento tem um predecessor e um sucessor exceto o primeiro e o último número.
	Exemplos de dados lineares: Vetores, Listas, Pilhas, Filas
- Dados não lineares: Não há uma ordem rígida entre os elementos, oferecem flexibilidade para representar conexões mais elaboradas. 
	Exemplos: árvores e grafos
- Dados Homogêneos: Coleção de dados onde todos apresentam o mesmo tipo, facilitando assim o acesso eficiente dos dados e a simplificação das operações de manipulação.
	Exemplos: Arrays e Listas Homogêneas
- Dados Heterogêneos: Coleção de dados onde os elementos podem ser de tipos diferentes. São necessárias abordagens mais complexas na manipulação e acesso aos dados devido a diversidade dos dados.
- Dados Estáticos: São coleções de dados fixos, ou seja a quantidade de elementos é definida no momento da criação da estrutura e não pode ser alterada durante a execução do programa
	Exemplo: Arrays
- Dados Dinâmicos: Ao contrário da Estática os dados do Dinâmico podem variar durante a execução do programa podendo diminuir ou aumentar conforme necessário. Oferecem mais flexibilidade mas também exigem gerenciamento mais complexo da memória.
	Exemplo: Listas Encadeadas e árvores dinâmicas

#### Vantagens e Desvantagens da utilização da estrutura de dados
##### Vantagens:
- Reutilização do Código
- Manutenção
- Eficiência

#### Desvantagens
- Limitação em Problemas Complexos
	Podem não ser eficientes na resolução de problemas de maior complexidade.
- Dificuldade na Adaptação
	Complementando com a de desvantagem de cima a medida que os requisitos aumentam talvez seja difícil adpatá-lo para as novas demandas.
- Não são Universais
	Nem todos os problemas pode ser resolvidos eficientemente com algoritmos e estruturas básicos

## Slide 2  - Estruturas Estáticas

Como dito mais em cima as estrutura estáticas referem-se a ==estrutura de dados que têm um tamanho fixo durante toda a execução do programa.==

As estruturas de dados ==são alocadas na memória durante a compilação e não podem ser alteradas em tempo de execução.==

As principais estruturas Estáticas são:
- Vetores
- Matrizes
- Registros
#### Vetores
Conjunto de variáveis de mesmo tipo, que possuem o mesmo identificador e são alocados sequencialmente na memória.

Para se referir a um vetor você precisa colocar o nome do vetor seguido da posição(chamado de ==Índice==) que você quer acessar entre colchetes:
	`nome_do_vetor[posicao_do_vetor]`
	obs: O primeiro índice de um vetor em c++ é sempre 0.

Por ser um índice de tamanho ele é definido durante a declaração
 ex:
Vetor n = 3 , 4 , 8 , 9 ,15
```cpp
n[0] = 3
n[1] = 4
n[2] = 8
n[3] = 9
n[4] = 15
```

#### Matrizes
As matrizes são estruturas bem parecidas com os vetores, no caso de apresentar um tamanho fixo, a diferença é que ela é bidimensional, organizado em linhas e colunas.

Para se referir a uma matriz novamente é bem parecido com um vetor mas você irá passar mais um parâmetro entre colchetes para acessar a linha
`nome_da_matriz[indice_da_coluna][indice_da_coluna]`

| `n[0][0]` = 1 | `n[0][1]` = 2 | `n[0][2]` = 3 | `n[0][3]` = 0 |
| ------------- | ------------- | ------------- | ------------- |
| `n[1][0]` = 4 | `n[1][1]` = 5 | `n[1][2]` = 6 | `n[1][3]` = 0 |
| `n[2][0]` = 7 | `n[2][1]` = 8 | `n[2][2]` = 9 | `n[2][3]` = 7 |

* Sempre lembrar que começa no 0 tanto a linha quanto a coluna, a ==linha vem primeiro== e ==depois a coluna== na hora de acessar um valor. Os valores dos indices da matriz devem ser números inteiros. Expressões podem ser calculadas caso o resultado seja um inteiro

#### Registros
Em uma matriz ou vetor o termo "registros" se referem a um elemento específico localizado em uma determinada posição, como por exemplo utilizando a matriz de cima o registro: `N = [2][3]` = 6, e em um vetor isso é mais simples pois seria contar os valores começando com `n[0]`

##### Operações básicas: Inserção, Remoção, Acesso e Atualização
1 - Inserção: Incorporar elementos adicionais a uma estrutura preexistente, e por ocorrer em diferentes posições, como no inicio, no final ou em uma posição específica da estrutura.

2 - Remoção: Excluir algum valor especifico com base no valor ou na posição

3 - Acesso: Recuperar ou consultar dados armazenados na estrutura, a eficiência no acesso pode variar conforme o tipo de estrutura de dados utilizada, como listas, arrays, árvores, entre outras.

4 - Atualização: Modificar ou Alterar o valor de um elemento existente na estrutura de forma controlada e dinâmica.

Vantagens das Estruturas Estáticas: 
	Simplicidade: São fáceis de entender e implementar
	Eficiência: O acesso direto aos elementos permite um tempo de execução eficiente
Desvantagens das Estruturas Estáticas:
	Tamanho fixo: Pode ser uma limitação o tamanho do vetor/matriz
	==Desperdício de memória: Pode ocorrer se o tamanho alocado for maior do que o necessário.==

Existem várias aplicações práticas para o a estrutura de dados estáticas dentre elas:
	Banco de dados relacionais
	Processamento de imagens e vídeos
	==Configuração de Hardware==
	==Configuração de Redes==
	Representação de matrizes Esparsas
	Aplicações Gráficas
	==Configuração de Jogos==
	Bibliotecas de Elementos Gráficos
	Compiladores e Analisadores Sintáticos
	Armazenamento de Configurações de software
	==Sistemas Embarcados==
	==Sistemas Operacionais==

Configuração de Hardware: Em programação de baixo nível e sistemas embarcados, estruturas de dados estáticas são usadas para representar configurações fixas de hardware, como registradores e memória de dispositivos.

Configuração de Redes: Ao lidar com configurações de rede, como tabelas de roteamento em roteadores, estruturas de dados estáticas são empregadas para otimizar o roteamento e o encaminhamento de pacotes.

Configurações de jogos: Em jogos de vídeo, as configurações estáticas, como mapas e layouts, podem ser representadas usando estruturas de dados estáticas para facilitar o acesso e a manipulação.

Sistemas Embarcados: Em sistemas embarcados, onde os recursos são limitados, estruturas
 de dados estáticas são preferíveis para evitar o uso excessivo de memória dinâmica.

Sistemas Operacionais: Estruturas de dados estáticas são usadas em sistemas operacionais para representar tabelas de processos, registros de arquivos e outras estruturas fixas.


## Slide 3  - Estruturas Dinâmicas

Ao contrário das estruturas estáticas as ==estruturas dinâmicas são coleções de dados que podem crescer ou diminuir de tamanho durante a execução do programa==

Fornecem flexibilidade para manipular conjunto de dados cujo tamanho que podem variar conforme a execução de um programa.

As estruturas de dados dinâmicas ==permitem a alocação e liberação dinâmica de memória== durante a execução do programa.

>O uso adequado de estruturas de dados dinâmicas requer gerenciamento cuidadoso da memória para evitar vazamentos de memória e outros problemas relacionados à alocação e desalocação dinâmica de recursos. Um entendimento sólido dos princípios de alocação dinâmica de memória e práticas de programação seguras é fundamental para aproveitar ao máximo o potencial dessas estruturas de dados dinâmicas.
>\ - Importante estudar essa parada.


Os tipo de estruturas dinâmicas mais utilizados são:
	Listas Ligadas: Simples, Duplas, Circulares
	Filas e Pilhas Dinâmicas.
	Árvores e Grafos Dinâmicos.


Vantagens da estrutura Dinâmica: 
	Flexibilidade, Eficiência de Memória, Desempenho.
Desvantagens: 
	Complexidade de Implementação, Acesos Aleatório Limitado

Para entender melhor a alocação Dinâmica é necessário um entendimento dos conceitos de **ponteiros** e **alocação dinâmica de memória**(será abordado depois no MD)


## Slide 4 - Ponteiros 

### Ponteiros

==São variáveis que armazenam endereços de memória em vez de armazenar diretamente valores de dados.== Eles são fornecem uma abordagem flexível e eficiente para lidar com dados que podem crescer ou diminuir durante a execução de um programa.

==Eles permitem que você manipule diretamente a memória do computador==, o que pode ser eficiente e flexível quando usado corretamente, mas também ==pode ser fonte de bugs difíceis de detectar e entender.==

Os ponteiros são muito úteis quando se tem uma situação em que uma variável precisa ser acessada em diferentes partes do programa.

Existem 3 propósitos principais para os ponteiros:
- Para alocar novos objetos no head
- Para passar funções para outras funções
- Para iterar sobre os elementos em matrizes ou outras estruturas de dados

Em c++, os conceitos de endereço e ponteiro são explícitos, em outras linguagens eles são ocultos(e representados pelo conceito mais abstrato de referência).


```cpp
#include <iostream>
using namespace std;

	int main() {
	int *ptr;
	int valor = 2;
	ptr = &valor;
	
	cout << "Endereço = " << hex << &valor << endl;
	cout << "Endereço = " << hex << ptr << endl;
	cout << "Valor = " << dec << *ptr << endl;
	return EXIT_SUCCESS;
}
```


```cpp

```


```cpp

```


#### Endereços
A memória RAM de qualquer computador é uma sequência de bytes. A posição(0, 1, 2, 3 , etc) que um byte ocupa na sequência é o endereço do byte. Cada variável de um programa ocupa um certo número de bytes consecutivos na memória do computador.
	char = 1 byte
	int = 4 bytes
	double = 8 bytes



```cpp
#include <iostream>
using namespace std;
	int main() {
	int num = 47;
	int *ptr;
	ptr = &num;
		cout << "Valor de num: " << num << endl; //47
		cout << "Endereço de num: " << &num << endl; //0x61ff08
		cout << "Valor apontado por ptr: " << *ptr << endl; //47
		cout << "Endereço armazenado em ptr: " << ptr << endl; //0x61ff08
return 0;
}
```
	Output:
	 Valor de num: 47
	Endereço de num: 0x61ff08
	Valor apontado por ptr: 10
	Endereço armazenado em ptr: 0x61ff08

	Explicação: no primeiro ele está somente acessando o valor de num, no segundo esse & é um operador que aceesa o local da variável na RAM, no terceiro é um ponteiro que está somente acessando o valor da variável num e o quarto está acessando o valor do endereço do ponteiro pois `:ptr = &num`

```cpp

```


```cpp

```



## Slide 5 - Alocação Dinâmica de Memória
```cpp
#include <iostream>
using namespace std;
	
int main() {
	int tamanho;
	cout << "Digite o tamanho do array: ";
	cin >> tamanho;
	
//alocação dinâmica do array
	int *array = new int[tamanho];
	cout << "Digite " << tamanho << " Números inteiros:\n";

//leitura dos elementos do array
	for (int i = 0; i < tamanho; ++i){ 
		cin >> array[i];
	}
	
	cout << "Valores do array:\n";
	
//Para exibir os valores do array
	for (int i = 0; i < tamanho; ++i){ 
		cout << array[i] << " ";
	} 
	cout << endl;
	
//liberação de memória alocada
	delete[] array; //Evita vazamentos de memória
return 0;
}
```
	Explicação: O programa pede o tamanho do array, depois pede para o usuário colocar os números que compoem esse array e após isso printa na tela o array completo em sequencia(simples)
e

```cpp

```

```cpp

```



# 2° Ciclo  
## Slide 1 - Listas

É uma estrutura de dados que organiza elementos em uma sequência ordenada. Cada elemento é chamado de nó e possui uma relação com o próximo elemento na sequência. 

O Funcionamento da lista envolve a capacidade de:
- Adicionar
- Remover
- Acessar Elementos
Normalmente os elementos da lista são acessados sequencialmente, começando pelo primeiro.

Tipos de Listas:
### 1 -  Encadeadas(pesquisar)

### 2 - Encadeadas Simples
Cada nó possui um elemento de dados e um ponteiro para o próximo nó na sequência, e o último nó tem como próximo nó um valor inválido, para indicar o fim da lista.
### 3 -  Encadeadas Dupla
É similar a Encadeada Simples mas cada nó possui um ponteiro para o próximo e para o nó anterior na sequência. Segue a mesma lógica do referencial para o próximo nó do ultimo como inválido, assim como o antes do primeiro.
### 4 - Encadeada Circular
Cada nó armazena o elemento e uma referência para o próximo nó. A diferença é que o último nó "aponta" por meio do ponteiro para o primeiro nó da lista, dando seu comportamento circular.
### 5 - Duplamente Encadeada Circular
Junta a Encadeada Dupla com circular, fazendo com que cada nó aponte para o anterior e o próximo e o primeiro elemento apontar para o ultimo e vice-versa.



Vantagens do uso da Lista:
- Flexibilidade: Dá para inserir ou remover os elementos em qualquer posição.
- Eficiência: Operadores de inserção ou remoção podem ser rápidos, em comparação com os arrays estáticos
- Estrutura Dinâmica: Pode crescer ou encolher conforme necessário, sem a necessidade de realocação de memória.
Desvantagens do uso de Listas:
- Acesso Sequencial: Para o acesso a elementos específicos é menos eficiente.
- **==Overhead de Memória**: Cada nó da lista requer espaço adicional para armazenar ponteiros, o que consome mais memória.==
- Complexidade: É mais complexo manter a integridade da lista

Usos das listas:
 Gerenciamento de memória dinâmica em linguagens de programação.
 Processamento de grandes conjuntos de dados onde a ordem dos elementos é importante.


Em C++ cada nó da lista armazena dois elementos essenciais: 
**Dado**: Representa o valor que o nó guarda podendo ser: int, float, char ou até objetos de outras classes 
**Próximo**: É ponteiro que aponta para o próximo nó na sequência da lista

Exemplo de Inserção e Travessia na lista, onde ele coloca os números com a função `push_back` e depois percorre a lista com o `for`
```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
	// Criando uma lista de inteiros
	list<int> MinhaLista;
	// Inserindo elementos na lista
	MinhaLista.push_back(5);
	MinhaLista.push_back(10);
	MinhaLista.push_back(15);
	// Imprimindo os elementos da lista
	cout << "Lista: ";
	
	for (auto it = MinhaLista.begin(); it != MinhaLista.end(); ++it) {
		cout << *it << " ";
	}
	cout << endl;
return 0;
}
```


## Slide 2 - Filas
É uma estrutura de dados linear que segue o principio **FIFO**(First In, First Out), onde o primeiro elemento inserido é o primeiro a ser removido

A fila segue o mesmo principio de uma fila de pessoas normais onde o primeiro que entrou será o primeiro a ser atendido e irá sair.

A fila pode ser implementada com vetores ou com listas encadeadas, dependendo da quantidade máxima de elementos que cabem na fila.

Tipos de Filas:
### 1- Fila Simples
Também conhecida como linear ou fila padrão, é a forma mais básica de fila

As operações de **inserção** de elementos são realizados no final da fila(ou na cauda), enquanto as operações de **remoção** são feitas no inicio da fila(cabeça), assim seguindo a politica FIFO, onde o primeiro elemento a entrar é o primeiro a sair.

Criando uma fila e inserindo três valores com a função `.push` 
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
	queue<int> fila;
	
	// Inserindo elementos na fila
	fila.push(10);
	fila.push(20);
	fila.push(30);
	
	// Mostrando e removendo elementos da fila
	while (!fila.empty()) {
		cout << "Elemento na frente: " << fila.front() << endl;
	//com esse trecho a fila vai retirar um elemento por interação 
		fila.pop();
	}
	
	return 0;
}
```


### 2 - Fila Dupla
É uma estrutura de dados que permite inserção e remoção de elementos em ambos os extremos(cauda e cabeça), **mas nenhum elemento pode ser adicionado ou excluído do meio**

É implementada usando uma lista circular duplamente encadeada. São mantidos LEFT E RIGHT, que apontam para qualquer extremidade do deque.

Operações Básicas:
- Inserção na extremidade traseira;
- Inserção na extremidade frontal;
- Remoção na extremidade frontal;
- Remoção na extremidade traseira;

Inserção na extremidade frontal: Sendo que o 8  era a 'cabeça' e depois virou o 32 e o 9 permaneceu como 'cauda'

|     | 8   | 99  | 48  | 9   |
| --- | --- | --- | --- | --- |
| 32  | 8   | 99  | 48  | 9   |

**Remoção na extremidade traseira:** O 9 erá a 'cauda' e após a remoção 0 48 ficou como a 'cabeça'

| 32  | 8   | 99  | 48  | 9   |
| --- | --- | --- | --- | --- |
| 32  | 8   | 99  | 48  |     |


Os outros seguem a mesma lógica, quando adicionado ele ocupa o lugar do que estava e para remover o "próximo" valor assume o lugar.

Para criar uma Fila Dupla e colocar os dados de forma diferente da normal e depois mostrar na tela.
```cpp
#include <iostream>
#include <deque>
using namespace std;

int main() {
	deque<int> filaDupla;
	
	// Inserindo elementos no começo e no fim da fila
	filaDupla.push_back(10);
	filaDupla.push_front(20);
	filaDupla.push_back(30);
	
	// Mostrando e removendo elementos da fila
	while (!filaDupla.empty()) {
		cout << "Elemento na frente: " << filaDupla.front() << endl;
		filaDupla.pop_front();
	}
	return 0;
}
```

### 3 - Fila Circular
É uma variação da fila simples, onde o último elemento aponta primeiro elemento formando um círculo lógico.

Funciona da seguinte maneira, a medida que os dados são retirados o head muda e quando os dados são adicionados vão para o final(contanto que haja espaço) mesmo que o final não seja igual certinho nas casa normais


| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | 4   | 5   | 6   | 7   | 8   | 9   |
| 10  | 11  |     |     | 4   | 5   | 6   | 7   | 8   | 9   |
| 10  | 11  | 12  |     |     |     | 6   | 7   | 8   | 9   |

1° - A fila com 10 números sendo 0(head) e 9(tale)
2° - Retirado 4 números(do começo pois é um FIFO) sendo 4(head) e 9(tale)
3° - Adicionado 2 números sendo 4(head) e 11(tale)
4° - Retirado 2 números e adicionado 1sendo 6(head) e 12(tale)
	Segue a lógica.

É um exemplo de fila circular usando POO entretanto não entendi muito como funciona
```cpp
#include <iostream>
using namespace std;

class FilaCircular {
private:
    int *fila, capacidade, frente, tras, tamanho;
public:
    FilaCircular(int cap) : capacidade(cap), fila(new int[cap]), frente(0), tras(-1), tamanho(0) {}
        ~FilaCircular() { delete[] fila; }
    bool isFull() { return tamanho == capacidade; }
    bool isEmpty() { return tamanho == 0; }
    void enfileirar(int valor) { if (!isFull()) fila[++tras % capacidade] = valor, ++tamanho; }
    void desenfileirar() { if (!isEmpty()) ++frente %= capacidade, --tamanho; }
    int frenteElemento() { return isEmpty() ? (cout << "Fila vazia" << endl, -1) : fila[frente]; }
};

int main() {
    FilaCircular fila(5); fila.enfileirar(10), fila.enfileirar(20), fila.enfileirar(30);
    while (!fila.isEmpty()) cout << "Elemento na frente: " << fila.frenteElemento() << endl,
    fila.desenfileirar();
return 0;
}
```

### 4 - Fila de Prioridade

É uma estrutura de dados onde cada elemento possui uma prioridade associada, **elas não seguem a ordem FIFO, mas sim a prioridade dos elementos, removendo primeiro aquele com a maior(ou menor, dependendo da implementação).**

```cpp
#include <iostream>
#include <queue>
#include <vector>
using namespace std;

int main() {

	// Maior prioridade tem o maior valor
	priority_queue<int> filaPrioridade;
	
	// Inserindo elementos na fila de prioridade
	filaPrioridade.push(10);
	filaPrioridade.push(20);
	filaPrioridade.push(30);
	
	// Mostrando e removendo elementos da fila de prioridade
	while (!filaPrioridade.empty()) {
		cout << "Elemento de maior prioridade: " << filaPrioridade.top() << endl;
		filaPrioridade.pop();
	}
return 0;
}

```

Sistemas de Chamados(TED 2)
```cpp
#include <iostream>
#include <queue> // Listas FIFO
#include <string>
using namespace std;

//classe atendimento
class Atendimento {
public:
    //atributos
    int id;
    string descricao;

    //construtor(inicializador dos atributos)
    Atendimento(int id, string& descricao) : id(id), descricao(descricao) {}
};

//classe sistema de atendimento
class SistemaAtendimento {
private:

    queue<Atendimento> filaNormal;//Chamados normais
    queue<Atendimento> filaPrioritaria;//Chamados prioritarios
    int proximoId;

public:
    //construtor
    SistemaAtendimento() : proximoId(1) {}

     //1 - Adicionar chamado
    void adicionarChamado() {
        string descricao;
        int prioridade;

        cout << "Digite a descricao do chamado: ";
        cin.ignore();
        getline(cin, descricao);
        
        cout << "Digite a prioridade (0 para normal, 1 para prioritario): ";
        cin >> prioridade;

        Atendimento novoChamado(proximoId++, descricao);
        
        if (prioridade == 1) {
            filaPrioritaria.push(novoChamado);
            cout << "Chamado prioritario adicionado com sucesso! ID: " << novoChamado.id << endl;
        } else {
            filaNormal.push(novoChamado);
            cout << "Chamado normal adicionado com sucesso! ID: " << novoChamado.id << endl;
        }
    }

	//2 - Processo do chamado
    void processarChamado() {
        if (!filaPrioritaria.empty()) {
            Atendimento chamadoAtual = filaPrioritaria.front();
            filaPrioritaria.pop();
            cout << "Processando chamado prioritario ID: " << chamadoAtual.id << " - " << chamadoAtual.descricao << endl;
        } else if (!filaNormal.empty()) {
            Atendimento chamadoAtual = filaNormal.front();
            filaNormal.pop();
            cout << "Processando chamado normal ID: " << chamadoAtual.id << " - " << chamadoAtual.descricao << endl;
        } else {
            cout << "Nenhum chamado na fila para processar." << endl;
        }
    }

//3 - Exibicao de chamados
    void exibirChamados() const {
        queue<Atendimento> copiaNormal = filaNormal;
        queue<Atendimento> copiaPrioritaria = filaPrioritaria;
        int nTamanho = filaNormal.size();
        int pTamanho = filaPrioritaria.size();

        cout << "Chamados prioritarios na fila:" <<  pTamanho << endl;
        if (copiaPrioritaria.empty()) {
            cout << "Nenhum chamado prioritario na fila." << endl;
        } else {
            while (!copiaPrioritaria.empty()) {
                Atendimento chamado = copiaPrioritaria.front();
                copiaPrioritaria.pop();
                cout << "ID: " << chamado.id << " - " << chamado.descricao << endl;
            }
        }
        cout << "Chamados normais na fila:" << nTamanho << endl;
        if (copiaNormal.empty()) {
            cout << "Nenhum chamado normal na fila." << endl;
        } else {
            while (!copiaNormal.empty()) {
                Atendimento chamado = copiaNormal.front();
                copiaNormal.pop();
                cout << "ID: " << chamado.id << " - " << chamado.descricao << endl;
            }
        }
    }
};

int main() {
    SistemaAtendimento sistema;
    int opcao;

    do {
        cout << "Sistema de Atendimento" << endl;
        cout << "1. Adicionar chamado" << endl;
        cout << "2. Processar chamado" << endl;
        cout << "3. Exibir chamados na fila" << endl;
        cout << "4. Sair" << endl;
        cout << "Escolha uma opcao: ";
        cin >> opcao;

        switch (opcao) {
            case 1:
                sistema.adicionarChamado();
                break;
            case 2:
                sistema.processarChamado();
                break;
            case 3:
                sistema.exibirChamados();
                break;
            case 4:
                cout << "Saindo do sistema..." << endl;
                break;
            default:
                cout << "Opcao invalida! Tente novamente." << endl;
        }
    } while (opcao != 4);
    return 0;
}

```

**Vantagens do Uso de Fila:**
- Simplicidade: Implementação e entendimento das operações de fila são simples
- Gerenciamentos de Processos: Filas são úteis em sistemas operacionais para gerenciamento de tarefas
- Organização Natural: Refletem processos naturais, como filas em sistemas de atendimento.

**Desvantagens do Uso de Fila:**
- Acesso Limitado: Só é possível acessar os elementos na frente e no final da fila
- Desempenho: Pelo deslocamento de elementos o desempenho pode ser prejudicado.

LISTA X FILA
```cpp

```

```cpp

```


## Slide 3 - Pilha
São estruturas de dados que armazenam os elementos em um formato sequencial, empilhando um item acima do outro. 

Sempre quando um novo elemento é inserido, damos a ele o nome de "topo", pois é o primeiro elemento ao qual teremos acesso.
Além do topo existe o elemento base, que representa o elemento mais antigo.

Os elementos são adicionados e removidos na mesma extremidade, que **é o topo da pilha**, seguindo o padrão LIFO(Last In First Out), onde o último a entrar será o primeiro a sair.

Operações Básicas em Pilha
- Push: Adiciona um item ao topo da pilha
- Pop: Remove um item ao topo da pilha
- Top: Acessa um item ao topo da pilha sem removê-lo
- IsEmpty: Verifica se a pilha está vazia.

Exemplos: Navegação entre páginas web; O mecanismo de desfazer/refazer dos editores de texto.

Vantagens do Uso de Pilha:
- Simplicidade: Das operações de Push e Pop, são simples e eficientes
- Uso de Memória.

Desvantagens:
- Acesso Limitado: só é possível acessar o elemento do topo da pilha
- Menor Flexibilidade: Em comparação com as listas ou filas

PILHA X FILA

```cpp

```

```cpp

```

```cpp

```

```cpp

```

```cpp

```
