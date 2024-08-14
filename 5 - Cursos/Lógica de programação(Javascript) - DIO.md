 Um algoritmo é uma sequência finita de ações executáveis que visam obter uma solução para um determinado tipo de problema


# Estrutura de um Software e seu ambiente de Desenvolvimento

Pilares que quase todos os programas possuem.
**Input**: Comandos de interação ou entrada de dados.
**process**: São verificações e ações para realizar o pedido do usuário.
**output**: são comandos de saída para retornar alguma coisa(resultado do processamento).

 **Features** (ou funcionalidades) em um aplicativo são as diferentes tarefas ou funções que o aplicativo pode realizar. Por exemplo, se um aplicativo de câmera tem uma funcionalidade de zoom, essa é uma feature. As features podem variar dependendo do aplicativo e do seu propósito.

Cada feature de um programa terá uma algoritmo diferente.

IDE -  (Integrated Development Environment). Um ambiente de desenvolvimento integrado (IDE) é um software para criar aplicações que combina ferramentas comuns de desenvolvedor em uma única interface de usuário gráfica (GUI).

>Dica: Qualquer curso que fazer não fazer de forma correta certinha, errar as vezes de propósito para aprender a lidar com erros.

# Trabalhando com variáveis

`string` - são variáveis que armazenam texto
`number` - são variáveis que armazenam números
`boolean` - são variáveis lógicas, que armazenam o valor de ligado ou desligado (true/false)

javascript é uma linguagem não tipada não te obriga a declarar o tipo de variável que você vai usar

Declarando variáveis:
``` js
console.log("Digita o nome do seu jogador")

//declara uma variável
let nickname = "Maria mestra do Pikachu"

//concantenando uma mensagem fixa + uma variável
console.log("Bem vinda " + nickname)
console.log(nickname + " entrou no servidor")

```

Declarando constantes:

``` js
const notificacao = "Pokemon Go diz: "

//saida
console.log(notificacao + "tem um novo pokemon na região")
console.log(notificacao + "você foi derrotado por um líder")
```

Ajudando a vovó
``` js
let poteCafe = "café pilão"
let poteAcucar = "Açucar cristal"
let poteBiscoito = "Biscoito Maizena"
const messagemDaVovo = "Na cozinha da vovó hoje tem: "

console.log(messagemDaVovo +  poteCafe + " - " + poteAcucar + " - " + poteBiscoito)

poteCafe = "Café 3 corações"

console.log(messagemDaVovo +  poteCafe + " - " + poteAcucar + " - " + poteBiscoito)
```


Tipos de variáveis
```js
//pokemon
let nomePokemon = "pikachu"
let pokemonSexo = "M";
let nivelPokemon = 20
let pontosDeVidaPokemon = 45
let selecionavel = false
```

# Criando e Manipulando Vetores e Matrizes

Vetores ou Arrays: Guardam dados em linha
``` js
//criando o vetor
let pokemon = ["pikachu" , "charmander" , "Bulbassaur"];

pokemon.shift();//apaga o primeiro valor do vetor
pokemon.pop();//apaga o último valor do vetor

//acessando uma posição no vetor
console.log(pokemon);

// console.log(pokemon[1]); Acessando a posição 2 do vetor(0,1,2)
```
Obs: evitar criar vetores que guardem coisas muito diferentes.


Matrizes: Guardam dados em linhas e colunas

```js
//criando o vetor
let pokemon = ["pikachu" , "Charmander" , "Bulbassauro"];
//criando matrix
let timePokemon = [

  ["Pikachu" , "M" , 1],
  ["Charmander" , "F" , 4],

]

//acessando uma posição na matriz
console.log("O pokemon " + timePokemon[1][0] + " é do sexo " + timePokemon[1][1] + " e está no nível " + timePokemon[1][2])
console.log(pokemon.length) //Retorna quantas posições o vetor tem
```
Resultado: O Pokemon Charmander é do sexo F e está no nível 4 ; 3


# Introdução ao Mundo de Operadores de Programação.

## Operadores Aritméticos
|  |  |  |
| ---- | ---- | ---- |
| Operador | Descrição | Exemplo |
| + | Adição | let result = 5 + 3; |
| - | Subtração | let result = 8 - 2; |
| * | Multiplicação | let result = 4 * 6; |
| / | Divisão | let result = 10 / 2; |
| % | Módulo (resto da divisão) | let result = 10 % 3; |
``` js 
let idade = 30;
console.log("O valor da minha variavél é:" + idade);

// o codigo é "lido" sequencial ou seja o valor de variavel muda
idade = 30 + 6;
console.log(idade);

let primeiroNumero = 2024;
let segundoNumero = 2000;
console.log(primeiroNumero - segundoNumero);

let multiplicador = 4;
let multiplicando = 12;
let produto = multiplicador * multiplicando;
console.log("O valor da operação é: " + produto);

// não precisa do "let", pois a variável ja foi declarada
multiplicador = 8;
// é necessário refazer o calculo
produto = multiplicador * multiplicando;
console.log("O valor da nova operação é: " + produto);

let notaMercado = 50;
let pessoasDividir = 2;
console.log("Operação de divisão é: " + notaMercado/pessoasDividir);

// O resto do calculo
let calculo = 10 % 3;
console.log("Operação de módulo: " + calculo);
```

## Operadores de Incremento e Decremento:
|  |  |  |
| ---- | ---- | ---- |
| Operador | Descrição | Exemplo |
| ++ | Incremento | let counter = 0; counter++; |
| -- | Decremento | let counter = 5; counter--; |
``` js
let contador = 1;

// incremento soma 1
contador++

// decremento subtrai 1
contador--

console.log(contador);

``` 
## Operadores de Atribuição:
|  |  |  |
| ---- | ---- | ---- |
| Operador | Descrição | Exemplo |
| = | Atribuição | let x = 5; |
| += | Adição e atribuição | let num = 10; num += 2; |
| -= | Subtração e atribuição | let num = 10; num -= 3; |
| *= | Multiplicação e atribuição | let num = 5; num *= 4; |
| /= | Divisão e atribuição | let num = 10; num /= 2; |
| %= | Módulo e atribuição | let num = 10; num %= 3; |
``` js
let preco = 10;
preco += 5; // preco = preco + 5
preco -= 5; // preco = preco - 5

console.log(preco);
``` 

## Operadores de comparação:
|  |  |  |
| ---- | ---- | ---- |
| Operador | Descrição | Exemplo |
| == | Igual a | let isEqual = (x == y); |
| != | Diferente de | let isNotEqual = (x != y); |
| > | Maior que | let isGreater = (x > y); |
| < | Menor que | let isLess = (x < y); |
| >= | Maior ou igual a | let isGreaterOrEqual = (x >= y); |
| <= | Menor ou igual a | let isLessOrEqual = (x <= y); |
``` js
let numero = "1";
console.log(numero === "1");

let marca = "Apple";
let resultado = marca !== "Samsung"
console.log(resultado);

// = é abribuição
// == é para comparar valor
// === é para comparar o valor e o formato do conteúdo
// !== é diferente ?
``` 


``` js
let idadeMinima = 18;
let idadeUsuario = 18;
let idadePermitida = idadeUsuario >= idadeMinima;

console.log(idadePermitida);
``` 


#### Operadores lógicos
|  |  |  |
| ---- | ---- | ---- |
| Operador | Descrição | Exemplo |
| && | AND lógico | if (condition1 && condition2) |
| \|\| | OR lógico | if (condition1 \| condition2) |
| ! | NOT lógico | if (!condition) |

``` js
//AND ( && )

let idade = 18;
let vistoVerificado = true;
let resultado = (idade >= 18) && (vistoVerificado === true);

console.log(resultado); //True
``` 

``` js
// OR (||) pelo menos uma das condições precisa ser verdadeira
let tempo = "sol";
let item = "guarda chuva";

let podeSair = (tempo !=="chuva") || (item ==="gurda chuva");
console.log("nosso personagem pode sair? " + podeSair) //True

``` 

``` js
//NO (!) - nega uma afirmação
let tempo = "chuva";
let horario = 8;

let resultado = (tempo ==="chuva") && (horario > 6);
console.log(!resultado); // era para o resultador ser true mas o "!" muda o valo para "false"
``` 

# Estruturas de Controle

If:
``` js
 let possuiOvos = true
	let itensComprados = ""
	if(possuiOvos){
		itensComprados = "leite"
	}
	
	console.log("Item comprado: " + itensComprados);

``` 


Else:
``` js
 let possuiOvos = false
	let itensComprados = ""
	if(possuiOvos){
		itensComprados = "leite"
	} else {
		console.log("Passou na sessão de congelados")
		itensComprados = "Lasanha Congelada"
	}
	
	console.log("Item comprado: " + itensComprados);
	
```

Else if:
``` js
let nivelDeFome = 1

if(nivelDeFome === 3){
    console.log("pouca fome")
} else if(nivelDeFome === 2){
    console.log("muita fome")
}else{
    console.log("Você está morrendo")
}    

```

Switch-Case e Default
``` js
//estrutura de decisão
let fruta = "banana";

switch(fruta){
    case "laranja":
    console.log("suco de laranja")
    break;

	//duas possibilidades para esse case: morango ou banana
    case "banana":
    case "morango":
    console.log("vitamina de banana")
	    //Quando o "case" encontra a condição verdade ele executa todas abaixo dele, por isso foi colocado o break para parar a execução.
    break;
    
    case "maça":
    console.log("suco de maça")
    break;

	//caso todos os cases falhem, o default executa como o else. 
    default:
    console.log("suco generico");

}

```

For
``` js
//for 
for(let contador = 0; contador <= 4; contador++){
    console.log(contador)
    console.log("Aumentando o contador")
}


```

``` js
//for 
let pontosVida = 0;

for(let i = 0; i < 10; i++){
    pontosVida += 1
    console.log("Tomou poção mágica " + i)
}

console.log(pontosVida + " Totais")
```

While
``` js
let contador = 0;

while(contador < 3 ){
    console.log("Olá")
    contador++
}

```

Do While
``` js
let contador = 0;
do {
    console.log("olá")
    contador++
} while(contador < 3)
```

### Desafio 1 - Classificador do Herói
``` js
## Objetivo

Crie uma variável para armazenar o nome e a quantidade de experiência (XP) de um herói, depois utilize uma estrutura de decisão para apresentar alguma das mensagens abaixo:

Se XP for menor do que 1.000 = Ferro  
Se XP for entre 1.001 e 2.000 = Bronze  
Se XP for entre 2.001 e 5.000 = Prata  
Se XP for entre 5.001 e 7.000 = Ouro  
Se XP for entre 7.001 e 8.000 = Platina  
Se XP for entre 8.001 e 9.000 = Ascendente  
Se XP for entre 9.001 e 10.000= Imortal  
Se XP for maior ou igual a 10.001 = Radiante

## Saída

Ao final deve se exibir uma mensagem:  
"O Herói de nome **{nome}** está no nível de **{nivel}**"
```


``` js
let heroName = "Ben 10"; //string precisa estar entre parenteses
let xp = 7500;

let nivel;

    if(xp < 1000 ){
        nivel = "Ferro";
        
    }else if(xp >= 1001 && xp <= 2000){
        nivel = "Bronze";
        
    }else if(xp >= 2001 && xp <= 5000){
        nivel = "Prata";

    }else if(xp >= 5001 && xp <= 6000){
        nivel = "Bronze";  

    }else if(xp >= 6001 && xp <= 7000){
        nivel = "Ouro";

    }else if(xp >= 7001 && xp <= 8000){
        nivel = "Platina";

    }else if(xp >= 8001 && xp <= 9000){
        nivel = "Ascendente";

    }else if(xp >= 9001 && xp <= 10000){
        nivel = "Imortal";

    } else {
        nivel = "Radiante";
    }

console.log("O herói de nome " + heroName + " tem o nível de " + nivel);

```

# Funções

``` js
torrar();

// normalmente funcoes são verbos de fazer algo
function torrar(){
    console.log("torrando pão")
    // função que chama outra função
    injetarPao()
}

function injetarPao(){
    console.log("preparando para injetar o pão")
    console.log("finalizado")
}

```

``` js
torrar("pão de forma", "Doug");
torrar("pão integral", "juliyene");

//passando dois parametros mas eles somente funcionam se tiverem nesse escopo
function torrar(pao, nome){
    console.log("Torrada feita com: " + pao)
    console.log("Pedido feito por: " + nome)
}
```


``` js
torrar("pão de forma", "Doug", 10.47);
torrar("pão integral");

// exemplos de valores genericos caso não passem na hora da chamada
function torrar(pao, nome = "Cliente", valor = 13){
    console.log("Torrada feita com: " + pao)
    console.log("Pedido feito por: " + nome)
    console.log("O valor total é " + valor)
}
```

Interpolação de strings
``` js
createStringConnection("db_products", "Doug", "4715")

function createStringConnection(databaseName,user,pass){
console.log(`Connect:DBCONNECT;user=${user};pass=${pass};initial_database=${databaseName}`)
}

```

Funções com Retornos
``` js
let resultado = soma(5, 10);
console.log("O resultado dessa função é: " + resultado);
//ou console.log("O resultado dessa função é: " + soma(5, 10)); mas não fica tão legivel

function soma(numA,numB){
    let somatorio = numA + numB
    return somatorio
    //ou return numA + numB(colocar a expressão direto no return)
}
```

``` js
let resultado = soma(5, 10);
console.log("O resultado dessa função é: " + resultado);

function soma(numA,numB){
    let somatorio = [3,11,90] //vetor
    return somatorio
    //uma função pode retornar um objeto por vez ou um valor por vez
}
```

``` js
let userName = getFirstName("Douglas Soares Rodrigues Lira");
console.log("Seja bem vindo: "+ userName)

function getFirstName(name){
    let firstName = name.split(" ")[3] //essa função split quebra e colocar cada um dos espaços em um vetor/ o numero entre colchetes é a posição do vetor
        return firstName
}
```

SDK do javascript é o node.


### Desafio 2 - Partidas Rankeadas
``` js
## Objetivo:

Crie uma função que recebe como parâmetro a quantidade de vitórias e derrotas de um jogador, depois disso retorne o resultado para uma variável, o saldo de Rankeadas deve ser feito através do calculo (vitórias - derrotas)

Se vitórias for menor do que 10 = Ferro  
Se vitórias for entre 11 e 20 = Bronze  
Se vitórias for entre 21 e 50 = Prata  
Se vitórias for entre 51 e 80 = Ouro  
Se vitórias for entre 81 e 90 = Diamante  
Se vitórias for entre 91 e 100= Lendário  
Se vitórias for maior ou igual a 101 = Imortal

## Saída

Ao final deve se exibir uma mensagem:  
"O Herói tem de saldo de **{saldoVitorias}** está no nível de **{nivel}**"
```

``` js
let vitorias = 115;
let derrotas = 47;
let rank = rankear(vitorias, derrotas);
console.log(rank);

function rankear (vitorias,derrotas){
    let saldoVitorias = (vitorias - derrotas)
let nivel;
if(saldoVitorias < 10 ){
    nivel = "Ferro";

}else if(saldoVitorias >= 11 && saldoVitorias <= 20){
    nivel = "Bronze";
    
}else if(saldoVitorias >= 21 && saldoVitorias <= 50){
    nivel = "Prata";

}else if(saldoVitorias >= 51 && saldoVitorias <= 80){
    nivel = "Ouro"; 

}else if(saldoVitorias >= 81 && saldoVitorias <= 90){
    nivel = "Diamante";

}else if(saldoVitorias >= 91 && saldoVitorias <= 100){
    nivel = "Lendário";
    
} else {
    nivel = "Imortal";
}

return `O Herói tem um saldo de ${saldoVitorias} vitórias e está no nível ${nivel} `

}

```

Objetos: 

# Objetos
## JSON
é uma estrutura de dados para agrupar de uma maneira mais organizada, normalmente com a finalidade transportar para outro local.

``` js
//JSON -- JavaScript Object Notation;
// Objetos - Chave e valor com o objetivo de transferir dados;

//tudo que estiver dentro dessa chaves é o escopo do JSON
let invoice = {
    name : "Doug",
    age: 24,
    products:{
        0: ["mouse2xwm", 29.90],
        1: ["Teclado Mecanico", 129.99],
        2: ["Monitor", 899.99]
    }
}

generateInvoice(invoice)

function generateInvoice(invoice){
    console.log(`O comprador é: ${invoice.name}`)
    console.log(`A idade é: ${invoice.age}`)
    console.log(`Os produtos são: ${invoice.products}`)
}
```
 O código de cima melhorado.
``` js
//JSON -- JavaScript Object Notation;
// Objetos - Chave e valor com o objetivo de transferir dados;

//tudo que estiver dentro dessa chaves é o escopo do JSON
let invoice = {
    name : "Doug",
    age: 24,
    products:{
        0: ["mouse2xwm", 29.99],
        1: ["Teclado Mecanico", 129.99],
        2: ["Monitor", 899.99],
        3: ["TV 100 polegadas", "100000"]
    }
}

generateInvoice(invoice)

function generateInvoice(invoice){
    console.log(`O comprador é: ${invoice.name}`)
    console.log(`A idade é: ${invoice.age}`)
    console.log("-------------")
    
    //sempre que ver o FOR IN é para percorrer uma lista ou um objeto
    for(const index in invoice.products){
        let [productName, productPrice] = invoice.products[index]
        console.log(` - ${productName}: R$ ${productPrice}`)
    }
}
```

Classes(Métodos e Propriedades)
Classe = Um modelo ou plano para criar objetos que compartilham características e comportamentos semelhantes
Propriedades= Valores associados a um objeto que descrevem suas características
Objeto = Uma instância específica de uma classe que possui propriedades e métodos


``` js
class formaDeBolo{
    constructor(saborDaMassa, saborRecheio){
        this.saborDaMassa = saborDaMassa
        this.saborRecheio = saborRecheio
    }
    
    escrever(){
        console.log(`Um delicioso bolo de ${this.saborDaMassa} com recheio de ${this.saborRecheio}`)
    }
    
    assar(){
        console.log("bolo assando de " + this.saborDaMassa)
    }
}

let boloFesta = new formaDeBolo("Chocolate" , "Nutella");
let boloPremium = new formaDeBolo("Baunilha" , "Coco");

boloFesta.escrever();
boloPremium.escrever();
boloPremium.assar();

```


### Desafio 3 - Poderes do herói 


``` js
**Instruções para entrega**

3️⃣ Escrevendo as classes de um Jogo

**O Que deve ser utilizado**

- Variáveis  
- Operadores  
- Laços de repetição  
- Estruturas de decisões  
- Funções  
- Classes e Objetos

## Objetivo:

Crie uma classe generica que represente um herói de uma aventura e que possua as seguintes propriedades:

- nome  
- idade  
- tipo (ex: guerreiro, mago, monge, ninja )

além disso, deve ter um método chamado atacar que deve atender os seguientes requisitos:

- exibir a mensagem: "o {tipo} atacou usando {ataque}")  
- aonde o {tipo} deve ser concatenando o tipo que está na propriedade da classe  
- e no {ataque} deve seguir uma descrição diferente conforme o tipo, seguindo a tabela abaixo:

se mago -> no ataque exibir (usou magia)  
se guerreiro -> no ataque exibir (usou espada)  
se monge -> no ataque exibir (usou artes marciais)  
se ninja -> no ataque exibir (usou shuriken)

## Saída

Ao final deve se exibir uma mensagem:

- "o {tipo} atacou usando {ataque}"  
  ex: mago atacou usando magia  
  guerreiro atacou usando espada

```

``` js
class heroi{
    constructor(nome, idade, tipo){
    this.nome = nome
    this.idade = idade
    this.tipo = tipo
    }
    
        ataque(){ 
            let ataque;
            
            if(this.tipo === "mago"){
                ataque = "magia"

            } else if(this.tipo === "guerreiro"){
                ataque = "espadas"
         
            } else if(this.tipo === "monge"){
                ataque = "artes maciais"
            
            } else if(this.tipo === "ninja"){
                ataque = "shuriken"
             
            } else {
                ataque = "nao existe essa opção"
            }
        
        console.log(`o ${this.tipo} de idade ${this.idade} atacou usando ${ataque}`);
    }
      
}

let mago = new heroi("ken1" , 23, "mago");
let guerreiro = new heroi("ken2" , 24, "guerreiro");
let monge = new heroi("ken3" , 25, "monge");
let ninja = new heroi("ken4" , 26, "ninja");


mago.ataque();
guerreiro.ataque();
monge.ataque();
ninja.ataque()

```
- Explicação do código acima
1. **Definição da Classe `Heroi`:**
    
    - A classe `Heroi` é definida com um construtor que recebe três parâmetros: `nome`, `idade` e `tipo`. Estes parâmetros são usados para inicializar as propriedades `nome`, `idade` e `tipo` do objeto `Heroi` que será criado posteriormente.
2. **Método `ataque()`:**
    
    - Este método verifica o tipo do herói (`mago`, `guerreiro`, `monge` ou `ninja`) e determina o tipo de ataque correspondente.
    - Se o tipo for `mago`, o ataque é definido como "magia".
    - Se o tipo for `guerreiro`, o ataque é definido como "espadas".
    - Se o tipo for `monge`, o ataque é definido como "artes marciais".
    - Se o tipo for `ninja`, o ataque é definido como "shuriken".
    - Se o tipo não corresponder a nenhum dos tipos conhecidos, uma mensagem indicando "não existe essa opção" é exibida.
3. **Instanciando objetos `Heroi`:**
    
    - São criados quatro objetos `Heroi` com diferentes características (`mago`, `guerreiro`, `monge` e `ninja`), utilizando o construtor da classe `Heroi` com valores específicos para `nome`, `idade` e `tipo`.
4. **Chamando o método `ataque()`:**
    
    - O método `ataque()` é chamado para cada um dos objetos `Heroi` criados anteriormente (`mago`, `guerreiro`, `monge` e `ninja`).
    - Cada chamada ao método `ataque()` imprime uma mensagem no console indicando o tipo do herói, sua idade e o tipo de ataque que ele realizou.

Essencialmente, este código representa uma implementação simples de uma classe `Heroi` em JavaScript, que possui a capacidade de realizar ataques diferentes com base no tipo de herói.



- O que é um método?
No contexto da programação, um método é uma função associada a um objeto específico ou a uma classe. Em JavaScript, os métodos são definidos dentro de objetos ou classes e podem ser chamados para realizar operações específicas relacionadas a esses objetos ou classes.

No código que você forneceu, o método `ataque()` é um método da classe `Heroi`. Ele é responsável por determinar o tipo de ataque que um herói específico pode realizar, com base no tipo de herói definido ao criar uma instância da classe `Heroi`.

Dentro do método `ataque()`, são feitas comparações para verificar o tipo de herói (`mago`, `guerreiro`, `monge` ou `ninja`) e, com base nesse tipo, é determinado o tipo de ataque correspondente. O método então imprime uma mensagem no console indicando o tipo do herói, sua idade e o tipo de ataque que ele realizou.

Em resumo, o método `ataque()` neste código é responsável por determinar e exibir o tipo de ataque de um herói específico.



Desafio do bootcamp - Gerenciamento de Itens Mágicos
``` js
//Desafios JavaScript na DIO têm funções "gets" e "print" acessíveis globalmente:
//- "gets" : lê UMA linha com dado(s) de entrada (inputs) do usuário;
//- "print": imprime um texto de saída (output), pulando linha.

// Definição da classe ItemMagico
class ItemMagico {
//TODO: Crie adequadamente um construtor que receba todos os atributos referente ao item mágico:
  constructor(tipo, dano, resistencia) {
    this.tipo = tipo  
    this.dano = dano  
    this.resistencia = resistencia

  }

  calcularDano() {
    return this.tipo === 'arma' ? this.dano * 2 : this.dano;
  }
}

// Solicita ao usuário para digitar o tipo do item mágico, o dano no item e a resistência do item
const tipoItem = gets();
const danoItem = parseInt(gets());
const resistenciaItem = parseInt(gets());

//TODO: Crie o de um objeto ItemMagico personalizado com base no tipo escolhido
const itemPersonalizado = new ItemMagico(tipoItem, danoItem, resistenciaItem);

// TODO: Imprima os atributos do item personalizado
print("Tipo: " + tipoItem );
print("Dano: " + danoItem );
print("Resistencia: " + itemPersonalizado.resistencia);

// Calcula e imprime o dano causado pelo item personalizado em um combate simulado
const danoTotal = itemPersonalizado.calcularDano();
print("Dano em combate: " + danoTotal);
```

``` js

```