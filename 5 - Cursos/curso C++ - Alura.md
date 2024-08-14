# Conhecendo a linguagem e a STL

Jogo da Adivinhação
```cpp 
#include <iostream> //i=include=Entrada o=Output=Saida STREAM=fluxo
#include <cstdlib> //para usar a função rand de número aleátorios
#include <ctime> //funcao para usar o time
using namespace std;

int main(){
    cout <<"************************************" << endl;
    cout <<"*Bem vindos ao jogo da adivinhacao!*" << endl;
    cout <<"************************************" << endl <<endl ;
    
    //mensagem para escolher o nivel de dificuldade
    cout << "Escolha o seu nível de dificuldade"<< endl;
    cout << "Facil(F); Medio(M) ou Dificil(D)"<< endl <<endl;
    
    char dificulty; //char por ser um caractere que irá passar
    cin >> dificulty;
    
    int numberAttemps;
    // if para determinar quantas tentativas cada um tem
    if (dificulty == 'F'){
        numberAttemps = 15;
    } else if(dificulty = 'M'){
        numberAttemps = 10;
    } else {
        numberAttemps = 5;
    }

    srand(time(NULL));
    const int SECRET_NUMBER = rand() % 100;

    //const int SECRET_NUMBER = 47;

    bool notHit = true;
    int attempts = 0;
    double points = 1000.0;

    for(attempts = 1; attempts <= numberAttemps; attempts++){
        int shot;
        
        cout << "Tentativa " << attempts <<endl;
        
        cout << "Qual o valor do seu chute?" <<endl;
        cin >> shot;

        //abs = para retornar o valor absoluto ou seja somente valores positivos
        double lostPoints = abs(shot-SECRET_NUMBER)/2.0;
        points = points - lostPoints;

        cout << "O valor do seu chute e: " << shot << endl;

        bool hit = shot == SECRET_NUMBER;
        bool biggerHit = shot > SECRET_NUMBER;

        if(hit){
            cout << "Parabens voce acertou o numero secreto" << endl;
            notHit = false;
            break; // para quebrar o laço de repetição
        } else if(biggerHit){
            cout << "O numero que voce chutou e maior que o numero secreto" << endl <<endl;  
        } else{
            cout << "O numero que voce chutou e menor que o numero secreto" << endl <<endl;
        }
    }
    
    cout << "GAME'S OVER"<< endl;


    if(notHit){
        cout << "Você perdeu! Tente novamente" <<endl;
    } else{
        cout << "Voce acertou o numero secreto em: " << attempts << " tentativas"<< endl;
        cout.precision(2); //para setar quantos números após a virgula nois queremos
        cout << fixed; //para não sair na notação cientifica
        cout << "Sua pontuacao foi de " << points << " pontos" << endl;
    }
}
```



Jogo da forca
```cpp
#include <iostream> //Ela inclui as var tipo string, mas é uma boa prática colocar
#include <string>
#include <map>
#include <vector>
#include <fstream> //Para colocar o ifstream 
#include <ctime>
#include <cstdlib>
using namespace std;

//Está fora do escopo pois é uma variável global
string secretWord = "DOUGLAS"; 
map<char, bool> shoted; //nao entendi
vector<char> missedAttempt;

//Função para verificar se a letra existe ou não na palavra
bool existWord(char shot){
   for(char word : secretWord)
        if(shot == word){
            return true;
        }   
   return false;
}

bool notHit(){
    for(char word : secretWord){
        if(!shoted[word]){
            return true;
        }
    }
    return false;
}

bool notHanger(){
    return missedAttempt.size() < 5;
}

void printHeader(){
     cout << endl;
    cout << "*******************************" <<endl;
    cout << "********JOGO DA FORCA**********" <<endl;
    cout << "*******************************" <<endl;
    cout << endl;
}

void printMistakes(){
    cout <<"Chutes errados: " ;
    for(char word : missedAttempt){
        cout << word << " " ;
    }
    cout << endl;
}

//não entendi essa função
void printWord(){
    for(char word : secretWord){
        if(shoted[word]){
          cout << word << " ";
        }else{
            cout << "_ ";
        }
    }
        cout << endl;
}

void shot(){
    cout << "Seu chute: ";
    char shot;
    cin >> shot;
    shoted [shot] = true; //não entendi

    if(existWord(shot)){
        cout << "Voce acertou, seu chute esta na palavra" << endl;
    }else{
         cout << "Voce errou, seu chute nao esta na palavra" <<endl;
         missedAttempt.push_back(shot);  
    }     
    cout << endl;
}

vector<string> readFile(){
    //input, file, stream
    ifstream file;
    file.open("words.txt");

    //if para se caso o arquivo for mudado de lugar, exibir uma mensagem de erro
    if(file.is_open()){ 
        int numberWords;
        file >> numberWords;

        //cout << "O arquivo possui " << numberWords << " words." <<endl;

        vector<string> fileWords;

        for(int i = 0; i < numberWords; i++){
            string readWord;
            file >> readWord;
            //cout <<" Na linha " << i << " :" << readWord <<endl;
            fileWords.push_back(readWord);
        }
        file.close(); //boa pratica é fechar o arquivo após o uso dele
        return fileWords;
    } else {
        cout << "Não foi possível acessar o banco de palavras." << endl;
        exit(0);
    }
}

//draw = sortear
void drawWord(){
    vector<string> words = readFile();

    srand(time(NULL));
    int drawIndex = rand() % words.size();

    secretWord = words[drawIndex];
}


void saveFile(vector<string> newList){
    ofstream file;
    file.open("words.txt");

    if(file.is_open()){
        file << newList.size() << endl;

        for(string word : newList){
            file << word << endl;
            //cout << "Palavra adicionada com sucesso." << endl;
        }
        file.close();
    }else{
        cout << "Não foi possível acessar o banco de palavras." << endl;
        exit(0);
    }
}

void addWord(){
    cout << "Digite a nova palavra, usando letras maiusculas." << endl;
    string newWord;
    cin >> newWord;

    vector<string> listWords = readFile();
    listWords.push_back(newWord);

    saveFile(listWords);
}


int main(){
    printHeader();

    readFile();
    drawWord();

    while(notHit() && notHanger()){
        printMistakes();
        printWord();
        shot();
    }
    cout << "Fim de jogo" << endl;
    cout << "A palavra secreta era: " << secretWord << endl;
    if(notHit()){
        cout << "Voce perdeu! Tente novamente!" << endl;
    } else {
        cout << "Parabens! Voce acertou a palavra secreta "<< endl;
        cout << "Voce deseja adicionar uma nova palavra ao banco(S/N)" << endl;
        char answer;
        cin >> answer;
        if(answer == 'S'){
            addWord();
        } else {

        }
    }  
}

```


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