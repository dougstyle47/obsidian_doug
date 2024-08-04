Um objeto é definido pelas suas características, pelo seu estado, pelo seu comportamento e identidade.

Variáveis dentro do objeto é chamado de atributo.

INT no CPF não dá pois "estoura"  os 32 bits considerando o número positivo e negativo é um valor menor que o número total que um CPF possa ter (caso seja 999.999.999-99), uma forma de "burlar" isso seria utilizar o UINT que desconsidera os valores negativos.


```c#
using System;

// Classe objeto = new Classe();`  
Aluno aluno1 = new Aluno(); 
// Classe objeto = new();  
Aluno aluno2 = new();

//var objeto = new Classe();
var aluno = new Aluno();
aluno.nome = "Douglas";
aluno.sobrenome = "Lira";
aluno.cpf = "111.111.111-11";
aluno.telefone = "(69) 992331895";
aluno.dataNascimento = new DateTime(1999,10,14);

Console.WriteLine(aluno.nome);
Console.WriteLine(aluno.sobrenome);
Console.WriteLine(aluno.cpf);
Console.WriteLine(aluno.dataNascimento);

// definir pelo menos 4 características de aluno
public class Aluno {
	
	public string nomecompleto => nome + " " + sobrenome;
	public string nome;
	public string sobrenome;
	public string cpf;
	public string telefone;
	public DateTime dataNascimento;
	
	public int idade => (int)((DateTime.Now - dataNascimento).TotalDays / 365);
}

//definir a classe Disciplina, onde ela tem pleo menos nome, curso, carga horária
// e créditos. Para saber quantos créditos uma disciplina tem, basta usar essa //equivalência: 40h igual a 2 créditos

```


```c#
Console.WriteLine("Hello \"World\"!");

Console.WriteLine("Generating invoices for customer \"Contoso Corp\" ...\n");
Console.WriteLine("Invoice: 1021\t\tComplete!");
Console.WriteLine("Invoice: 1022\t\tComplete!");
Console.WriteLine("\nOutput Directory:\t");Console.WriteLine("Generating invoices for customer \"Contoso Corp\" ...\n");
Console.WriteLine("Invoice: 1021\t\tComplete!");
Console.WriteLine("Invoice: 1022\t\tComplete!");

Console.WriteLine("Generating invoices for customer \"Contoso Corp\" ...\n");
Console.WriteLine("Invoice: 1021\t\tComplete!");
Console.WriteLine("Invoice: 1022\t\tComplete!");
Console.WriteLine("\nOutput Directory:\t");
Console.Write(@"c:\invoices");

// To generate Japanese invoices:
// Nihon no seikyū-sho o seisei suru ni wa:
Console.Write("\n\n\u65e5\u672c\u306e\u8acb\u6c42\u66f8\u3092\u751f\u6210\u3059\u308b\u306b\u306f\uff1a\n\t");
// User command to run an application
Console.WriteLine(@"c:\invoices\app.exe -j");
```

```c#
int version = 11;
string updateText = "Update to Windows";
string message = $"{updateText} {version}";
Console.WriteLine(message);

string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");


```

```c#
int version = 11;
string updateText = "Update to Windows";
string message = $"{updateText} {version}";

Console.WriteLine(message);

string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");

string projectName = "ACME";

string russianMessage = "\u041f\u043e\u0441\u043c\u043e\u0442\u0440\u0435\u0442\u044c \u0440\u0443\u0441\u0441\u043a\u0438\u0439 \u0432\u044b\u0432\u043e\u0434";

```

```c#
int currentAssignments = 5;

int sophia1 = 93;
int sophia2 = 87;
int sophia3 = 98;
int sophia4 = 95;
int sophia5 = 100;

int nicolas1 = 80;
int nicolas2 = 83;
int nicolas3 = 82;
int nicolas4 = 88;
int nicolas5 = 85;
  
int zahirah1 = 84;
int zahirah2 = 96;
int zahirah3 = 73;
int zahirah4 = 85;
int zahirah5 = 79;

int jeong1 = 90;
int jeong2 = 92;
int jeong3 = 98;
int jeong4 = 100;
int jeong5 = 97;

int sophiaSum = (sophia1 + sophia2 + sophia3 + sophia4 + sophia5);
int nicolasSum = (nicolas1 + nicolas2 + nicolas3 + nicolas4 + nicolas5);
int zahirahSum = (zahirah1 + zahirah2 + zahirah3 + zahirah4 + zahirah5);
int jeongSum = (jeong1 + jeong2 + jeong3 + jeong4 + jeong5);

decimal sophiaScore = (decimal) sophiaSum / currentAssignments;
decimal nicolasScore = (decimal) nicolasSum / currentAssignments;
decimal zahirahScore = (decimal) zahirahSum / currentAssignments;
decimal jeongScore = (decimal) jeongSum / currentAssignments;

Console.WriteLine("Student\t\tGrade\n");
Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA");
Console.WriteLine("Nicolas:\t" + nicolasScore + "\tB");
Console.WriteLine("Zahirah:\t" + zahirahScore + "\tB");
Console.WriteLine("Jeong:\t\t" + jeongScore + "\tA");
```

```c#

```

# 20/03/2024
Sub-Programas(apenas na programação estruturada)
	 - Funções(executa e retorna) 
	 - Procedimentos(executa)

Métodos: representam as ações de um objeto

```c#
using System;

Produto produto = new();

produto.descricao = "TV LG 4K";  
produto.quantidade = 8;  
produto.valor = 1899.99;

produto.comprarMuitos(5);  
produto.venderMuitos(3);  
Console.WriteLine(produto);

public class Produto {  
    // atributos ou variáveis membro ou características  
    public string descricao;  
    public int quantidade;  
    public double valor;  
      
    // sintaxe:  
    // visibilidade tipo nomeDoMetodo()   
    public void comprar() {  
        quantidade++; // pós incremento  
    }  
      
    public void comprarMuitos(int qtdAComprar) {  
        // quantidade = quantidade + qtdAComprar;  
        quantidade += qtdAComprar;  
    }  
      
    public void vender() {  
        quantidade--;  
    }  
      
    public void venderMuitos(int qtdAVender) { 
        // quantidade = quantidade - qtdAVender;
        quantidade -= qtdAVender; 
    }  
      
    public override string ToString() {
        return $"Produto: {descricao} - Valor: {valor} - Quantidade: {quantidade}";  
    } 
}

```


# 27/03/2024
Métodos são parecidos com funções

Programação estruturada
	Função: Retorna valor
	Procedimento: Retorna valor
POO
	Métodos apenas.
``` c#
using System;

//instaciar um objeto = criar um objeto
Produto produto = new();

//caracteristicas do objeto produto
produto.descricao = "TV LG 4K";  
produto.quantidade = 8;  
produto.valor = 1899.99;

//comportamentos do objeto produto
produto.comprarMuitos(5);  
produto.venderMuitos(3);  
Console.WriteLine(produto);

public class Produto {  
    // atributos ou variáveis membro ou características  
    public string descricao;  
    public int quantidade;  
    public double valor;  
      
    // sintaxe:  
    // visibilidade tipo nomeDoMetodo()   
    public void comprar() {  
        quantidade++; // pós incremento  
    }  
      
    public void comprarMuitos(int qtdAComprar) {  
        // quantidade = quantidade + qtdAComprar;  
        quantidade += qtdAComprar;  
    }  
      
    public void vender() {  
        quantidade--;  
    }  
      
    public void venderMuitos(int qtdAVender) { 
        // quantidade = quantidade - qtdAVender;
        quantidade -= qtdAVender; 
    }  
      
    public override string ToString() {
        return $"Produto: {descricao} - Valor: {valor} - Quantidade: {quantidade}";  
    } 
}

```


# (10/04/2024) - Revisão para prova

```c#
//1 - Definir a classe Disciplina(vazio);
//2 - Instanciar a classe disciplia(criar o objeto);
//3 - Criar os atributos Nome, CargaHoraria, Professor, Curso(variaveis membro, são normalmente privados, comeca com letra minuscula)
//4 - Criar um construtor onde o nome a carga horaria sejam inicializadas(ajustar a instanciação)
//5 - Criar os getters de nome e CH, já que eles serão caracteristicas somente leitura
//6 - Criar os getters e setters das demais características
//7 - Sobrescrever o método ToString() para mostrar o estado atual do objeto(POO, 80H, SIstemas de Informação, Prof. Lilo)
//8 - Testar a classe
//9 - Criar um campo calculado(baseado em outros campos), que mostra quantos créditos tem a disciplina,(20h <=> 1 crédito)

using System;
//2 - Instanciando a classe
var disciplina = new Disciplina("POO", 80);
//8 - Testando a classe
disciplina.Professor = "Lilo";
disciplina.Curso = "Sistemas";


var disciplina2 = new Disciplina("Logica", 120);
//8
disciplina2.Professor = "Askar";
disciplina2.Curso = "Engenharia";

Console.WriteLine(disciplina);
Console.WriteLine(disciplina2);


//1 - Definindo a Classe
public class Disciplina{

    //3 - Atributos
    private string nome;
    private int cargaHoraria;
    private string professor;
    private string curso;
    
    // 5 - Propriedades
    public string Nome{
        get {return nome;}
    }
    
    public int CargaHoraria{
        get{return cargaHoraria;}
    }
    
    //9 -Criar um campo calculado
    public int Creditos => cargaHoraria/20;
    
    //6 - Getters e Setters
    public string Professor{
        get { return professor;}
        set { professor = value;}
    }
    
    public string Curso{
        get {return curso;}
        set { curso = value;}
    }
    
    //4 - Construtores
    public Disciplina(string nome, int cargaHoraria){
        this.nome = nome;
        this.cargaHoraria = cargaHoraria;
        //é preciso colocar o this. para especificar que o nome(desse escopo) vai receber o "nome" da private class
    }
    
    // 7 - Métodos
    public override string ToString() {
        return $"{Nome}, {cargaHoraria}, {Creditos} creditos, {curso},  Prof. {professor}";
    }
    
}

```

```c#

```

```c#

```

```c#

```
