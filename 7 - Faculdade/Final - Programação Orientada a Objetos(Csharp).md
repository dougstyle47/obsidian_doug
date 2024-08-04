
No paradigma de programação orientada a objeto, temos dois conceitos bem distintos, a **Classe e o Objeto**.

A classe é a ideia do que seria um objeto, isto é, a descrição de uma pré-classificação existente.
Objeto, é o real, o que existe, que segue as ideias definidas acerca daquele objeto.
	Pessoa
		João, Pedro, Maria
	Carro
		Gol, Fiesta, Uno

Antes de criar um objeto é necessário saber como ele é, isto é classificá-lo, para depois cria-los e manipula-los. 

Todas a classes é iniciada com uma letra maiúscula(padrão adotado)
	Ex: Cliente, Produto, Conta Corrente, Nota Fiscal

```cs
public class Smartphone{
}
```

O objeto por sua vez inicia com letra minúscula
 Ex: arroz, tomate, arrozDoce, TomateSeco

==Obs: Como o lilo não posta nada, irei recorrer aos cursos da alura para aprender c#==
# 1 - Criando sua primeira aplicação

C# é **fortemente tipada** ou seja é sempre necessário declarar o tipo de uma variável

Um "hello world" com variável
```cs
//camelCase
string mensagemDeboasBindas = "Boas vindas ao Screen Sound";
Console.WriteLine(mensagemDeboasBindas);

Console.ReadLine();//Para o console não fechar rápido
```

Mesmas coisa de cima mas com função
```cs
void ExibirMensagemDeBoasVindas()
{
    string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
    Console.WriteLine("***************************");
	Console.WriteLine(mensagemDeboasVindas);
    Console.WriteLine("***************************");
}
    ExibirMensagemDeBoasVindas(); 

```


Usando o ==Verbatim Literal== para adicionar uma mensagem de um site no programa
```cs
        static void Main(string[] args)
        {

         void ExibirMensagemDeBoasVindas()
            {
                string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
                //é necessário o @ para fazer isso(verbatin literal)
                Console.WriteLine(@"
░██████╗░█████╗░██████╗░███████╗███████╗███╗░░██╗  ░██████╗░█████╗░██╗░░░██╗███╗░░██╗██████╗░
██╔════╝██╔══██╗██╔══██╗██╔════╝██╔════╝████╗░██║  ██╔════╝██╔══██╗██║░░░██║████╗░██║██╔══██╗
╚█████╗░██║░░╚═╝██████╔╝█████╗░░█████╗░░██╔██╗██║  ╚█████╗░██║░░██║██║░░░██║██╔██╗██║██║░░██║
░╚═══██╗██║░░██╗██╔══██╗██╔══╝░░██╔══╝░░██║╚████║  ░╚═══██╗██║░░██║██║░░░██║██║╚████║██║░░██║
██████╔╝╚█████╔╝██║░░██║███████╗███████╗██║░╚███║  ██████╔╝╚█████╔╝╚██████╔╝██║░╚███║██████╔╝
╚═════╝░░╚════╝░╚═╝░░╚═╝╚══════╝╚══════╝╚═╝░░╚══╝  ╚═════╝░░╚════╝░░╚═════╝░╚═╝░░╚══╝╚═════╝░
                    ");
                Console.WriteLine(mensagemDeboasVindas);


            }

            ExibirMensagemDeBoasVindas(); 
            Console.ReadLine(); //Para o console não fechar rápido

```

Definindo opções para o programa
```cs
        static void Main(string[] args)
        {

         void ExibirMensagemDeBoasVindas()
            {
                string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
                //é necessário o @ para fazer isso(verbatin literal)
	            Console.WriteLine(//@ "= Logo do Screen Sound ir lá em cima");
               Console.WriteLine(mensagemDeboasVindas);
            }

        void ExibirOpcoesDoMenu()
            {
                Console.WriteLine("\nDigite 1 para registrar uma banda");
                Console.WriteLine("Digite 2 para mostrar todas as bandas");
                Console.WriteLine("Digite 3 para exibir uma banda");
                Console.WriteLine("Digite 4 exibir a media de uma banda");
                Console.WriteLine("Digite -1 para sair");

            }

            ExibirMensagemDeBoasVindas();
            ExibirOpcoesDoMenu();
            Console.ReadLine(); //Para o console não fechar rápido

```

Transformando o valor da opção de string para int e colocando um IF para opção 1
```cs
        static void Main(string[] args)
        {

         void ExibirMensagemDeBoasVindas()
            {
                string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
                //é necessário o @ para fazer isso(verbatin literal)
		        Console.WriteLine(//@ "= Logo do Screen Sound ir lá em cima");
                Console.WriteLine(mensagemDeboasVindas);
            }

        void ExibirOpcoesDoMenu()
            {
                Console.WriteLine("\nDigite 1 para registrar uma banda");
                Console.WriteLine("Digite 2 para mostrar todas as bandas");
                Console.WriteLine("Digite 3 para exibir uma banda");
                Console.WriteLine("Digite 4 exibir a media de uma banda");
                Console.WriteLine("Digite -1 para sair");

                Console.Write("\nDigite a sua opção: ");
                string opcaoEscolhida = Console.ReadLine();

                //para transformar a opção escolhida de string para inteiro
                int opcaoEscolhidaNumerica = int.Parse(opcaoEscolhida);

                if(opcaoEscolhidaNumerica == 1)
                {
                    Console.WriteLine("Você digitou a opção: " + opcaoEscolhida);  

                }

            }


            ExibirMensagemDeBoasVindas();
            ExibirOpcoesDoMenu();
            Console.ReadLine(); //Para o console não fechar rápido

        }


```


Colocando as opções com Switch Case(Código completo até aqui)
```cs

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace PrimeiroProjeto
{
    internal class Program
    {
        static void Main(string[] args)
        {

            void ExibirMensagemDeBoasVindas()
            {
                string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
                //é necessário o @ para fazer isso(verbatin literal)
                Console.WriteLine(@"
░██████╗░█████╗░██████╗░███████╗███████╗███╗░░██╗  ░██████╗░█████╗░██╗░░░██╗███╗░░██╗██████╗░
██╔════╝██╔══██╗██╔══██╗██╔════╝██╔════╝████╗░██║  ██╔════╝██╔══██╗██║░░░██║████╗░██║██╔══██╗
╚█████╗░██║░░╚═╝██████╔╝█████╗░░█████╗░░██╔██╗██║  ╚█████╗░██║░░██║██║░░░██║██╔██╗██║██║░░██║
░╚═══██╗██║░░██╗██╔══██╗██╔══╝░░██╔══╝░░██║╚████║  ░╚═══██╗██║░░██║██║░░░██║██║╚████║██║░░██║
██████╔╝╚█████╔╝██║░░██║███████╗███████╗██║░╚███║  ██████╔╝╚█████╔╝╚██████╔╝██║░╚███║██████╔╝
╚═════╝░░╚════╝░╚═╝░░╚═╝╚══════╝╚══════╝╚═╝░░╚══╝  ╚═════╝░░╚════╝░░╚═════╝░╚═╝░░╚══╝╚═════╝░
                    ");
                Console.WriteLine(mensagemDeboasVindas);
            }

            void ExibirOpcoesDoMenu()
            {
                Console.WriteLine("\nDigite 1 para registrar uma banda");
                Console.WriteLine("Digite 2 para mostrar todas as bandas");
                Console.WriteLine("Digite 3 para exibir uma banda");
                Console.WriteLine("Digite 4 exibir a media de uma banda");
                Console.WriteLine("Digite -1 para sair");

                Console.Write("\nDigite a sua opção: ");
                string opcaoEscolhida = Console.ReadLine();

                //para transformar a opção escolhida de string para inteiro
                int opcaoEscolhidaNumerica = int.Parse(opcaoEscolhida);

                switch (opcaoEscolhidaNumerica)
                {
                    case 1:
                        Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 2:
                        Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 3:
                        Console.WriteLine("Você esoclescolheuheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 4:
                        Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 5:
                        Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    default:
                        Console.WriteLine("Opção inválida");
                        break;
                }
                }


                ExibirMensagemDeBoasVindas();
                ExibirOpcoesDoMenu();


                Console.ReadLine(); //Para o console não fechar rápido

            }
        }
    }
}

```

Opção 1 implementada, criado a lista que irá armazenar o nomes das bandas
```cs
        static void Main(string[] args)
        {
            string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
            //listas das bandas
            List<string> listaDasBandas = new List<string>();

            void ExibirLogo()
            {
                //é necessário o @ para fazer isso(verbatin literal)
                Console.WriteLine(@"");
                Console.WriteLine(mensagemDeboasVindas);
            }

            void ExibirOpcoesDoMenu()
            {
                ExibirLogo();
                Console.WriteLine("\nDigite 1 para registrar uma banda");
                Console.WriteLine("Digite 2 para mostrar todas as bandas");
                Console.WriteLine("Digite 3 para exibir uma banda");
                Console.WriteLine("Digite 4 exibir a media de uma banda");
                Console.WriteLine("Digite -1 para sair");

                Console.Write("\nDigite a sua opção: ");
                string opcaoEscolhida = Console.ReadLine();

                //para transformar a opção escolhida de string para inteiro
                int opcaoEscolhidaNumerica = int.Parse(opcaoEscolhida);

                switch (opcaoEscolhidaNumerica)
                {
                    case 1:RegistarBanda();
                        break;
                    case 2:Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 3: Console.WriteLine("Você esoclescolheuheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 4: Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 5: Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case -1: Console.WriteLine("Vai te embora Carniça");
                        break;
                    default:Console.WriteLine("Opção inválida");
                        break;
                }
            }

            void RegistarBanda()
            {
                Console.Clear();
                Console.WriteLine("Registro de bandas");
                Console.Write("Digite o nome da banda que deseja registrar: ");
                string nomeDaBanda = Console.ReadLine();
                listaDasBandas.Add(nomeDaBanda);
                // Interpolação foi o jeito que foi usado para colocar o nome da banda
                Console.WriteLine($"A banda {nomeDaBanda} foi registrada com sucesso");
                //Thread.Sleep(2000); para haver uma espera, mas não está funcionando
                System.Threading.Thread.Sleep(2000); // funcionou com esse
                Console.Clear();
                ExibirOpcoesDoMenu();
               
            }


            ExibirLogo();
            ExibirOpcoesDoMenu();


            Console.ReadLine(); //Para o console não fechar rápido

        }

```


```cs
	static void Main(string[] args)
        {
            string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
            //listas das bandas
            List<string> listaDasBandas = new List<string> {"Linkin Park" , "Arctic Monkeys" , "A Tribe Call Quest" };

            void ExibirLogo()
            {
                //é necessário o @ para fazer isso(verbatin literal)
                Console.WriteLine(@"");
                Console.WriteLine(mensagemDeboasVindas);
            }

            void ExibirOpcoesDoMenu()
            {
                ExibirLogo();
                Console.WriteLine("\nDigite 1 para registrar uma banda");
                Console.WriteLine("Digite 2 para mostrar todas as bandas");
                Console.WriteLine("Digite 3 para exibir uma banda");
                Console.WriteLine("Digite 4 exibir a media de uma banda");
                Console.WriteLine("Digite -1 para sair");

                Console.Write("\nDigite a sua opção: ");
                string opcaoEscolhida = Console.ReadLine();

                //para transformar a opção escolhida de string para inteiro
                int opcaoEscolhidaNumerica = int.Parse(opcaoEscolhida);

                switch (opcaoEscolhidaNumerica)
                {
                    case 1:RegistarBanda();
                        break;
                    case 2: MostrarBandasRegistradas();
                        break;
                    case 3: Console.WriteLine("Você esoclescolheuheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 4: Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case 5: Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case -1: Console.WriteLine("Vai te embora Carniça");
                        break;
                    default:Console.WriteLine("Opção inválida");
                        break;
                }
            }

            void RegistarBanda()
            {
                Console.Clear();
                Console.WriteLine("********************");
                Console.WriteLine("Registro de bandas");
                Console.WriteLine("********************\n");
                Console.Write("Digite o nome da banda que deseja registrar: ");
                string nomeDaBanda = Console.ReadLine();
                listaDasBandas.Add(nomeDaBanda);
                // Interpolação foi o jeito que foi usado para colocar o nome da banda
                Console.WriteLine($"A banda {nomeDaBanda} foi registrada com sucesso");
                //Thread.Sleep(2000); para haver uma espera, mas não está funcionando
                System.Threading.Thread.Sleep(2000); // funcionou com esse
                Console.Clear();
                ExibirOpcoesDoMenu();
               
            }

            void MostrarBandasRegistradas()
            {
                Console.Clear();
                Console.WriteLine("************************************");
                Console.WriteLine("Exibindo todas as bandas registradas");
                Console.WriteLine("************************************\n");

                for(int i = 0; i < listaDasBandas.Count; i++
                    )
                {
                    Console.WriteLine($"Banda: {listaDasBandas[i]}");
                }
                Console.WriteLine("\nDigite uma tecla para voltar ao menu principal");
                Console.ReadKey();
                Console.Clear();
                ExibirOpcoesDoMenu();

            }


            ExibirLogo();
            ExibirOpcoesDoMenu();


            Console.ReadLine(); //Para o console não fechar rápido

        }
```

Mudando o For em MostrarBandasRegistradas
```cs
    void MostrarBandasRegistradas()
    {
        Console.Clear();
        Console.WriteLine("************************************");
        Console.WriteLine("Exibindo todas as bandas registradas");
        Console.WriteLine("************************************\n");

        //for(int i = 0; i < listaDasBandas.Count; i++
        //    )
        //{
        //    Console.WriteLine($"Banda: {listaDasBandas[i]}");
        //}

        // Para substituir o FOR normal
        foreach (string banda in listaDasBandas)
        {
            Console.WriteLine($"Banda: {banda}");
        }

        Console.WriteLine("\nDigite uma tecla para voltar ao menu principal");
        Console.ReadKey();
        Console.Clear();
        ExibirOpcoesDoMenu();

    }

```

## Código no Final do Curso
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace PrimeiroProjeto
{
    internal class Program
    {
        static void Main(string[] args)
        {
            string mensagemDeboasVindas = "Boas vindas ao Screen Sound";
            //listas das bandas
            //List<string> listaDasBandas = new List<string> { "Linkin Park", "Arctic Monkeys", "A Tribe Call Quest" };
            Dictionary<string, List<int>> bandasRegistradas = new Dictionary<string, List<int>>();
            bandasRegistradas.Add("Linkin Park", new List<int> { 10, 9, 10});
            bandasRegistradas.Add("Arctic Monkeys", new List<int> ());

            void ExibirLogo()
            {
                //é necessário o @ para fazer isso(verbatin literal)
                Console.WriteLine(@"
░██████╗░█████╗░██████╗░███████╗███████╗███╗░░██╗  ░██████╗░█████╗░██╗░░░██╗███╗░░██╗██████╗░
██╔════╝██╔══██╗██╔══██╗██╔════╝██╔════╝████╗░██║  ██╔════╝██╔══██╗██║░░░██║████╗░██║██╔══██╗
╚█████╗░██║░░╚═╝██████╔╝█████╗░░█████╗░░██╔██╗██║  ╚█████╗░██║░░██║██║░░░██║██╔██╗██║██║░░██║
░╚═══██╗██║░░██╗██╔══██╗██╔══╝░░██╔══╝░░██║╚████║  ░╚═══██╗██║░░██║██║░░░██║██║╚████║██║░░██║
██████╔╝╚█████╔╝██║░░██║███████╗███████╗██║░╚███║  ██████╔╝╚█████╔╝╚██████╔╝██║░╚███║██████╔╝
╚═════╝░░╚════╝░╚═╝░░╚═╝╚══════╝╚══════╝╚═╝░░╚══╝  ╚═════╝░░╚════╝░░╚═════╝░╚═╝░░╚══╝╚═════╝░
                    ");
                Console.WriteLine(mensagemDeboasVindas);
            }

            void ExibirOpcoesDoMenu()
            {
                ExibirLogo();
                Console.WriteLine("\nDigite 1 para registrar uma banda");
                Console.WriteLine("Digite 2 para mostrar todas as bandas");
                Console.WriteLine("Digite 3 para avaliar uma banda");
                Console.WriteLine("Digite 4 exibir a média de uma banda");
                Console.WriteLine("Digite -1 para sair");

                Console.Write("\nDigite a sua opção: ");
                string opcaoEscolhida = Console.ReadLine();

                //para transformar a opção escolhida de string para inteiro
                int opcaoEscolhidaNumerica = int.Parse(opcaoEscolhida);

                switch (opcaoEscolhidaNumerica)
                {
                    case 1: RegistarBanda();
                        break;
                    case 2: MostrarBandasRegistradas();
                        break;
                    case 3: AvaliarUmaBanda();
                        break;
                    case 4: ExibirMedia();
                        break;
                    case 5: Console.WriteLine("Você escolheu a opção " + opcaoEscolhidaNumerica);
                        break;
                    case -1: Console.WriteLine("Vai te embora Carniça");
                        break;
                    default: Console.WriteLine("Opção inválida");
                        break;
                }
            }

            void RegistarBanda()
            {
                Console.Clear();
                ExibirTituloDaOpcao("Registros Das Bandas");
                Console.Write("Digite o nome da banda que deseja registrar: ");
                string nomeDaBanda = Console.ReadLine();
                bandasRegistradas.Add(nomeDaBanda, new List<int>());
                // Interpolação foi o jeito que foi usado para colocar o nome da banda
                Console.WriteLine($"A banda {nomeDaBanda} foi registrada com sucesso");
                //Thread.Sleep(2000); para haver uma espera, mas não está funcionando
                System.Threading.Thread.Sleep(2000); // funcionou com esse
                Console.Clear();
                ExibirOpcoesDoMenu();

            }

            void MostrarBandasRegistradas()
            {
                Console.Clear();
                ExibirTituloDaOpcao("Exibindo todas as bandas registradas");

                //for(int i = 0; i < listaDasBandas.Count; i++
                //    )
                //{
                //    Console.WriteLine($"Banda: {listaDasBandas[i]}");
                //}

                // Para substituir o FOR normal
                foreach (string banda in bandasRegistradas.Keys)
                {
                    Console.WriteLine($"Banda: {banda}");
                }

                Console.WriteLine("\nDigite uma tecla para voltar ao menu principal");
                Console.ReadKey();
                Console.Clear();
                ExibirOpcoesDoMenu();
            }

            void AvaliarUmaBanda()
            {
                Console.Clear();
                ExibirTituloDaOpcao("Avaliar Banda");
                Console.Write("Digite o nome da banda que deseja avaliar: ");
                string nomeDaBanda = Console.ReadLine();

                if (bandasRegistradas.ContainsKey(nomeDaBanda))
                {
                    Console.WriteLine($"Qual a nota que a banda {nomeDaBanda} merece: ");
                    int nota = int.Parse(Console.ReadLine());
                    bandasRegistradas[nomeDaBanda].Add(nota);
                    Console.WriteLine($"\nA nota {nota} foi registrada com sucesso para a banda {nomeDaBanda}");
                    System.Threading.Thread.Sleep(2000);
                    Console.Clear();
                    ExibirOpcoesDoMenu();
                }
                else
                {
                    Console.WriteLine($"\nA Banda {nomeDaBanda} não foi adicionada");
                    Console.WriteLine("Digite uma tecla para voltar para o menu");
                    Console.ReadKey();
                    Console.Clear();
                    ExibirOpcoesDoMenu();
                }

            }

            //Para colocar os asteriscos embaixo dos titulos
            void ExibirTituloDaOpcao(string titulo)
            {
                int quantidadeDeLetras = titulo.Length;
                string asteriscos = string.Empty.PadLeft(quantidadeDeLetras, '*');
                Console.WriteLine(asteriscos);
                Console.WriteLine(titulo);
                Console.WriteLine(asteriscos + "\n");

            }

            void ExibirMedia()
            {
                Console.Clear();
                ExibirTituloDaOpcao("Exibir Média da banda");
                Console.Write("Digite o nome da banda que deseja exibir a média: ");
                string nomeDaBanda = Console.ReadLine();
                if (bandasRegistradas.ContainsKey(nomeDaBanda))
                {
                    List<int> notasDaBanda = bandasRegistradas[nomeDaBanda];
                    Console.WriteLine($"\nA média da banda{nomeDaBanda} é {notasDaBanda.Average()}.");
                    Console.WriteLine("Digite uma tecla para voltar para o menu");
                    Console.ReadKey();
                    Console.Clear();
                    ExibirOpcoesDoMenu(); 
                }
                else
                {
                    Console.WriteLine($"\nA Banda {nomeDaBanda} não foi adicionada");
                    Console.WriteLine("Digite uma tecla para voltar para o menu");
                    Console.ReadKey();
                    Console.Clear();
                    ExibirOpcoesDoMenu();
                }                
            }

            ExibirLogo();
            ExibirOpcoesDoMenu();


            Console.ReadLine(); //Para o console não fechar rápido

        }
    }
}

```


# 2 - Aplicando a Orientação a Objeto



```cs

```


```cs

```


```cs

```


```cs

```

