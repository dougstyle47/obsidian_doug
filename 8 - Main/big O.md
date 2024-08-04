O big O é um forma de que descreve o comportamento limitante de uma função quando ao argumento tende a um valor específico ou ao infinito, ou seja é o tanto que é custoso para um computador "resolver" um algoritmo em específico.

Esperamos que a medida que aumenta a entrada de dados(n) em um algoritmo o tempo de resolução também aumente, mas existem várias formas de como o tempo de execução aumenta, e o Big O serve para definir como o tempo vai aumentar. 


### O(1) 
Não importa o tanto que o entrada de dados aumente o tempo de complexidade não muda. É o algoritmo mais eficiente.

### O(n)
É o tempo linear, a medida que os dados aumentar o tempo aumenta igualmente, é um algoritmo bom quando o número de dados é pequeno mas quando começa a aumentar o tempo de execução se torna muito grande.

### O(n²)
Normalmente utilizado para interagir com arrays bidimensionais. Normalmente o array é um quadrado(lados iguais)
### O(n.m)
Também utilizado em arrays bidimensionais mas normalmente com valores diferentes de m e n, mas funciona quase da mesma forma do O(n²)

### O(n³)
Array com 3 dimensões normalmente é o maior mas é possível ver O(n^4), irá precisar de mais loops para interagir com cada cada array.

### O(log n)
 Nesse tipo de algoritmo em cada interação você elimina metade dos elementos(como na pesquisa binária) é realmente muito utilizado pois você pode trabalhar com valores bem altos e não aumentar tanto o tamanho do tempo necessário para resolução.

### O(nlogn)
Merge Sort