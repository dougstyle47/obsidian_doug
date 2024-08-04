Proposito Geral do C++: Criar todo o tipo de programas: games, sistemas operacionais, navegadores, compiladores, sistemas embarcados.
É uma linguagem compilada: A linguagem escrita no código é convertida em linguagem de máquina, Case-Sensitive.

Source Code > Compilador > Machine Code

``` cpp
#include <iostream>
using namespace std;

int main(){
    cout << "Hello World!\n";
    cout << "My name is Douglas" <<endl;
    cout << "Today is Wendysdan";
}

```

``` cpp
#include <iostream>

using namespace std;
int main(){

    float annualSalary;
    cout << "Please enter your annual salary: ";
    cin >> annualSalary;
    float monthlySalary = annualSalary / 12;
    cout << "Yor monthly salary is: " << monthlySalary <<endl;
    cout << "In 10 years you will earn: " << annualSalary * 10;

    char character = 'a';
    float firstSecondThird;
}
```

Data Type Overflow
``` cpp
int main(){


    int yearOfBirth = 999646466;
    char gender = 'm';
    bool isOlderThan18 = true;
    float averageGrade = 4.5;
    double balance = 45678945856;
  
    cout <<"Size of int is: "<<sizeof(int) <<" bytes\n";
    //-1, -2, -3,...,-214783648
    cout<<"Int min value is "<< INT_MIN <<endl;
    //0, -1, -2, -3,..., 214783647
    cout<<"Int max value is: "<< INT_MAX <<endl;

    //unsigned int serve para apenas "ver" os valores int positivos
    cout<<"Size of unsigned int is: "<<sizeof(unsigned int)<<" bytes\n";
    cout<<"UInt max value is: "<< UINT_MAX << endl;
    cout <<"Size of bool is: "<<sizeof(bool) <<" bytes\n";
    cout <<"Size of char is: "<<sizeof(char) <<" bytes\n";
    cout <<"Size of float is: "<<sizeof(float) <<" bytes\n";
   cout <<"Size of double is: "<<sizeof(double) <<" bytes\n";

}
```

Data type overflow
``` cpp
int main(){

    int intMax = INT_MAX;
    cout << intMax << endl;
    cout << intMax + 1;
}
```

ASCII table
``` cpp
int main(){

//cout<<(int) 'a' <<endl;
cout<<int('a') << endl;
cout<<int('A') << endl;
cout<<char(65) << endl;
}

```

Esse código recebe alguma palavra que você escreveu e mostra como ficaria cada letra em ASCII, mas a variável result soma os ASCII das letras(o que não era o objetivo).
``` cpp
#include <iostream>
#include <limits.h>
using namespace std;

int main(){
    string secretWord;
    int result = 0;

    cout << "Escreva a palavra que voce quer transformar em ASCII: ";
    cin >> secretWord;

    for(int i = 0; i < secretWord.length(); i++){
        char letra = secretWord[i];
        result += int(letra);
        cout << "Letra "<<secretWord[i]<<" = "<< int(letra) << endl;
    }
    
    cout << "A palavra que voce escreveu em ASCII: " << result <<endl;
    return 0;
}

```
1. **Por que usar parênteses após `length()`:**
    - Em C++, `length()` é um método que retorna o tamanho da string, ou seja, o número de caracteres que ela contém. Como `length` é um método (ou função) da classe `std::string`, é necessário chamá-lo com parênteses, mesmo que ele não receba nenhum argumento. Os parênteses indicam que estamos chamando uma função.
2. **Char letra = palavra[i]:**
    - Esta linha está acessando o caractere na posição `i` da string `palavra` e atribuindo esse caractere à variável `letra`. Em C++, strings são tratadas como arrays de caracteres, então podemos acessar caracteres individuais usando colchetes `[i]`, onde `i` é o índice do caractere que queremos acessar. Quando escrevemos `palavra[i]`, estamos acessando o caractere na posição `i` da string `palavra`. O caractere resultante é então armazenado na variável `letra`, que é do tipo `char`, já que cada caractere é do tipo `char`.


Recebe 5 letras e transforma em mensagem ASCII
``` cpp
#include <iostream>
#include <limits.h>
using namespace std;

int main(){


    //voce pode criar as variáveis assim contato que elas sejam iguais
    char c1, c2, c3, c4, c5;
    cout << "Enter 5 letters: ";
    cin >> c1 >> c2 >> c3 >> c4 >> c5;
    cout<<"ASCII messagem: " << int(c1) << " " << int(c2) << " " << int(c3) << " "<< int(c4) << " " << int(c5);

}

```

 Recebe um número e verifica se é par ou impar
``` cpp
#include <iostream>
#include <limits.h>
using namespace std;

int main(){  

    int number;
    cout << "Enter a number: ";
    cin >> number;

    if(number % 2 == 0){
        cout << ("The number is even");
    } else  {
        cout << ("The number is odd");
    }
}
```

Recebe o valor dos 3 lados de um triangulo e devolve qual tipo de triangulo foi informado
``` cpp
#include <iostream>
#include <limits.h>
using namespace std;

int main(){

    float side1, side2, side3;
    cout << "Enter the measure of side 1 of the triangulo: ";
    cin >> side1;
    cout << "Enter the measure of side 2 of the triangulo: ";
    cin >> side2;
    cout << "Enter the measure of side 3 of the triangulo: ";
    cin >> side3;

  

    if(side1 == side2 && side1 == side3){
        cout<< "Equilateral triangle";
    } else if(side1!= side2 && side1 != side2 && side2!=side3){
        cout<<"Escalene triangle";
    }else{
        cout<<"Isosceles triangle";
    }
}
```

Operadores básicos
``` cpp
int main(){

    int a = 5, b = 8;
    cout << (a != b);
    system("cls");

  
    cout << (a == 5 && b == 5)<<endl;
    cout << (a == 5 || b == 5)<<endl;
    int x = 5;
    x +=7;
    //x = x + 7
    cout << x << endl;
}

```

Programa para trocar os valores das variáveis(3 variáveis)
``` cpp
int main(){

    int a = 20;
    int b = 10;

    int temp = a;
    a = b;
    b = temp;
    
    cout << "a = "<< a << " , b = " << b << endl;

}

```

Programa para trocar os valores das variáveis( 2 variáveis)
``` cpp
int main(){
    int a = 20;
    int b = 10;

    a = a + b;
    b = a - b;
    a = a - b;
    cout << "a = "<< a << " , b = " << b << endl;
}

```

IMC
``` cpp
#include <iostream>
#include <limits.h>
using namespace std;
  
int main(){

    //float altura = 1.70;
    //float peso = 62.00;
    //float imc = peso / (altura * altura);

    float weight, height, bmi;
    cout << "Weight(Kg), Height(m): ";
    cin >> weight >> height;
    bmi = weight / (height * height);

    if (bmi < 18.5){
        cout << " Seu imc e:" << bmi << " voce esta com baixo peso" << endl;
    } else if(bmi > 25) {
        cout <<" Seu imc e: " << bmi << " voce esta com sobrepeso"<< endl;
    } else {
        cout << " Seu imc e: " << bmi << " seu peso esta normal"<< endl;
    }
}
```

Jogo da Adivinhação de números
``` cpp
int main(){

    int hostUserName, guestUserNum;
    cout << "Host: ";
    cin >> hostUserName;
    system("cls");
    cout << "Guest: ";
    cin >> guestUserNum;

    //essa linha serve para substituir o código abaixo comentada = ternary operator
    (hostUserName == guestUserNum)? cout << "Correct!":cout<<"Failed!";


    // if(hostUserName == guestUserNum){
    //     cout << "Correct!";
    // } else {
    //     cout << "Failed!";
    // }
}

```

Calculadora
``` cpp
int main(){

    float num1, num2;
    char operation;
    cout<<"**DougystleCode Calculator**"<<endl;
    cin>>num1>>operation>>num2;

    switch (operation){
        case '-':
        cout << num1 << operation<< num2 << " = " << num1 - num2;
        break;

        case '+':
        cout << num1 << operation<< num2 << " = " << num1 + num2;
        break;

        case '*':
        cout << num1 << operation << num2 << " = " << num1 * num2;
        break;

        case '/':
        cout << num1 << operation << num2 << " = " << num1 / num2;
        break;


        case '%':
//1. `(int)num1`: Aqui, `num1` está sendo explicitamente convertido para um tipo `int`. Essa conversão força `num1` a perder sua parte fracionária e ser tratado apenas como um número inteiro. Por exemplo, se `num1` fosse 5.6, essa conversão o transformaria em 5. 
//2. `(int)num2`: Similarmente, `num2` está sendo convertido para um tipo `int`.  
//3. `((int)num1 == num1)`: Esta expressão compara o valor convertido de `num1` (um inteiro) com o valor original de `num1`. Se esses dois valores forem iguais, isso significa que `num1` era originalmente um número inteiro, pois a conversão para `int` não alterou seu valor. Se forem diferentes, isso indica que `num1` não era um número inteiro. 
//4. `((int)num2 == num2)`: Similarmente, esta expressão compara o valor convertido de `num2` com o valor original de `num2`.
            bool isNum1Int, isNum2Int;
            isNum1Int = ((int)num1==num1);//5 == 5.0
            isNum2Int = ((int)num2==num2);

            if(isNum1Int && isNum2Int){
                cout << num1 << operation << num2 <<  " = " << (int)num1 % (int)num2;
            } else {

                cout << "Operacao invalida";
            }
        break;

    default: cout << "Operacao invalida"<< endl;
   }

}

```

Programa que diz quantos dias tem o mês indicado.
``` cpp
int main(){

    int year, month;
    cout<<"Indique o ano e o mes respectivamente"<<endl;
    cin >> year >> month;
    
    switch(month) {
    //Conta para ver se o ano é bissexto 
        case 2:(year % 4 == 0 && year % 100 != 0 || year % 400 == 0 )?
        cout << "29 dias no mes": cout << "28 dias no mes";
        break;
        
        case 4:
        case 6:
        case 9:
        case 11:
        cout << "30 dias no mes";
        break;
        
        case 1:
        case 5:
        case 7:
        case 8:
        case 10:
        case 12:
        cout << "31 dias no mes";
        break;

        default: cout << "Not valid";
    }
}

```

Programa para ver quais números entre 100 e 500 são divisíveis por 3 e 5.
``` cpp
int main(){

    int counter = 100;

    while(counter <= 500){
        if(counter%3 == 0 && counter%5 == 0)
        cout<< counter << " is divisible\n" ;
        counter++;
    }
}
```

Contador de Dígitos de um número.
``` cpp
int main(){
    
    int number;
    cout << "Number: ";
    cin >> number;
    
    if(number == 0){//se o número for zero ele avisa que não pode ser efetuada
        cout << "You have enter 0.\n";
    } else {
        if(number < 0){//se o número de entrada for negativo ele multiplica por -1 para ficar positivo
            number *= -1;
        }
        int counter = 0;
        while(number > 0){ //enquanto o valor for maior que zero o while continua a rodar
            //number = number / 10;
            number /= 10; // vai dividindo por 10 para ir mudando a virgula de local
            counter++;
        }
        cout << "O numero de digitos e: " << counter;
    }
}
```

Programa para fazer um reverse no número indicado pelo usuário.
``` cpp
int main(){

    int number, reverse = 0;
    cout << "Numero: ";
    cin >> number;
    
         //A ideia do codigo é, pegar que restou de uma divisão por 10 do numero de entrada e adicionar
        //na váriavel "reverse" multiplicada por 10 para significar as dezenas, centenas, milhares...
    while(number != 0 ) {
   
        reverse *= 10;
        reverse += number % 10;
        number /= 10;
    }
    cout << "Reverso : " << reverse;
}
```

Programa para "autenticar uma entrada" com um pin(do while)
``` cpp
int main(){
    
    int usersPin = 1234, pin, errorCounter = 0;

    do{
        cout << "Pin: ";
        cin >> pin;
        if(pin != usersPin)
            errorCounter++;

  

    } while (errorCounter<3  && pin!=usersPin);
    if(errorCounter<3){
        cout<<"Loading...";
    }else {
        cout << "Blocked...";
    }
}

```

Programa para calcular fatorial(for)
``` cpp
int main(){

    int number;  
    cout << "number: ";
    cin >> number;

    int factorial = 1;

    for(int i = number ; i > 0; i--){
        factorial = factorial * i;
    }

    //para resolver do 1 até o número
    //for(int i = 1; i <= number; i++){
    //   result = result * i;
    //}
    cout << factorial;

}
```

Programa para Pedir três notas e fazer a média dela
``` cpp
#include <iostream>
#include <limits.h>
using namespace std;

int main(){
    
    int grade, sum = 0;
    
    for(int i = 0; i < 3; i++){

        do{
            cout << "Nota " << i + 1 << ": ";
            cin >> grade;
        }while(grade < 1 || grade > 5 );
        sum += grade;
    }
   
    cout <<  "Soma = " << sum << endl;
    cout << "Media = " << (float)sum / 3.0 << endl;
}

```

Tabuada
``` cpp
int main(){

    for(int i = 1; i <= 10; i++){
        for(int j = 1; j <= 10; j++){
            cout << i << " * " << j << " = "<< i * j << endl;
        }
        cout << endl;
    }
}
```

Fazer um desenho de símbolos(For)
``` cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(){

    int height, width;
    cout << "Height: ";
    cin >> height;
    cout << "width: ";
    cin >> width;
    char symbol;
    cout << "Symbol: ";
    cin >> symbol;

    for (int h = 0; h < height; h++){
        for(int w = 0; w < width; w++){
            cout << setw(3) << symbol;
        }
        cout << endl;
    }
}
```

Desenhando 2 triângulos (For)
``` cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(){
    int length;
    cout << "length: ";
    cin >> length;
    char symbol;
    cout << "Symbol: ";
    cin >> symbol;

    //triangulo crescente
    for(int i = 1; i <= length; i++){
        for(int j = 1; j <= i; j++)
	        cout << setw(2) <<symbol;
	        cout << endl;
    }    

    cout << endl;
    
    //tringulo decrecente
    for(int i = length; i >= 1; i--){
        for(int j = 1; j <= i; j++)
	        cout << setw(2) <<symbol;
	        cout << endl;
    }    
}
```

Introdução a Funções(Funções)
``` cpp
#include <iostream>
using namespace std;

//declaração de função pois ela está lá embaixo e o compilador le o codigo de cima para baixo
void function();

int main(){
    cout<<"Hello from main()\n" << endl;
    function();
}

void function(){
    cout<<"hello from function()" << endl;
}
```

Funções com Paramêtros(Funções)
``` cpp
#include <iostream>
using namespace std;

//definindo um padrão(default) de age caso não passem na chamada da funcao
void introduceMe(string name, string city, int age = 0){
    cout << "My name is: " << name << endl;
    cout << "I am from: " << city << endl;
    if(age!=0){
        cout << "I am: " << age << " years old " << endl;
    }
}

int main(){
   string name, city;
    int age;
    cout << "Name: ";
    cin >> name;
    cout << "City: ";
    cin >> city;
    cout << "Age: ";
    cin >> age;

    introduceMe(name, city, age);
    //introduceMe("Douglas", "Porto Velho", 24);
    //introduceMe("Juliyene", "Joao Pessoa");
}
```

Número Primo(Funções e For)
``` cpp
#include <iostream>
using namespace std;

// funcao para calcular o número primo
bool isPrimeNumber(int number){
    for(int i = 2; i < number; i++){
        if(number % i == 0)
            return false;
        }
    return true;
}

int main(){
    int counter = 0;
    for(int i = 1; i <= 100; i++){
        bool isPrime = isPrimeNumber(i);
        if(isPrime){
            cout <<"The number: " << i <<" e um numero primo\n";
            counter++;
        }
    }
    //contador para saber quantos números primos tem no escopo
    cout << "O numero de numeros primos e: " << counter;
}
```

Function Overloading
``` cpp
#include <iostream>
using namespace std;

int sum(int a, int b);
double sum(double a, double b);
float sum(float a, float b, float c);

int main(){

    cout << sum(15,47) << endl;
    cout << sum(1.5,4.7) << endl;
     cout << sum(1.5,4.7,2.6) << endl;
}

int sum(int a, int b){
    return a + b;
}

double sum(double a, double b){
    return a + b;
}

float sum(float a, float b, float c){
    return a + b + c;
}
```

Sistema Bancário(Funções e Switch Case)
``` cpp
#include <iostream>
using namespace std;

void showMenu(){
    cout <<"***********MENU***************" << endl;
    cout <<"1. Check balance" << endl;
    cout <<"2. Deposit" << endl;
    cout <<"3. Withdraw" << endl;
    cout <<"4. Exit" << endl;
    cout <<"******************************" << endl;
}

int main(){
    //chech balance, deposit, withdraw, show menu
    int option;
    double balance = 500;
    
    do{
        showMenu();
        cout<<"Option: ";
        cin >> option;
        system("cls");

        switch(option){
            case 1:
            cout <<"Balance is: " << balance << " $" <<endl;
            break;

            case 2:
            double deposityAmout;
            cout <<"Deposit amout: ";
            cin >> deposityAmout;
            balance+=deposityAmout;
            break;

            case 3:
            double WithdrawAmout;
            cout <<"Deposit amout: ";
            cin >> WithdrawAmout;
            
            if(WithdrawAmout<=balance){
                balance-=WithdrawAmout;
            }else{
                cout << "Not engough money" << endl;
            }
            break;
        }
    } while (option!=4);
}


```

Função Genérica e Template
``` cpp
#include <iostream>
using namespace std;

//como usar a mesma função com diferentes tipos de dados
template<typename T>
void Swap(T& a, T& b){
    T temp = a;
    a = b;
    b = temp;
}

int main(){
    int a = 5, b = 7;
    cout << a << " - " << b << endl;
    Swap<int>(a,b);
    cout << a << " - " << b << endl;    

    char c = 'c', d = 'd';
    cout << c << " - " << d << endl;
    Swap<char>(c,d);
    cout << c << " - " << d << endl;    
}
```

Programa para calcular a soma entre dois números(Função Recursiva)
``` cpp
#include <iostream>
using namespace std;

int recursive_sum(int m, int n){    //m = 2, n = 4
    if(m == n){ //na funcao de recursao e importante existe um codigo desse tipo que impete de um loop infinito
        return m;  
    }
    return m + recursive_sum(m + 1, n);
}

int main (){
    int m = 1, n = 4;
    cout<<"Sum = "<< recursive_sum(m,n);
    /*for(int i = m; i <= n; i++){
        sum += i;    
    }
    cout << "Sum = " << sum;*/  
}
```

Classe: Será um template ou a planta
Objeto: Um exemplo da classe
	ex: 
		Classe: Fruta  
		Objeto: Maça, Laranja, banana

Classe com Objetos
``` cpp
#include <iostream>
#include <list>
using namespace std;

//criando a classe
class YoutubeChannel{
public: //por default vem privado
    //crindo os atributos
    string Name;
    string OwnerName;
    int SubscribersCount;
    list<string> PublishedVideoTitles;
};

int main(){
	//criando os objetos da classe
    YoutubeChannel ytChannel;
    ytChannel.Name = "dOug";
    ytChannel.OwnerName = "Douglas";
    ytChannel.SubscribersCount = 2000;
    ytChannel.PublishedVideoTitles = {"dOug o mestre", "dOug o mestre2", "dOug o mestre3"};

    cout << "Name: " << ytChannel.Name <<endl;
    cout << "OwnerName: " << ytChannel.OwnerName <<endl;
    cout << "SubscribersCount: " << ytChannel.SubscribersCount <<endl;
    cout << "Videos: " << endl;
    for(string videotitle: ytChannel.PublishedVideoTitles){
        cout << videotitle <<endl;
    }
}
```

Construtores e Métodos de Classes
``` cpp
#include <iostream>
#include <list>
using namespace std;

class YoutubeChannel{
public:
    string Name;
    string OwnerName;
    int SubscribersCount;
    list<string> PublishedVideoTitles;

    //Construtor da classe
    YoutubeChannel(string name, string ownerName){
        Name = name;
        ownerName = ownerName;
        SubscribersCount = 0;
    }

    void GetInfo(){
        cout << "Name: " << Name <<endl;
        cout << "OwnerName: " << OwnerName <<endl;
        cout << "SubscribersCount: " << SubscribersCount <<endl;
        cout << "Videos: " << endl;
        for(string videotitle: PublishedVideoTitles){
            cout << videotitle <<endl;
        }
    }    
};

int main(){
    //criando os objetos, usando um construtor
    YoutubeChannel ytChannel("dOug", "Douglas" );
    ytChannel.PublishedVideoTitles.push_back("c++ for novatos");
    ytChannel.PublishedVideoTitles.push_back("html for novatos");
    ytChannel.PublishedVideoTitles.push_back("c++ OOP");

    YoutubeChannel ytChannel2("Ballarina","Juliane");

    //metodo para os objetos
    ytChannel.GetInfo();
    ytChannel2.GetInfo();
```

Encapsulamento
``` cpp
#include <iostream>
#include <list>
using namespace std;


class YoutubeChannel{
//O conceito de encapsulamento diz que esses atributos devem ser privados,
//e não deveria ser acessados de fora da classe, então eles devem ser acessados
// por metodos que irão mudar os dados dos atributos.

private:
    string Name;
    string OwnerName;
    int SubscribersCount;
    list<string> PublishedVideoTitles;

public:
    //Construtor da classe
    YoutubeChannel(string name, string ownerName){
        Name = name;
        ownerName = ownerName;
        SubscribersCount = 0;
    }
    void GetInfo(){
        cout << "Name: " << Name <<endl;
        cout << "OwnerName: " << OwnerName <<endl;
        cout << "SubscribersCount: " << SubscribersCount <<endl;
        cout << "Videos: " << endl;
        for(string videotitle: PublishedVideoTitles){
            cout << videotitle <<endl;
        }
    }    
    void Subscribe(){
        SubscribersCount++;

    }
    void Unsubscribe(){
        if(SubscribersCount > 0){
            SubscribersCount--;  
        }  
    }
    void PublishVideo(string title){
        PublishedVideoTitles.push_back(title);
    }
};

int main(){
    //criando os objetos, usando um construtor
    YoutubeChannel ytChannel("dOug", "Douglas");
    ytChannel.PublishVideo("c++ for novatos");
    ytChannel.PublishVideo("html for novatos");
    ytChannel.PublishVideo("c++ OOP");


    ytChannel.Unsubscribe();

    //metodo para os objetos
    ytChannel.GetInfo();
}
```
