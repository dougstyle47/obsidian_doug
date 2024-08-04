algoritmo de busca linear ou busca sequencial é um termo para expressar um tipo de pesquisa em [[vetores]] ou [[listas]] de modo sequencial, elemento por elemento, de modo que a função do tempo em relação ao número de elementos é linear, ou seja cresce proporcionalmente. 

Vantagens: Simplicidade(fácil de entender e implementar); Não requer ordenação; Baixa complexidade de memória.
Desvantagens: Baixa eficiência em listas grandes, Ineficiente em buscas repetidas.

Exemplos de código

- Código em c++ com entrada de dados.
``` cpp
#include <iostream>
#include <vector>

using namespace std;
int main(){

    int n, pos;
    cout << "Tamanho da sequencia:  ";
    cin >> n;
    vector<int>sequencia(n);
    cout << "Digite os numeros da sequencia: \n";
    
    for(int i=0; i < n; i++){
        cin >> sequencia[i];
    }

    cout << "Posicao desejada(comecando em 0): ";
    cin >> pos;

    if(pos >= 0 && pos < n){
        cout << "Valor na posicao " << pos << ":" << sequencia[pos]<< endl;
    } else {
        cout << "Posicao inválida. Deve estar no intervalo [0, " <<n - 1 <<"].\n";
    }

    return 0;
}
```

