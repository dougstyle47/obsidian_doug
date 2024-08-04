
## **Pergunta 1** (0,2 pontos)
O conceito: _“[...] são estruturas hierárquicas que representam relações entre elementos, as quais permitem organizar dados de forma eficiente“_ se refere a

|     | Listas Ligadas             |
| --- | -------------------------- |
| X   | Árvores e Grafos Dinâmicos |
|     | Filas e Pilhas Dinâmicas   |
|     | Vetores.                   |
|     | Matrizes.                  |
Justificativa: 
  
A estrutura hierárquica que é mencionada na sua descrição parece se referir a uma **árvore**. Uma árvore é uma estrutura de dados na qual os elementos, chamados de nós, são organizados hierarquicamente. Cada nó pode ter um ou mais nós filhos, formando assim uma estrutura hierárquica.

Na descrição que você forneceu, "elementos" podem ser interpretados como os nós da árvore, e as "relações entre elementos" seriam as conexões entre os nós (ou seja, quais nós são pais de quais outros nós). Organizar dados de forma eficiente refere-se à capacidade da estrutura de árvore de facilitar operações como busca, inserção e exclusão de elementos.

As árvores são amplamente utilizadas em ciência da computação e têm diversas aplicações, desde estruturas de diretórios em sistemas de arquivos até representações de dados em algoritmos de busca, como árvores binárias de busca e árvores de decisão, entre outras.

## **Pergunta 2** (0,2 pontos)

 **O conceito: “A capacidade de expandir ou reduzir a quantidade de memória alocada dinamicamente torna possível lidar com estruturas de dados que podem crescer ou encolher ao longo do tempo.” se refere a que vantagem oferecida pela alocação dinâmica?**

|   X | Flexibilidade.             |
| --- | -------------------------- |
|     | Uso Eficiente de Recursos. |
|     | Reutilização de Memória.   |
|     | Dinamismo.                 |
|     | Desempenho.                |

Justificativa:
Essa afirmação se refere à vantagem da alocação dinâmica de memória em permitir a gestão flexível e eficiente da memória para estruturas de dados que podem ter tamanhos variáveis ao longo do tempo. A capacidade de expandir ou reduzir a quantidade de memória alocada dinamicamente é uma característica importante da alocação dinâmica de memória, que oferece diversas vantagens, incluindo:

1. **Flexibilidade**: A alocação dinâmica permite que programas aloquem memória conforme necessário durante a execução do programa, em vez de alocar toda a memória necessária antecipadamente. Isso é particularmente útil para estruturas de dados cujo tamanho pode variar dinamicamente, como listas encadeadas, árvores e pilhas.
    
2. **Eficiência**: A alocação dinâmica de memória evita a necessidade de reservar uma quantidade fixa de memória para uma estrutura de dados, mesmo quando essa estrutura raramente atinge seu tamanho máximo. Isso ajuda a evitar o desperdício de memória e permite uma utilização mais eficiente dos recursos do sistema.
    
3. **Gerenciamento de recursos**: A alocação dinâmica permite que os recursos de memória sejam liberados quando não forem mais necessários, ajudando a evitar vazamentos de memória e garantindo que a memória seja utilizada de forma otimizada ao longo do tempo.
    
4. **Adaptabilidade**: Com a alocação dinâmica, os programas podem se adaptar dinamicamente às mudanças nos requisitos de memória, permitindo uma resposta mais flexível a diferentes cenários de uso e evitando problemas de alocação estática de memória que podem surgir com tamanhos imprevisíveis de dados.


## **Pergunta 3** (0,2 pontos)

**O conceito:_“A alocação dinâmica permite que os programas ajustem dinamicamente o uso da memória conforme necessário durante a execução, acomodando situações em que o tamanho exato da memória não é conhecido antecipadamente."_ se refere a que vantagem oferecida pela alocação dinâmica?**

|     |                            |
| --- | -------------------------- |
|     | Uso Eficiente de Recursos. |
| X   | Flexibilidade.             |
|     | Desempenho.                |
|     | Dinamismo.                 |
|     | Reutilização de Memória.   |

Justificativa:
A vantagem oferecida pela alocação dinâmica de memória que melhor se encaixa nessa descrição é:

**Flexibilidade:** A alocação dinâmica permite que os programas ajustem dinamicamente o uso da memória conforme necessário durante a execução. Isso é especialmente útil quando o tamanho exato da memória necessário não é conhecido antecipadamente, pois a alocação dinâmica permite acomodar situações em que as necessidades de memória podem variar ao longo do tempo.


## **Pergunta 4** (0,2 pontos)

```cpp
#include <iostream>
using namespace std;

void swap(int *ptrA, int *ptrB){
    int temp = *ptrA;
    *ptrA = *ptrB;
    *ptrB = temp;
}
int main(){
    int a = 5;
    int b = 10;
    
    cout << "Valores iniciais: "<<endl;
    cout << "a: "<< a << endl;
    cout << "b: "<< b << endl;

    swap(&a,&b);
    cout << "\nValores após a troca: " <<endl;
    cout << "a: "<< a << endl;
    cout << "b: "<< b << endl;

return 0;
}
```
 output:
 Imprime "Valores iniciais:", seguido por "a: 5" e "b: 10". Depois, imprime "Valores após a troca:" seguido por "a: 10" e "b: 5".

## **Pergunta 5** (0,2 pontos)
```cpp
#include <iostream>
using namespace std;

int main(){
	int x = 5;
	int y = 10;
	int *ptr = &x;
	*ptr +=y;
	ptr++;
	(*ptr)--;
	x *= (*ptr);
	cout << "Valor de x: " << x << endl;
	return 0
}
```
output: 
135

## **Pergunta 6** (0,2 pontos)

**Qual das seguintes afirmações descreve uma premissa básica para o desenvolvimento de um algoritmo eficiente, conforme descrito no texto?**

|     | Estabelecer uma sequência infinita de passos. |
| --- | --------------------------------------------- |
|     | Organizar as ações de forma aleatória.        |
|     | Definir ações simples e ambíguias.            |
|     | Definir ações complexas e intricadas.         |
|   X | Definir ações simples e sem ambiguidade.      |
justificativa:
Algoritmos eficientes são construídos sobre a base de ações simples e claramente definidas, onde cada passo é preciso e inequívoco. Isso permite uma compreensão clara do comportamento do algoritmo e facilita sua implementação, teste e manutenção. A ambiguidade pode levar a erros de interpretação e dificultar a compreensão do algoritmo, resultando em um desempenho inferior. Portanto, definir ações simples e sem ambiguidade é essencial para o desenvolvimento de algoritmos eficientes.

## **Pergunta 7** (0,2 pontos)
**Um algoritmo possui uma estrutura básica composta de: Sequência, Seleção (ou condicional), Repetição (ou iteração).**

**Nesse contexto, analise as seguintes afirmativas:**
**I. A sequência refere-se a uma série ordenada e lógica de instruções ou comandos que são executados de forma sequencial, um após o outro.**
**II. A Seleção (ou Condicional) está relacionada a uma tomada de decisões com base em condições.**
**III. A repetição que também conhecida como Iteração, é uma execução repetida de um conjunto específico de instruções.**

**Está CORRETO o que se afirmar somente em:**

|     |              |
| --- | ------------ |
|     | III.         |
|     | II.          |
| X   | I, II e III. |
|     | I.           |
|     | I e II.      |
Justificativa:
- A afirmação I está correta: A sequência refere-se a uma série ordenada e lógica de instruções executadas sequencialmente.
- A afirmação II está correta: A seleção (ou condicional) envolve tomar decisões com base em condições específicas.
- A afirmação III está correta: A repetição (ou iteração) implica na execução repetida de um conjunto específico de instruções


## **Pergunta 8** (0,2 pontos)

```cpp
#include <iostream>
using namespace std;

int main(){
	int n;
	cout << "Digite o tamanho do array: ";
	cin >> n;
	int *array = new int[n]();
	for(int i = 0; i < n; ++i)
		array[i] = ( i + 1) * 2 - 1;
	cout << "Array gerado: ";
	for(int i = 0; i < n; ++i)
		cout << array[i] << " ";
	cout << endl;
	delete[]array;
	return 0;
}
```
O resultado do código será: Array dinâmico com números impares começando de 1.

justificativa : Isso porque o código aloca dinamicamente um array de inteiros (`int *array = new int[n]()`) e preenche esse array com números ímpares (`array[i] = (i + 1) * 2 - 1;`).


## **Pergunta 9** (0,2 pontos)

```cpp
#include <iostram>
using namespace std;

int main() {
	int x = 4;
	int y = 1;
	int z = x + (y * y) / x;
	cout<< "O valor de z é " << z << endl;
	retun 0;
}
```
Resultado: O valor de z é: 4

## **Pergunta 10** (0,2 pontos)
**Em relação aos tipos de estruturas de dados estáticas, analise as afirmativas a seguir:**

**I – Vetor é um conjunto de variáveis de mesmo tipo, que possuem o mesmo identificador (nome) e são alocadas sequencialmente na memória.**
**II – Uma matriz é uma coleção bidimensional de elementos, organizados em linhas e colunas.**
**III - O termo "_registros_" geralmente se refere a elementos individuais ou entradas em uma matriz ou vetor.**

**Está CORRETO o que se afirmar somente em:**

Opções de pergunta 10:

|     | I.           |
| --- | ------------ |
|     | II.          |
|     | I e II.      |
|     | III.         |
| X   | I, II e III. |
justificada:
- A afirmação I está correta: Um vetor é realmente um conjunto de variáveis do mesmo tipo, com o mesmo identificador (nome), alocadas sequencialmente na memória.
- A afirmação II está correta: Uma matriz é uma coleção bidimensional de elementos organizados em linhas e colunas.
- A afirmação III está correta: O termo "registros" pode se referir a elementos individuais ou entradas em uma matriz ou vetor.

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