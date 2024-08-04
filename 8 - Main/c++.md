#inicial 

É uma linguagem de programação criada em 1985. Surgiu para ser uma expansão de C para inserir o paradigma de programação orientada a objetos(POO), seu nome inicial era "C com classes".  Criada por Bjarne Stroustrup, a ideia dele era criar um linguagem com semelhante a com os recursos de C mas com alguns implementos como verificação de tipo ativa, Herança Básica, Argumento de Funcionamento padrão, Classes entre outros. É uma linguagem compilada multi-paradigma e podemos dizer que é Fortemente Tipada e Estática.

Lugares onde C++ é mais utilizado

* Jogos;
* Mercado Financeiro;
* Grandes Aplicações;
	* Navegadores;
	* Softwares Multimídia;
	* Pacotes Office;
* Sistemas Operacionais;
* Micro controladores;

## Hello World

``` cpp
#include <iostream> //standard library

int main() { //main function

    std::cout << "Hello World"; //statement

    return 0;

}
```

- `#include <iostream>`: Essa linha permite usar as funcionalidades da biblioteca de entrada e saída padrão em C++.
    
- `int main() { ... }`: É a função principal do programa. Todo programa em C++ deve ter uma função `main()`, que é o ponto de entrada do programa. Nesse código, ela não recebe nenhum argumento.
    
- `std::cout << "Hello World";`: `std::cout` é o objeto usado para imprimir saída no console. `<<` é o operador de inserção, que coloca "Hello World" na saída padrão (neste caso, o console).
    
- `return 0;`: Termina a função `main()` e retorna 0, indicando que o programa foi concluído com sucesso. Um valor diferente de zero pode indicar que algo deu errado durante a execução.

Após isto basta [[compilar em c++]]

## Tipos de Dados em C++
