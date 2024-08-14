##  Cap 1 - Introdução a algoritmos

==Um algoritmo é um conjunto de instruções que realizam uma tarefa==. A ideia do livro é fazer com que vejamos os desempenhos de diferentes algoritmos para escolher melhor qual o melhor para utilizar na sua estrutura de dados.

## Pesquisa Binária
A pesquisa binária é um algoritmo. Sua entrada é uma lista ordenada de elementos, caso o objeto que você esteja procurando esteja lá ele retorna sua localização, caso contrário retorna `none`.

A pesquisa Binária consiste em dividir a quantidade de números pela metade e partindo dai elimina metade dos números restantes a cada vez. Diferente da pesquisa simples que iria conferir valor por valor até achar o objeto(palavra, numero).

**A pesquisa binária só funciona caso a lista esteja ordenada.**

- Em uma pesquisa de 240 mil palavras na "pior das hipóteses":
	- Pesquisa simples : 240 mil tentativas
	- Pesquisa binária: 18 tentativas
		- 240mil > 120mil > 60 mil > 30 mil > 15 mil > 7500 > 3750 > 1875 > 938 > 469 > 235 > 118 > 59 > 30 > 15 > 8 > 4 > 2 > 1/  Você elimina metade dos números com a pesquisa binária
		Obs: Quando o valor resultante do cálculo é um float (como 3,45), assumimos a parte inteira como o índice do elemento do meio ou seja 3;

Pesquisa binária em Python (apresentado no livro)
``` python 
def pesquisa_binaria (lista, item):
    baixo = 0
    alto = len(lista) - 1 
    
    while baixo <= alto:
        meio = (baixo + alto) // 2
        chute = lista[meio]
        
        if chute == item:
            return meio
        if chute > item:
            alto = meio - 1
        else: 
            baixo = meio + 1
    return 
    
minha_lista = [1,2,3,5,7,9,10,11,12,13,14,15,16,17,18,19,20,21,22]
print(pesquisa_binaria(minha_lista, 21))
print(pesquisa_binaria(minha_lista, -1))
```

Códigos de pesquisa binária em C++(Eu)
``` cpp
#include <iostream>
#include <vector>
using namespace std;

int pesquisa_binaria(lista, item)
    baixo = 0;
    alto = length(lista) - 1;
    
    while(baixo < = alto){
        meio = (baixo + alto) / 2;
        chute = lista[meio]

        if(chute == item){
           return meio;
           
        } else if (chute > item){
           alto = meio - 1;
           
        }else{

            baixo = meio + 1
        }
    return none;
    }
  
int main {
    minha_lista[1,3,5,7,9]
    cout << pesquisa_binaria(minha_lista,3);
    cout << pesquisa_binaria(minha_lista,-1);
}
```

Código de pesquisa binária em C++(Recebendo os valores(tamanho do array e target) do usuário)
``` cpp
#include <iostream>
#include <vector>
using namespace std;

int buscaBinaria(const vector<int>& v, int k) {
    int l = 0, r = v.size() - 1;
        while (l <= r) {
            int m = (l + r) / 2;
        if (v[m] == k) return m;
            (v[m] < k) ? l = m + 1 : r = m - 1;
        }
    return -1;
}

int main() {
    //recebendo o tamanho do vetor #simples
    int tamanho;
    cout << "Tamanho do vetor: ";
    cin >> tamanho;

    //Declara um vetor que pode conter elementos do tipo inteiro(int)
    // -' vector' é uma estrutura de dados da biblioteca padrão do C++ que fornece um 
    // contêiner dinamico para armazenar elementos em sequencia.
    vector<int> vetor(tamanho);
    cout << "Elementos em ordem crescente:\n";
    for (int i = 0; i < tamanho; cin >> vetor[i++]);

    //recebendo o valor a ser buscado
    int elemento;
    cout << "Elemento a buscar: ";
    cin >> elemento;

    int i = buscaBinaria(vetor, elemento);

    (i != -1) ? cout << "Encontrado na posicao " << i << endl : cout << "Nao encontrado." << endl;

    return 0;
}

```

### Big O 
Logaritmos

Não basta saber quanto tempo um algoritmo leva para ser executado - você precisa saber se o tempo de execução aumenta conforme a lista aumenta. A notação Big O não fornece o tempo em segundos, ela permite que você comparte o número de operações. Ela informa o quão rapidamente um algoritmo cresce.

A notação Big O leva em consideração a pior das hipóteses, então pode-se dizer que, para o pior caso, você analisou cada item da lista.

Exemplos de execução Big O:
	O(log n) - Também conhecido como tempo logarítmico. Pesquisa Binária
	O(n) - Conhecido como tempo linear. Pesquisa Simples
	O(n * log n) - Quicksort
	O(n²) - Ordenação por seleção
	O(n!) - Caixeiro Viajante

#### O caixeiro viajante(Problema)
O caixeiro precisa passar por todas as cinco cidades percorrendo uma distância mínima. Ele precisa analisar a passagem por 5 cidades o que dá um total de 120 operações para resolver o problema. Se caso sejam 6 cidades o número de operações passa a 720 operações ou permutações, para 7 cidades são necessárias 5.050 operações.

| Cidades | Operações                         |
| ------- | --------------------------------- |
| 6       | 720                               |
| 7       | 5040                              |
| 8       | 40320                             |
| ...     | ...                               |
| 15      | 1307674368000                     |
| ...     | ...                               |
| 30      | 265252859812191058636308480000000 |
Para N itens é necessário n!(fatorial de n) operações para chegar a um resultado. Então esse é o tempo de execução O(n!) ou o *tempo fatorial*. Esse algoritmo consome muitas operações, exceto para casos envolvendo números pequenos.

Esse é um problema sem solução e muitos acreditam ser impossível melhorá-lo. O melhor que você pode fazer é chegar em uma solução aproximada(Cap 10).

Resumos do Capítulo
- A pesquisa binária é muito mais rápida do que a pesquisa simples;
- O(log n) é mais rápido do que O(n), e O(log n) fica ainda mais rápido conforme conforme os elementos da lista aumentam;
- A rapidez de uma algoritmo não é medida em segundos;
- O tempo de execução de um algoritmo é medido por meio de seu crescimento;
- O tempo de execução de um algoritmo é expresso na notação Big O.


# Cap 2 - Ordenação por seleção
### Como funciona a memória

A memória do computador funciona como uma gaveta que armazena itens e cada gaveta tem o seu o seu endereço, ex: `fe0ffeeb` é o endereço de slot na memória.

Cada vez que quer armazenar um item na memória, você "pede ao computador" um espaço e ele "te da" um endereço no qual você pode armazenar seu item. Se quiser armazenar múltiplos itens, existem duas maneiras para fazer isso: **arrays e listas.**

### Arrays e Listas Encadeadas

Utilizar um array significa que seus dados estarão armazenados continuamente "um ao lado do outro".

Caso precisasse adicionar mais algum dado precisaria mover todo os dados já adicionados para um outro local na memória na qual coubesse todos "um do lado do outro", ou seja adicionar novos dados em um array se torna uma tarefa mais lenta.

Uma das formas de contornar isso seria "reservando os lugares", você reserva um espaço de memória antes de utilizado sem nenhum valor para que quando novos dados entrem eles preencham esses espaços reservados.

  
Desvantagens:

- Você pode não precisar dos espaços extras que reversou; então a memória será desperdiçada. Você não está utilizando a memória, mas ninguém pode usá-la também.

- Você pode precisar adicionar mais dez itens a sua lista de tarefas, então você terá que mover seus itens de qualquer maneira.

  

### Listas Encadeadas

Com as listas encadeadas, seus itens podem estar em qualquer lugar da memória.

Cada item armazena o endereço do próximo item da lista. Um monte de endereços aleatórios de memória estão ligados.


Funciona da seguinte forma, você vai ao primeiro endereço e ele diz "o próximo item pode ser encontrado no endereço 123". Então vai ao endereço 123 e diz "o próximo item pode ser encontrado no endereço 847", e assim por diante. **Adicionar um item a uma lista encadeada é fácil: você o coloca em qualquer lugar na memória e coloca o endereço do item anterior.** Se existe espaço na memória, você terá espaço para a sua lista encadeada.

Se as listas encadeadas são melhores para inserções, para que sevem os arrays?

### Arrays

Suponha que você queria ler o último item de uma **lista encadeada**. Você não pode fazer isso por que não sabe o endereço dele. Em vez disso precisa ir ao item #1 para pegar o endereço do item #2. Então é necessário ir ao item #2 para pegar o endereço do item #3 e assim por diante até conseguir o endereço do último item, isso ocorre pois os elementos estão aleatórios no sistema e um endereço só guarda o valor do anterior e próximo.

Listas encadeadas são ótimas se você quiser ler todos os itens , um de cada vez mas terríveis caso queira pular um desses itens.

Já com os arrays é diferente eles são ótimos para ler se você deseja ler valores aleatórios, pois pode encontrar qualquer elemento instantaneamente em um array.

  

#### Terminologia

A numeração de um array começa no 0 e não no 1

| 10  | 20  | 30  | 40  | 50  | 60  | 70  |
| --- | --- | --- | --- | --- | --- | --- |
| 0   | 1   | 2   | 3   | 4   | 5   | 6   |
  

==A posição de um elemento é chamado de índice==. Portanto, em vez de dizer que o "número 20 está na posição 2" dizemos o "número 20 está no índice 1"

  

Tempo de execução para operadores comuns em arrays e listas

  
|          | Arrays | Listas |
| -------- | ------ | ------ |
| Leitura  | O(1)   | O(n)   |
| Inserção | O(n)   |  O(1)  |

O(n)  = tempo de execução linear
O(1) = tempo de execução constante

  
#### Inserindo algo no meio da lista

Se por acaso precisassemos

```


```

``` cpp

```

``` cpp

```

``` cpp

```

``` cpp

```

``` cpp

```

``` cpp

```

``` cpp

```

``` cpp

```

``` cpp

```