Sintaxe básica de ponteiros
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 10;
    int *ptr;
    ptr = &numero;
    
    cout << "O valor de 'numero' é: " << numero << endl;
    cout << "O endereço de 'numero' é: " << &numero << endl;
    //e necessario passar o ponteiro com * para acessar o valor da variavel apontada
    cout << "O valor apontado por 'ptr' é: " << *ptr << endl;
    cout << "O endereço armazenado em 'ptr' é: " << ptr << endl;

return 0;
}
```


Exemplo de código com ponteiros
> Esse código pega os valores `a` e `b` e por meio da função swap troca os seus valores usando ponteiros na função.
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
- Os valores de swap precisam ser passados com o `&`
	Do ponto de vista do resultado final, os valores de `a` e `b` serão trocados corretamente, independentemente de passarmos os endereços de memória (ponteiros) ou os valores diretamente para a função `swap`.
	Isso ocorre porque, quando passamos os valores `a` e `b` diretamente para a função `swap`, o que acontece é que os valores de `a` e `b` são copiados para os parâmetros `ptrA` e `ptrB` na função. Portanto, dentro da função `swap`, estamos manipulando cópias dos valores originais de `a` e `b`. Mesmo que essas manipulações ocorram em cópias dos valores, elas afetam os valores originais de `a` e `b` porque estamos trabalhando com ponteiros que apontam para esses valores na memória.
	Então, em termos de resultado final, o código funcionará corretamente e os valores de `a` e `b` serão trocados após a chamada da função `swap`, independentemente de como os argumentos são passados para a função. No entanto, em termos de boas práticas de programação e clareza do código, é preferível usar ponteiros como argumentos para a função `swap` quando queremos trocar os valores de duas variáveis.