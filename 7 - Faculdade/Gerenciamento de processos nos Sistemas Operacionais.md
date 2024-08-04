Tópicos para abordar
- Fundamentos do Gerenciamento de Processos
- Escalonamento de Processos
- Sincronização e Comunicação entre Processos

- Gerenciamento de Memória
- Controle de Processos e Recursos
- Estudos de Caso e Aplicações Práticas
- Desafios e Tendências Futuras

## Introdução

Um sistema de computação moderno conta inúmeros componentes de hardware em sua composição assim como dispositivos de entrada/saída de dados. Ou seja um sistema complexo que por sua vez, torna ainda mais complexo a atividade de escrever programas que controlem todos esses dispositivos e os utilizem corretamente e que sejam otimizados. Há muito tempo surgiu a necessidade de separar os programadores da complexidade do hardware, buscando trazer mais abstração na hora da programação por meio do alto nível. A maneira que evoluiu gradualmente foi colocar uma camada de software sobre o hardware básico, para gerenciar todas as partes do sistema e apresentar ao usuário uma interface, ou máquina virtual, mais fácil de entender e programar. Essa camada de software é o sistema operacional(Tanenbaum, 2018)

O Sistema Operacional tem como função atuar como gerenciador de recursos presentes no sistema computacional, como tempo de CPU, espaço de memória, espaço de armazenamento em arquivo, dispositivo de I/O. Ao lidar com solicitações de recursos e possivelmente conflitantes, o sistema operacional precisa decidir como alocá-los a programas e usuários específicos de modo a poder operar o sistema de computação de maneira eficiente e justa.

## Fundamentos do gerenciamento de processos
Os primeiros computadores permitiram que apenas um programa fosse executado de cada vez. Esse programa tinha controle sobre o sistema e acesso a todos os seus recursos. Por outro lado, os sistemas de computação atuais permitem que vários programas sejam carregados da memória e executados concorrentemente. Essa evolução demandou controle mais firme e maior compartimentalização dos diversos programas; e essas necessidades resultaram na noção de **processo**, que é uma programa em execução.

Um processo é mais do que um código do programa, mas também é conhecido como seção de texto. Ele também inclui a atividade corrente, conforme representada pelo valor do contador do programa e o conteúdo dos registradores do processador. Geralmente um processo também inclui a pilha do processo que contém dados temporários(como parâmetros de funções, endereços de retorno e variáveis locais), e uma seção de dados, que contém variáveis globais.

Embora dois processos possam estar associados ao mesmo programa, ainda assim eles são considerados duas sequências de execução separadas. O modelo de processo descrito até agora sugere que um programa é que executa apenas uma **tread**, ou seja quando um processo está executado um programa de processamento de texto por exemplo, um único tread de instruções está sendo executado. Esse tread de controle único permite que o processo execute apenas uma tarefa de cada vez.

## Escalonamento de Processos

Entretanto com o crescimento dos recursos computacionais se fez necessário que houvesse por parte do SO um processo de gerenciamento e alocação de recursos de CPU para os processos que estão sendo executados no sistema. Quando múltiplos processos competem pela CPU ao mesmo tempo, o escalonador de processos entra em ação para decidir qual processo será executado em seguida e por quanto tempo.

Existem diferentes algoritmos de escalonamento de processos, cada um com suas próprias características e prioridades. Alguns dos principais objetivos do escalonamento de processos incluem maximizar a utilização da CPU, minimizar o tempo de resposta, garantir justiça na alocação de recursos e evitar o starvation (situação em que um processo nunca é selecionado para execução).

Alguns exemplos de algoritmos de escalonamento de processos incluem o algoritmo FIFO (First In, First Out), o algoritmo SJF (Shortest Job First), o algoritmo Round Robin, entre outros. Cada um desses algoritmos tem suas vantagens e limitações, e a escolha do algoritmo adequado depende das características do sistema e dos requisitos de desempenho.

Exemplo de código FIFO(C)
``` c
#include <stdio.h>

// Estrutura para representar um processo
typedef struct {
    int id;
    int tempo_execucao;
} Processo;

int main() {
    Processo p1 = {1, 10};
    Processo p2 = {2, 5};
    Processo p3 = {3, 8};

    // Executando os processos na ordem em que foram criados (FIFO)
    printf("Ordem de execucao dos processos:\n");
    printf("Processo %d executado.\n", p1.id);
    printf("Processo %d executado.\n", p2.id);
    printf("Processo %d executado.\n", p3.id);

    return 0;
}
```
Neste exemplo os três processos são executados na ordem em que foram criados. Representando o conceito de FIFO(First In, First Out), onde processos são executados na ordem em que chegaram.

## Sincronização de Processos
Um conceito importante dos processos é o processo cooperativo que são aqueles que podem afetar outros processos em execução no sistema, ou por eles afetados. Os processos cooperativos pode compartilhar diretamente um espaço de endereçamento lógico, ou podem ser autorizados a compartilhar dados somente por meio de arquivos ou mensagens. O acesso concorrente a dados compartilhados pode resultar em inconsistência de dados, no entanto existem mecanismos para assegurar a execução ordenada de processos cooperativos que compartilham um espaço de endereçamento lógico para que a consistência dos dados seja mantida.

Uma das técnicas utilizadas para sincronizar processo uma que podemos citar é a dos Semáforos que consiste em utilizar uma variável inteira (ou abstração de uma variável) que é usada para controlar o acesso concorrente a recursos compartilhados. 

Operações básicas em semáforos:
- **wait (P)**: Decrementa o valor do semáforo. Se o resultado for negativo, o processo que executou a operação é colocado em espera (bloqueado) até que o semáforo se torne positivo.
- **signal (V)**: Incrementa o valor do semáforo. Se houver processos esperando no semáforo, um deles é desbloqueado.

Os semáforos são usados para implementar exclusão mútua (garantindo que apenas um processo possa acessar um recurso compartilhado de cada vez) e sincronização entre processos (coordenando a execução de processos concorrentes).
## Gerenciamento de memória
 
 O gerenciamento de memória em sistemas operacionais é uma função essencial responsável por garantir que os recursos de memória física sejam utilizados de forma eficiente e transparente para os processos em execução. Em um sistema computacional, a memória é um recurso finito e compartilhado entre vários processos, e o gerenciamento eficaz desse recurso é crucial para o desempenho e estabilidade do sistema.

Existem várias técnicas e estratégias empregadas pelos sistemas operacionais para gerenciar a memória de forma eficiente, uma das que podemos citar é a memória virtual, que permite a execução de processos que não estão totalmente na memória. Uma grande vantagem desse esquema é que os programas podem ser maiores do que a memória física. Além disso, a memória virtual abstrai a memória principal em um array de armazenamento uniforme extremamente grande, separando  a memória lógica, conforme vista pelo usuário, da memória física. Entretanto quando não implementada na maneira correta pode acabar piorando substancialmente o desempenho.

## Desafios e Tendências Futuras

Os sistemas operacionais enfrentam uma série de desafios e tendências futuras, incluindo a necessidade de suportar novas arquiteturas de hardware, lidar com grandes volumes de dados em tempo real, garantir a segurança e privacidade dos usuários, e otimizar o desempenho em ambientes distribuídos e em nuvem. 
## Referências

Tanenbaum, Andrew, S. e Albert S. Woodhull. _Sistemas operacionais_. Disponível em: Minha Biblioteca, (3rd edição). Grupo A, 2008.

Silberschatz, Abraham e Peter Baer Galvin. _Fundamentos de Sistemas Operacionais_.(9° edição),LTZ, 2015 

Jr., Ramiro S., C. et al. _Sistemas operacionais_. Disponível em: Minha Biblioteca, Grupo A, 2019.