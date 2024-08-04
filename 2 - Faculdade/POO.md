# Atividade Avaliativa
```cs
public class A {
  private int x;
  public int y() {}
}

public class B {
  private int x;
  private int y;
  public int Y {
    get { return y; }
    set { y = value; }
  }
  public int z { get; set; }
}

public class C {
public int z() {}
}
```
## **Pergunta 1** (1 ponto)
Os comandos Get e Set do elemento Y da classe B serve para manipular o atributo y

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: Os comandos `get` e `set` da propriedade `Y` da classe B servem para acessar e modificar o atributo `y`.
## **Pergunta 2** (1 ponto)
A classe A não tem construtor.

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: A classe A não tem um construtor explicitamente definido, mas possui um construtor padrão implícito fornecido pelo compilador.
## **Pergunta 3** (1 ponto)

É possível a partir da classe B acessar o elemento x de A?

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: Não é possível acessar diretamente o elemento `x` da classe A a partir da classe B, pois `x` é um campo privado.
## **Pergunta 4** (1 ponto)

Na classe A temos 1 atributo e 1 método

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: Na classe A, há 1 atributo (`x`) e 1 método (`y()`).
## **Pergunta 5** (1 ponto)
Na classe A temos 1 atributo e 1 propriedade?

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: Na classe A, há 1 atributo (`x`) e nenhum propriedade.
## **Pergunta 6** (1 ponto)

A partir da classe C, é possível acessar o elemento y da classe A.

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: Não é possível acessar diretamente o elemento `y` da classe A a partir da classe C, pois `y` é um campo privado.
## **Pergunta 7** (1 ponto)
Todos os atributos da classe A são privados.

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: Todos os atributos da classe A (`x`) são privados.
## **Pergunta 8** (1 ponto)
A classe C todos seus elementos são públicos?

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
**Verdadeiro**: Todos os elementos da classe C (`z()`) são públicos
## **Pergunta 9** (1 ponto)
Não existem parâmetros em todos os métodos da classe A, B e C.

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: Não existem parâmetros em nenhum dos métodos das classes A, B e C.
## **Pergunta 10** (1 ponto)
O elemento z na classe B é um método?

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: O elemento `z` na classe B é uma propriedade, não um método.
## **Pergunta 11** (1 ponto)
Todas as propriedades da classe B são públicos.

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: Todas as propriedades da classe B são públicas.
## **Pergunta 12** (1 ponto)
A classe C tem 1 método e 1 construtor?

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: A classe C tem apenas um método, não um construtor explícito.
## **Pergunta 13** (1 ponto)
Na classe B temos duas propriedades com métodos Get e Set definidos.

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: Na classe B, há duas propriedades (`Y` e `z`) com métodos `get` e `set` definidos.
## **Pergunta 14** (1 ponto)

A classe B tem 2 variáveis membros e 2 propriedades

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: A classe B possui 2 variáveis membros (`x` e `y`) e 2 propriedades (`Y` e `z`).
## **Pergunta 15** (1 ponto)
A classe B tem 3 atributos e 1 método

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: A classe B tem 2 variáveis membros (`x` e `y`) e 2 propriedades (`Y` e `z`), totalizando 4 elementos.
## **Pergunta 16** (1 ponto)
Pela aderência às boas práticas de desenvolvimento em C#, o elemento z deveria iniciar com letra maiúscula.

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: De acordo com as convenções de nomenclatura em C#, o nome do elemento `z` na classe B deveria começar com letra maiúscula para seguir o padrão Pascal Case.
## **Pergunta 17** (1 ponto)
A classe B pode acessar todos os elementos de C.

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Falso**: A classe B não pode acessar diretamente os elementos da classe C, pois eles não são acessíveis devido à sua visibilidade privada.
## **Pergunta 18** (1 ponto)
Na classe A o método declarado é um construtor

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: Na classe A, o método declarado não é um construtor. É um método comum chamado `y()`.
## **Pergunta 19** (1 ponto)
Foram declarados 3 classes?

|     |            |
| --- | ---------- |
| X   | Verdadeiro |
|     | Falso      |
1. **Verdadeiro**: Foram declaradas 3 classes: A, B e C.
## **Pergunta 20** (1 ponto)
Somente 2 classes tem construtores

|     |            |
| --- | ---------- |
|     | Verdadeiro |
| X   | Falso      |
1. **Falso**: Somente a classe A possui um construtor implícito fornecido pelo compilador. As outras classes não têm construtores explicitamente definidos.
#  respostas corretas 18/20


# Atividade Avaliativa 2
| Instruções                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| // criar uma classe de conta corrente onde: <br>// tem agencia, número, saldo,  <br>// saldo para saque e data de abertura  <br>// a agencia e o número só pode ser definido na criação da conta  <br>// e não pode mais ser alterado  <br>// o saldo só pode ser manipulado pelas operações   <br>// de depósito e saque  <br>// a conta pode ser bronze, prata ou ouro de acordo   <br>// com o tempo de relacionamento:  <br>// . até 5 anos: bronze com limite de 1 mil reais  <br>// . até 10 anos: prata com limite de 10 mil reais  <br>// . acima de 10 anos: ouro com limite de 50 mil reais<br><br>// faça uma interface para permitir interagir com a conta<br><br>// -----------------------------------  <br>//   [1] - Criar conta  <br>//   [2] - Mostrar saldo  <br>//   [3] - Sacar  <br>//   [4] - Depositar  <br>// ----------------------------------- |

```cs
using System;

// Enum para os tipos de conta
public enum TipoConta
{
    Bronze,
    Prata,
    Ouro
}

// Classe para representar a conta corrente
public class ContaCorrente
{
    // Propriedades da conta corrente
    public string Agencia { get; }
    public string Numero { get; }
    public double Saldo { get; private set; }
    public double LimiteSaque { get; private set; }
    public DateTime DataAbertura { get; }

    // Construtor para inicializar a conta corrente
    public ContaCorrente(string agencia, string numero, double saldoInicial, DateTime dataAbertura)
    {
        Agencia = agencia;
        Numero = numero;
        Saldo = saldoInicial;
        DataAbertura = dataAbertura;
        DefinirLimiteSaque();
    }

    // Método privado para definir o limite de saque com base no tempo de relacionamento
    private void DefinirLimiteSaque()
    {
        TimeSpan tempoRelacionamento = DateTime.Now - DataAbertura;
        if (tempoRelacionamento.TotalDays <= 5 * 365)
        {
            LimiteSaque = 1000;
        }
        else if (tempoRelacionamento.TotalDays <= 10 * 365)
        {
            LimiteSaque = 10000;
        }
        else
        {
            LimiteSaque = 50000;
        }
    }

    // Método para realizar um depósito na conta
    public void Depositar(double valor)
    {
        if (valor <= 0)
        {
            Console.WriteLine("O valor do depósito deve ser maior que zero.");
            return;
        }
        Saldo += valor;
        Console.WriteLine($"Depósito de R${valor} realizado com sucesso. Novo saldo: R${Saldo}");
    }

    // Método para realizar um saque na conta
    public void Sacar(double valor)
    {
        if (valor <= 0)
        {
            Console.WriteLine("O valor do saque deve ser maior que zero.");
            return;
        }
        if (valor > Saldo + LimiteSaque)
        {
            Console.WriteLine("Saldo insuficiente para realizar o saque.");
            return;
        }
        Saldo -= valor;
        Console.WriteLine($"Saque de R${valor} realizado com sucesso. Novo saldo: R${Saldo}");
    }

    // Método para mostrar o saldo da conta
    public void MostrarSaldo()
    {
        Console.WriteLine($"Saldo da conta: R${Saldo}");
    }
}

// Interface para interagir com a conta corrente
public interface IContaCorrenteInteracao
{
    void CriarConta();
    void MostrarSaldo();
    void Sacar();
    void Depositar();
}

// Implementação da interface
public class InteracaoContaCorrente : IContaCorrenteInteracao
{
    private ContaCorrente conta;

    public InteracaoContaCorrente()
    {
        conta = null;
    }

    public void CriarConta()
    {
        Console.Write("Digite a agência da conta: ");
        string agencia = Console.ReadLine();
        Console.Write("Digite o número da conta: ");
        string numero = Console.ReadLine();
        Console.Write("Digite o saldo inicial: ");
        double saldoInicial = Convert.ToDouble(Console.ReadLine());
        DateTime dataAbertura = DateTime.Now; // Data de abertura será a data atual
        conta = new ContaCorrente(agencia, numero, saldoInicial, dataAbertura);
        Console.WriteLine("Conta criada com sucesso!");
    }

    public void MostrarSaldo()
    {
        if (conta == null)
        {
            Console.WriteLine("Conta não foi criada ainda.");
            return;
        }
        conta.MostrarSaldo();
    }

    public void Sacar()
    {
        if (conta == null)
        {
            Console.WriteLine("Conta não foi criada ainda.");
            return;
        }
        Console.Write("Digite o valor a ser sacado: ");
        double valor = Convert.ToDouble(Console.ReadLine());
        conta.Sacar(valor);
    }

    public void Depositar()
    {
        if (conta == null)
        {
            Console.WriteLine("Conta não foi criada ainda.");
            return;
        }
        Console.Write("Digite o valor a ser depositado: ");
        double valor = Convert.ToDouble(Console.ReadLine());
        conta.Depositar(valor);
    }
}

// Classe principal para testar a interação com a conta corrente
class Program
{
    static void Main(string[] args)
    {
        InteracaoContaCorrente interacaoConta = new InteracaoContaCorrente();

        while (true)
        {
            Console.WriteLine("[1] - Criar conta");
            Console.WriteLine("[2] - Mostrar saldo");
            Console.WriteLine("[3] - Sacar");
            Console.WriteLine("[4] - Depositar");
            Console.WriteLine("[5] - Sair");

            int opcao = Convert.ToInt32(Console.ReadLine());

            switch (opcao)
            {
                case 1:
                    interacaoConta.CriarConta();
                    break;
                case 2:
                    interacaoConta.MostrarSaldo();
                    break;
                case 3:
                    interacaoConta.Sacar();
                    break;
                case 4:
                    interacaoConta.Depositar();
                    break;
                case 5:
                    Console.WriteLine("Saindo...");
                    return;
                default:
                    Console.WriteLine("Opção inválida. Tente novamente.");
                    break;
            }
        }
    }
}
```

```cs

```

```cs

```
