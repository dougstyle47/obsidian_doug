# 1 - Introdução 

>"Não há conhecimento que não tenha valor"
>\ - Edmund Burke

Linux se encontra amplamente difundido nos servidores de grandes sistemas, instalar bancos de dados e servidores web, além de gerenciá-los, é uma tarefa comum e relativamente fácil em sistemas Linux.

Uma das formas de pensar um **Sistema Operacional** é imaginar um conjunto de vários programas unidos, aguardando serem usados. As distribuições Linux como **Slackware, Debian, Ubuntu, Red Hat e Fedora** são aglomerado de programas e configurações específicas. Há também o **Android**, que adaptou o kernel do Linux para criar seu próprio sistema operacional focado em dispositivos móveis. 

==Linux é o kernel, o componente central, o coração do sistema.== Conecta os programas de hardware, é a parte central de um Sistema Operacional. Apenas com o Kernel não teríamos muitas opções. Precisamos de programas, configurações, interface gráfica e drivers para tirar um proveito real desse sistema operacional.

Ubuntu é o Sistema usado no Livro. O Ubuntu por padrão já instala uma suíte de aplicativos de escritórios gratuita: o LibreOffice, que possui compatibilidade com os arquivos formatados no Microsoft Office.

Apesar das facilidades que o Ubuntu oferece como um sistema operacional tradicional o foco do livro é no uso para desenvolvedores e administradores de sistemas. Sem dúvida, a ferramenta principal é o ==Shell== do linux.
# 2 - Conhecendo o Shell

Após abrir o terminal/shell/prompt

ubuntu: nome de usuário;
@servidor: é o nome de host;
~: é a abreviação para a pasta do usuário;
$: **Indica que o usuário não possui poderes de administrador**

mostra o diretório que estamos atualmente chamado de current e mostra o caminho
```sh
pwd
```

Exibe o nome do usuário atual que estamos usando
```sh
whoami
```

Retorna a data atual
```sh
date
```

Mostra os comando antes digitados no Shell
```sh
history
```

Para ir até o diretório /
```sh
cd /
```

Lista todos os diretórios ou arquivos presentes no diretório principal
```sh
ls
```

Para limpar o prompt(Ctrl + L =  joga tudo para cima)
```sh
clear
```

Para voltar para o diretório home do usuário(/home/ubuntu é o caminho absoluto)
```sh
cd ~
```

==Para criar um Diretório==( Ex: `mkdir aplicativos`)
```sh
mkdir
```

Para criar um Diretórios com subspastas
```
mkdir -p pai/filho/neto
```

Entrar em um diretório específico(`cd aplicativos`)
```sh
cd 
```

Voltar para o diretório anterior
```sh
cd ..
```

Criar um arquivo e mover para um diretório
`touch` - Cria um arquivo
`mv` - move um arquivo para o destino
`ls` - de listar já visto, mas com o complemento você não precisa estar dentro do diretório
```sh
touch meu_arquivo
mv meu_arquivo aplicativos/
ls aplicativos

```

Copiando um arquivo do diretório meu_arquivo para o  presente diretório.
cp - copiar um arquivo
Feito de dentro do Diretório que você precisa a copia, poderia ser também: 
`cp aplicativos/meu_arquivo /home/douglas`

```sh
cp aplicativos/meu_arquivo . 

```

Existe sempre em diretórios alguns arquivos chamados de arquivos ocultos que o comando `ls` não consegue "puxar" então utilizados com alguns complementos, esses arquivos normalmente possuem um ponto no inicio do nome(.profile).

 `ls -a`: Mostra os arquivos ocultos de forma simples
`ls -la`: Mostra os arquivos ocultos de forma mais detalhada
`ll`: No ubuntu é uma forma reduzida do comando acima

Renomear arquivos, também utiliza o comando `mv`
```sh
mv meu_arquivo meu_arquivo.txt
```

Para exibir mensagens na tela
```sh
echo "Exibindo mensagem na tela"
```

Escrevendo mensagem no arquivo
```sh
echo Escrevendo no arquivo > meu_arquivo.txt
```

Visualizando mensagem dentro do arquivo, O `cat` faz parte de uma coleção de comandos para manipular arquivos.
```sh
cat meu_arquivo.txt
```

Para saber informações sobre um arquivo ou diretório
```sh
file meu_arquivo.txt
file aplicativos/
```

Removendo arquivos 
```sh
rm meu_arquivo
```


Para remover um diretório o comando `rm` não funciona, aparece a mensagem de erro: `cannot remove aplicativos`, se caso o diretório esteja vazio é possível utilizar o `rmdir` mas se caso ele contenha algum arquivo dentro usar o `rm -r`.
==Obs: Cuidado ao utilizar o `rm -r`, é um comando perigoso.==
```sh
rm -r aplicativos/
```

Comando para pedir ajuda para o Shell, exemplos de comando.
```sh
help cd
ls --help
```

Para acessar a documentação padrão do linux(`man`), exemplos de comando.
```sh
man ls
```
Mas é importante você encarar o `man` e sua navegação estranha. Você verá que, no Linux, muitos comandos trabalham de forma similar.


Para saber a descrição simples de um programa:
```sh
whatis ls
```


Para localizar arquivos no sistemas
find (caminho) expressão (ação).
	Alguns critérios de busca definidos em expressão
	`name` = procura arquivos pelo nome;
	`user` = procura arquivos pelo nome do usuário dono do arquivo;
	`atime` = procura arquivos que foram acessados já mais de x dias.

"Busque pelo nome todos os arquivos que contenham a palavra bash no corpo do seu nome"
```sh
find . -name \*.bash*
```
a ação  `-print` que é padrão quando não especificamos de forma explícita.

"Busque por arquivos que comecem com net e terminem com qualquer coisa"
```sh
find /etc/init -name net*
```
O `*` usado em expressões é o mesmo que qualquer coisa.

Busca por arquivos que foram modificados há mais de 1 dia(-1 = menos de um dia).
```sh
find . -atime +1
```

##### Pesquisar sobre TeleTYpe(TTY), que corresponde ao primeiros terminais usados em computadores, normalmente acessado pelo comando Ctrl + Alt + F1.


# 3 - Manipulando Arquivos
Editores de texto no terminal

### O editor Vim
O Vi é o editor básico disponível em grande parte das distribuições Linux. Atualmente este editor é oferecido com mais recursos e recebe o nome de VIM(VI iMproved), no Ubuntu por padrão ele já vem instalado com o nome de `vi`

Comando para entrar no vi
```sh
vi
```

Existem quatro modos no vim
Visual; Inserção; Substituição; Deleção

Sempre que precisarmos entrar no modo visualização clicamos em ESC.

==Para sair do VIM==: Você precisa estar no modo visualização(ESC) e colocar o comando
```sh
:q 
```

Comando para criar um arquivo e edita-lo `vi + nomedoarquivo.extensao`
```sh
vi vim_basico.txt
```

Comando para entrar no modo inserção: `i`
Após alterar o arquivo utilizar no modo Visualização o comando para salvar
```sh
:w
```


No vim podemos navegar pelo arquivo usando as teclas direcionais ou as teclas
• h: move para a esquerda;
• j: move para baixo (próxima linha);
• k: move para cima (linha anterior);
• l: move para a direita.

Mais comandos que facilitam a movimentação:
• G: move para a última linha do arquivo;
• gg: move para a primeira linha do arquivo;
• 0: move o cursor para o início da linha;
• $; move o cursor para o final da linha.

Alguns comandos básicos para ajudar na inserção de texto:
• i: para inserir texto antes do cursor;
• a: para inserir texto depois do cursor;
• A: para inserir texto no final de uma linha onde se encontra o cursor;
• o: para adicionar uma linha abaixo da linha atual;
• O: para adicionar uma linha acima da linha atual.

Temos também comandos para alteração e localização no modo visual:
• x: deleta o caractere onde está o cursor;
• dd: deleta a linha atual;
• u: desfaz a última modificação no arquivo;
• yy: copia uma linha, `p` cola o que foi copiado;
• `/palavra`: busca pela palavra ou caractere em todo o arquivo.

### O editor Nano
O Nano é mais uma alternativa para edição de textos no terminal, está disponível em quase todas as distribuições linux, assim como o Vim.

Para abrir o nano basta escrever no terminal
```sh
nano
```

comandos básicos(sendo ^ = Ctrl):
• ^G apresenta a tela de ajuda sobre mais comandos do editor;
• ^X sai do editor; se o arquivo não estiver salvo será solicitado para salvar antes
de sair;
• ^O salva um arquivo;
• ^W busca por uma palavra dentro do arquivo.
• ^R selecionar um arquivo para editar;

### Cat
Para criar um arquivo e começar a escrever comando nele podemos utilizar o cat
```sh
cat > agenda
```
e depois para visualizar utilizar `cat agenda`

`cat -et nomeArquivo`: coloca ao invés do `<tab>` coloca um ^
`cat -n nomeArquivo`: enumera as linhas presentes no arquivo


Concatenação de arquivos(juntando os arquivos vim_basico e agenda e criando o concatenando.txt)
```sh
cat vim_basico.txt agenda > concatenando.txt
```

Comandos `head` e `tail`. Mostram os primeiros e ultimas 10 linhas de um arquivo respectivamente, mas com o comando -n conseguimos definir o número exatamente.

`head` primeiras 3 linhas
```sh
head -n 3 concatenando.txt
```

`tail` ultimas 3 linhas
```sh
tail -n 3 concatenando.txt
```

# 4 - Compactação e descompactação de arquivos
O linux por padrão já possui vários utilitários de compressão de arquivos. Compactar arquivos e diretórios é uma boa prática para realização de backups.

### Tar
Serve para agrupar vários arquivos ema apenas um. Isso, na prática, evita que precisemos fazer várias transferências de arquivos entre computadores, enviando apenas um único arquivo.

>Basicamente existem três tipos de arquivos que são utilizados como .tar:
`tar.gz`, `tar.tgz`, `tar.bz2`

Ao utilizar o .tar, ele realiza um cópia sem compactação dos arquivos passados como parâmetro, ou seja ele junta todos os arquivos em único arquivo sem compactar.

Algumas opções do tar:
- -c: cria um novo arquivo .tar e adiciona os arquivos a serem compactados;
- -f: indica que o destino é um arquivo em disco;
-  -v: exibe o nome de cada arquivo compactado;
- -x:  extrai os arquivos agrupados no arquivo .tar.

Juntar todos os arquivos que terminam em .txt em apenas um
```sh
tar -cf backup.tar *.txt
```

 Separação de todos os arquivos presentes no arquivo 
```sh
tar xvf backup.tar
```

#### 1- .tar.gz
Realiza dois processos diferentes, primeiro ele cria um arquivo .tar e em seguida, compacta utilizando o formato .gz. Ou seja além de gerar um único arquivo como o .tar, ele será compactado, reduzindo assim o seu tamanho.

Gerar um único arquivo e compactar todos os que estão com formato .txt
```sh
tar zcvf backup.tar.gz *.txt
```

Verificando a diferença de tamanho entre os arquivos
```sh
du -h backup.tar backup.tar.gz
```
`du` - Comando que exibe o número de blocos usados para arquivos, o tamanho

Descompactação dos arquivos `gz`
```sh
tar zxvf backup.tar.gz
```
#### 2- .tar.bz2
Ocorre o mesmo caso que com o .tar.gz: a compactação com o formato .bz2 é mais eficiente que o .gz, **porém é mais lenta na hora de gerar a cópia**

Gerando um único arquivo e compactar todos os que estão com formato .txt
```sh
tar jcvf backup.tar.bz2 *.txt
```

obs: Após utilizar o comando `du` as duas formas de tar apresentam o mesmo tamanho mas isso ocorre pois os arquivos que estamos trabalhando são pequenos.

Descompactação dos arquivos
```sh
tar jxvf backup.tar.bz2
```

#### Gzip/Gunzip
Foma de compressão mais utilizada no Linux. O `gzip` gera um arquivo no formato `.gz`
```sh
gzip -c -r *.txt > backup.gz
```
-c: Criar um arquivo
-r: Compactar
Compactação de vários arquivos utilizando o `gzip`, os arquivos serão concatenados em um só e em seguida comprimidos no formato `.gz`.

Para descompactar usamos o `gunzip`, com as opções -c e -v para exibir outros conteúdos.
```sh
gunzip backup.gz
```
Ao executar a descompactação com `gunzip`, o nosso arquivo `backup.gz` deixará de existir pois por padrão o `gunzip` extrai o arquivo comprimido no formato .`gz` e exclui o arquivo compacto.

#### Zip/Unzip
`zip `Cria um arquivo compacto no formato `.zip`, enquanto o `unzip` faz o trabalho inverso, descompactando.
```sh
zip backup.zip *.txt
```

Descompactando os arquivos
```sh
unzip backup.zip
```


# 5 - Entendendo a estrutura de diretórios
A estrutura de diretórios armazena arquivos de forma hierárquica, de maneira que o o usuário não precisa conhecer os detalhes técnicos do sistema de armazenamento. Mas para poder navegar e obter informações é preciso entender essa estrutura.

No ubuntu a estrutura de diretórios segue o padrão LSB(Linux Standard Base), que por sua vez segue a especificação do FHS(Filesystem Hierarchy Standard). Esses padrões são importantes pois ajudam a manter a compatibilidade entre as variações de distribuições Linux.

Um diretório é um local onde guardamos arquivos no sistema, também conhecidos por pastas. A primeira listagem de diretórios, que pode ser chamada de *árvore* 

Verificando o conteúdo do diretório `raiz`.
```sh
ls /
```
O `/` é um diretório - ==podemos dizer que é o principal diretório do sistema==, pois nele ficam todos os outros. No windows podemos pensar como no `c:` ou no ícone Meu Computador. Todo diretório dentro do raiz `/` é chamado de subdiretório.

Na estrutura, O FHS determina que obrigatoriamente uma distribuição Linux deve conter 14 diretórios.

`/bin` : Armazena arquivos executáveis binários, que são comandos base para a execução do sistema, por exemplo o `ls` e `cd`. Esse diretório é público, ou seja, qualquer usuário pode usar os executáveis que estão lá.

`/boot`: Contém arquivos de inicialização do sistema, dentre os quais está o gerenciador de *boot* do sistema. Ele é um aplicativo que carrega o sistema operacional durante a inicialização.

`/dev`: Mantem o caminho dos dispositivos instalados no sistema. Todo o hardware reconhecido pelo sistema é representado por um arquivo nesse diretório, por exemplo, disco rígido e placa de vídeo.

`/etc`: Ficam os arquivos de configuração do sistema, scripts de inicialização, configuração padrão, para usuários e arquivos de configuração de programas que são instalados. Será muito utilizado na instalação de aplicativos.

`/lib`: Contém as bibliotecas e módulos do *kernel* que são essenciais para o funcionamento do sistema. As bibliotecas são funções compartilhadas que podem ser usadas por vários programas.

`/media`: Responsável por manter os pontos de montagem, ou seja, quando inserimos um pen drive é neste diretório que ele ficará disponível temporariamente enquanto usamos

`/mnt`: Utilizado para montagem temporária de sistemas de arquivos, isto é, um HD ou um pen drive. Este diretório pode ser usado da mesma forma que o `/media`

`/opt`: É onde normalmente instalamos programas que não fazem parte oficialmente da distribuição. Por exemplo, o google chrome.

`/sbin`: Ficam os comando utilizados para inicialização, reparação e restauração dos sistema. É um diretório de comando essenciais, mas com a diferença de que apenas um usuário pode usar, o `root`.

`/srv`: Mantém dados de serviços disponíveis pelo sistema e pode ser acessado de forma geral(por todos os usuário), por exemplo, *web server*.

`/tmp`: Ficam armazenados arquivos temporários, informações que devem ser mantidas até o fim de uma operação, como um download em andamento ou arquivos de cache de vídeos do Youtube.

`/urs`: São mantidos programas que não são essenciais para o funcionamento do sistema. Programas instalados pelo usuário, como editores, programas gráficos, gerenciadores de janelas são exemplos disso.

`/var`: Contém arquivos de dados variáveis, ou seja, arquivos que podem aumentar de tamanho, como arquivos de log, arquivos de banco de dados e mensagens de e-mail.

#### Diretórios opcionais
Os diretórios `/home` e `/root` são opcionais - eles podem existir no sistema mas não obrigatoriamente com estes nomes, apesar de serem assim com frequência!

`/home`: Armazena os diretórios e arquivos dos usuários cadastrados no sistema, por exemplo `/home/douglas`. Ele poderia ser chamado por outro nome como `/minha_pasta`, por exemplo, e isso não afetaria em nada a estrutura do sistema.

`/root`: É a pasta pessoal do **superusuário** `root`.


#### Os diretórios `/proc` e `/sys`

`/proc`: Contém arquivos temporários de processos em execução no sistema. Em outras palavras, é um diretório virtual usado pelo kernel. Nele são mantidos configurações atuais do sistema e dados estatísticos. 

`/sys`: Armazena quase o mesmo conteúdo porém de forma mais organizada para podermos administrar.

# 6 - Administração de usuários
O linux é um sistema multiusuário, ou seja, que pode ser usado por várias usuários simultaneamente, sem que interfira nas atividades do outro, nem consiga alterar seus arquivos. Um bom exemplo seria um servidor web compartilhado, baseado em Linux, que hospeda alguns milhares de sites, cada um administrado por um usuário diferente.

As restrições implementadas no sistema de permissões são muito eficientes. Esse esquema de permissões é fundamental para o funcionamento do sistema por completo. As permissões consistem em um conjunto de três regras: ==leitura, escrita e execução==. É graças a esse esquema de permissões que não vemos sistemas Linux infectados por malwares ou vírus.

Para entender sobre o controle de usuários, vamos dividir esta seção em três categorias:
1 - Super Usuário(sudo) ou Administrador;
2 - Usuário de Sistema;
3 - Usuário Comum.

#### Usuário administrador e sudo
No sistema é chamado de `root`. Ele é responsável por controlar todo o sistema e não possui restrições. Sempre que executamos algum programa ou tarefa que necessite de poderes administrativos, precisamos do `root`, que chamamos por meio do comando `sudo`.

Sempre que fomos instalar um programa ou atualizar todo o sistema usaremos o comando `sudo` para ter as permissões de `root` e conseguir efetuar essas tarefas.

#### Usuários de sistema
São usuários que não necessitam logar no sistema - eles existem para controlar serviços e normalmente não possuem senhas.

#### Usuários comuns
São contas criadas para utilizadores do sistema. Essencialmente, eles podem executar tarefas básicas como criar  e editar documentos, navegar na interne, assistir vídeos e etc.

### Permissões
As permissões são opções que permitem um usuário ter controle de acesso, leitura e gravação de arquivos.Os três tipos de permissão são:  r (leitura) , w (escrita) , x (execução)

- **Arquivos de leitura:** podem ser abertos e ter seu conteúdo visualizado, assim como pastas com o mesmo tipo de permissão podem ter os arquivos listados.
- **Arquivos de permissão de escrita:** podem ser alterados - o usuário, neste caso, tem permissão para editar um arquivo e até apagar. Em diretórios é possível criar um novo arquivo.
- **Permissão de execução**: Dá a possibilidade de executar um arquivo como um programa, por exemplo um `script` de instalação de um aplicativo.

Listar detalhadamente os arquivos presentes no diretório
```sh
ls -l
```
-l = long listing

Exemplo da saída do prompt:
```sh
-rw-rw-r-- 1 douglas douglas   936 abr  3 09:40 backup.gz
-rw-rw-r-- 1 douglas douglas 10240 abr  2 16:49 backup.tar
-rw-rw-r-- 1 douglas douglas  1023 abr  3 09:19 backup.tar.bz2
-rw-rw-r-- 1 douglas douglas   923 abr  3 08:55 backup.tar.gz
-rw-rw-r-- 1 douglas douglas  1453 abr  3 10:00 backup.zip
-rw-rw-r-- 1 douglas douglas   115 abr  2 15:35 concatenando.txt
-rw-rw-r-- 1 douglas douglas   123 abr  2 15:18 nano_basico.txt
-rw-rw-r-- 1 douglas douglas  1423 set 27  2023 postgresql.txt
-rw-rw-r-- 1 douglas douglas    56 abr  2 15:34 vim_basico.txt
```

Significado:
`-`: significa "desabilitado" ou permissão negada;
`r`: permissão de leitura, apenas lê um arquivo;
`w`: permissão de escrita, pode escrever em arquivos e diretórios;
`x`: permissão para executar um arquivo.

A aplicação de permissões aos arquivos está liga a três entidades, que são classes de acesso aos arquivos:
`u`: usuário dono do arquivo;
`g`: grupo a que o arquivo pertence;
`o`: outros usuários que não sejam o dono nem pertençam ao grupo.

A lista com `ls -l`, os primeiros caracteres indicam o modo do arquivo
```sh
-rw-rw-r-- 1 douglas douglas    56 abr  2 15:34 vim_basico.txt
```
O primeiro caractere indica se é um diretório, link ou um arquivo. Os outros 9 caracteres *formam três grupos de três caracteres*
- O primeiro caractere de casa grupo representa a permissão de *leitura*, r.
- O segundo caractere representa a permissão de escrita, w.
- O terceiro caractere representa a permissão de execução,x.
- Quando o caractere -(hífen) é exibido, significa que a permissão está desligada.

Os três grupos:
`rw-`: dono
`rw-`: grupo
`r--`: outros
`douglas`: dono
`douglas`: grupo
As permissões para o *dono* do arquivo são de leitura e escrita. As permissões para o *grupo* ao qual o arquivo pertence são também de leitura e escrita, es permissões de `outros` são apenas de leitura. `douglas` é o nome doo dono do arquivo e também é o nome do grupo para a qual o arquivo pertence. É possível visualizar as permissões no ambiente gráfico também.

### Atribuindo permissões
O comando para atribuir permissões é o `chmod`, ele atua diretamente nos níveis *dono, grupo e outros.*

sintaxe: `chmod [opções] modo_arquivo`

opções para modo de arquivo:
`-c` : lista informações sobre os arquivos modificados;
`-f` : ignora mensagens de erro;
`-R` : modo recursivo, altera as permissões de todos os arquivos e diretórios;
`-v` : lista de forma detalhada as alterações de atributo.

### Bits de atributo(REVISAR)
São um controle adicional as permissões de arquivos. As entidades *dono, grupo e outros* têm suas configurações setadas pelo dono do arquivo. Essas configurações podem ser representadas também pelos *bits de atributo*, ou seja, assim como existem três entidades, também existem três *bits de atributo*, que podem estar ligados ou desligados.

**Bit SetUID:** Permite que um arquivo seja executado da mesma forma que é executada pelo dono.
**Bit SetGID:** Permite que um arquivo seja executado como se fosse parte do grupo pelo seu dono. Quando um arquivo é criado em um diretório que possui este bit ativo, ele é criado com o mesmo grupo do diretório.
**Bit Sticky:** Ativa uma proteção para o arquivo e não permite que ele seja apagado, a não ser pelo próprio dono.

Para indicar se um *bit* está ativo ou inativo, usa-se(1 ou +) para ativo e (0 ou -) para inativo.

Os bits de proteção definem proteções básicas de um arquivo, como vimos anteriormente,são *leitura, escrita e execução*. Ativar ou não esses bits é o que define as permissões d quem poderá trabalhar com o arquivo.

bits de proteção são definidos por três grupos de três bits,sendo que cada grupo possui três bits e cada bit representa uma permissão
```sh
000 000 000
```
As permissões de cada entidade são representadas por cada grupo de três zeros e são lidas sempre da esquerda para a direita. Quando usamos o comando `ls -l`vemos as permissões de outra maneira: `rwx rwx rwx`

#### Os tipos de notações
Juntando os bits de atributo e de proteção temos um total de 12 bits, sendo 3 de atributos e 9 de proteção. Binária: `000 000 000 000` Simbólica: `sst rwx rwx rwx`

A notação octal converte cada grupo de 3 bits em um caractere que de 0 a 7:

| Grupos:   | Dono | Grupo | Outros |
| --------- | ---- | ----- | ------ |
| Simbólica | rwx  | r-x   | r--    |
| Binária   | 111  | 101   | 100    |
| Octal     | 7    | 5     | 4      |

Usando o `ls -l agenda` 
```sh
\\output
-rw-rw-r-- 1 douglas douglas 59 abr  2 15:26 agenda
```
O arquivo possui permissão de leitura e escrita para o dono e para o grupo e apenas de leitura para o outros.

`chmod` para manter as permissões para dono e grupo e setar uma nova permissão para outros
```sh
chmod u=rw,g=rw,o=rw agenda 
```
u = usuário dono, g = grupo, o = outros 

Arquivo Agenda após o `chmod`
```sh
-rw-rw-rw- 1 douglas douglas 59 abr  2 15:26 agenda
```

Forma octal de representar o comando:
```sh
chmod 666 agenda
```

```sh
chmod -v 664 agenda
```
output: `mode of 'agenda' changed from 0666 (rw-rw-rw-) to 0664 (rw-rw-r--)
A opção `-v` do `chmod` nos mostra duas notações de modo que fica fácil comparar e entender o que estamos fazendo.

| Binário | Simbólico | Octal |
| ------- | --------- | ----- |
| 000     | ---       | 0     |
| 001     | --x       | 1     |
| 010     | -w-       | 2     |
| 011     | -wx       | 3     |
| 100     | r--       | 4     |
| 101     | r-x       | 5     |
| 110     | rw-       | 6     |
| 111     | rwx       | 7     |


#### Criando Grupos
O usuário deve pertencer a uma grupo e pode ser adicionado a outros grupos. 

`addgroup` criando um grupo chamado *suporte*
```sh
sudo addgroup suporte
```
output: `Adding group 'suporte' (GID 1005)`
automaticamente ele recebe o seu número GID

#### Criando usuários
O comando `adduser`, que pode também adicionar usuários em grupos e até criar novos grupos.

`adduser juliane` irá adicionar o usuário `juliane`solicitando as informações adicionais como: nome, senha, grupo, pasta home...

```sh
sudo add juliane
```
output: Adding user `juliane' ...
	Adding new group `juliane' (1002) ...
	Adding new user `juliane' (1001) with group `juliane' ...
	Creating home directory `/home/juliane' ...
	Copying files from `/etc/skel' ...
	New password: `sky`
	BAD PASSWORD: The password is shorter than 8 characters
	Retype new password: `sky`
	passwd: password updated successfully
	Changing the user information for juliane
	Enter the new value, or press ENTER for the default
		Full Name []: 
		Room Number []: 
		Work Phone []: 
		Home Phone []: 
		Other []: 
	Is the information correct? [Y/n] y


Algumas informações de juliane
```sh
id juliane
```
output: `uid=1001(juliane) gid=1002(juliane) groups=1002(juliane)`

Usuários presentes no sistema
```sh
ls /home
```
output: `douglas    juliane`

Adicionando juliane ao grupo suporte
```sh
sudo addgruoup juline suporte
```

Verificar quais grupos juliane está inserida
```sh
groups juliane
```
ou 
```sh
id juliane
```

Um novo usuário pode ser criado e de imediato já possuir um grupo de nossa escolha. O adduser poderia fazer isso recebendo como argumentos o nome do usuário e o nome do grupo: `adduser (usuário) (grupo)`. E para remover usuário e grupo poderíamos usar o comando `deluser`, quem a seguinte sintaxe: `deluser (usuário) (grupo)`

#### Alterando grupos
Cada arquivo e diretório possui um dono e um grupo. Tanto o dono como o grupo ao qual um arquivo ou diretório pertence podem ser alterados.

Alterando o grupo do arquivo agenda: douglas > suporte
```sh
sudo chgrp suporte agenda
```
Agora quem pertence ao grupo suporte passam a ter acesso ao arquivo agenda, neste caso o usuário `juliane`

Alterando o dono do arquivo para `juliane`
```sh
sudo chown juliane:suporte agenda
```
não é possível abrir o arquivo agenda com o usuário douglas

Voltando o dono e o grupo do arquivo para douglas
```sh
sudo chown douglas:douglas agenda
```

Comando `sudo` é quem tem o pode de delegar todas as atribuições no sistema e escolher usuários, grupos e permissões.


# 7 - Instalando pacotes e aplicativos

==Cada distribuição Linux possui pacotes específicos. ==

Pacote é um conjunto de arquivos agrupados para facilitar a instalação e distribuição de um programa. Ele pode conter `scripts` para listagem e checagem de dependências para configuração durante o processo de instalação de um aplicativo

No *Ubuntu* os pacotes são baseados em *Debian* e têm a extensão `.deb`

> Para instalar pacotes no Ubuntu no ***modo gráfico*** basta instalar o instalador do pacote pelo site do programa `.deb` e no diretório do mesmo clicar com o botão direito no ícone e escolher a opção *abrir com Central de Programas do Ubuntu* então executar e instalar, o gerenciador irá informar que o pacote foi instalado.


### Gerenciando pacotes com APT
O gerenciador de pacotes no terminal utilizando a ferramenta APT(Advanced Packaging Tool). Usaremos o comando `apt-get`, que é uma interface para a ferramente APT. Assim como o `apt-get` existe o `aptitude`.

Algumas opções do `apt-get`
- `update`: atualiza a lista de pacotes;
- `upgrade`: atualiza todo o sistema;
- `install` : instala um novo programa;
- `remove`: desinstala um programa.

##### Instalando Java

Adicionando uma canal de software
```sh
sudo add-apt-repository ppa:webupd8team/java
```

Após isso atualizar a lista de pacotes
```sh
sudo apt-get update
sudo apt-get upgrade
```

Instalando o Java
```sh
sudo apt-get install oracle-java7-installer
```
ok...ok...ok...

Para verificar se foi instalado e também verificar a versão
```sh
java --version
```


# 8 - Prática, instalando Apache, PHP e MySQL
Objetivo será de instalar e configurar o *web server Apache*, a linguagem de programação PHP e o banco de dados MySQL.

### Apache
Precisamos atualizar a nossa lista de pacotes e instalar um pacote essencial para o processo de compilação de outros pacotes, ele é o `build-essential`, que possui, por exemplo, compilador para a linguagem C(GCC) e outras ferramentas.

atualizando a lista de pacotes
```sh
apt-get update
```

Instalando o pacote `build-essential`
```sh
sudo apt-get install build-essential
```

Instalando o pacote `apache2`
```sh
sudo apt-get install apache2
```

Sempre que quiser obter informações sobre um pacote, utilize o comando `apt-cache`, que possui a seguinte sintaxe `apt-cache show _pacote`
```sh
sudo apt-cache show apache2
```

Se o Apache foi instalado com sucesso, já deve estar funcionando. Faça um teste acessando pelo browser o endereço `http://localhost` ou `https://127.0.0.1`, você verá uma mensagem do Apache informando que o web server está funcionando.

Verificar as opções disponíveis para o serviço `apache2`
```sh
sudo service apache2
```
output:
`Usage: /etc/init.d/apache2 {start|stop|graceful-stop|restart|reload|`
`force-reload|start-htcacheclean|stop-htcacheclean|status}`

o comando service executa o script de serviços *apache2* localizado em `/etc/init.d/apache2`, que possui as várias opções como iniciar, parar,
restartar e outras.

Para parar o serviço apache2
```sh
sudo service apache2 stop
```
A página apache do browser não está mais acessível.

Para iniciar o serviço novamente
```sh
sudo service apache2 start
```

Reinicie sua máquina e veja que, por padrão, o serviço do Apache é inicializado
automaticamente. Alguns pacotes, como o Apache, além de instalar um serviço,
torna-o autoinicializável.

### Linkando arquivos
O `apache` faz bastante uso de linkagem de arquivos em suas configurações. Para fazer um link, utilizamos o comando `ls -s`, que cria um link simbólico para o arquivo de origem - seu conteúdo é o caminho do arquivo.


```sh
/etc/apache2/sites-enabled$ ls -l
```
output:
total 0
lrwxrwxrwx 1 root root 26 Oct 3 23:11 000-default ->
../sites-available/default

o arquivo `000-default` está apontando para o arquivo `default`, que fica no diretório `sites-available`. Vamos criar um link simbólico para o default com outro nome, para isso devemos antes remover o link que já existe:

removendo link default: `/etc/apache2/site-enabled`
```sh
sudo rm 000-default
```

Criando link simbólico para o default(?)
```sh
sudo ln -s
```

Existem dois tipos de ligações:
**Hard Link:** cria um arquivo capaz de compartilhar os dados;
**Link Simbólico:** é somente um caminho para o arquivo original.

No exemplo anterior, criamos um link simbólico. Sem a opção `-s` no co-
mando `ln`, teríamos criado um hard link. Agora qualquer alteração no link
`douglas-config` que se encontra no diretório `sites-enabled` será refletida no
arquivo default, que fica em `sites-available`.
O Linux utiliza bastante o recurso de linkagem de arquivos, até mesmo para re-
presentar o hardware durante o processo de comunicação com o kernel. Liste de
forma detalhada o diretório `/dev`para ver a quantidade de hard links e links simbólicos utilizados pelo sistema.


### MySQL
Sistema de gerenciamento de Banco de dados relacional, muito usado em conjunto com aplicações bem conhecidas como o WordPress.

Instalando o pacote mysql-server
```sh
sudo apt-get install mysql-server
```
-seguir os passos da instalação

verificar o status do serviço mysql
```sh
sudo service mysql status
```

Efetuar login no serviço como usuário root:
```sh
sudo mysql -u root -p
```

Assim como o `apache`, o `mysql` também é um serviço e, como tal, possui as mesmas regras disponíveis no `service`. Isso possibilita parar, iniciar, recarregar, ver o status.

```sh
sudo service mysql stop
sudo service mysql status
sudo service mysql start
```


### PHP(Estudar depois)
Instalaremos três pacotes, `php 5` – pacote da linguagem, `php-pear` – pacote com classes
base para o `php` e o `php5-mysql` – pacote para comunicação com o banco de dados
`mysql`
```sh
sudo apt-get install php5 php-pear php5-mysql
```
obs: pacotes desatualizados, procurar por novos.


precisamos ajustar o seu arquivo de configuração que está em `/etc/php5/apache2/php.ini`


# 9 - Entendendo Processos

Definição de Processo:
>Um processo é um tipo de atividade. Ele tem um programa, entrada, saída e um estado. Um único processador pode ser compartilhado entre vários processos, com algum algoritmo de agendamento sendo utilizado para determinar quando parar de trabalhar em um processo e servir a um diferente.
>\ - Tanenbaum

Ou seja uma representação de um programa em execução utilizando os recursos do computador para realizar alguma tarefa.

Estados de um processo: 
- **Execução:** O processo está ativo utilizando a CPU e outros recursos;
- **Pronto:** O processo está temporariamente parado;
- **Bloqueado:** O processo está parado aguardando a execução de algum evento para voltar ao estado de `execuçao`

Além de possuir esses comportamentos, um processo é capaz de criar outros processos. Quando isso ocorre dizemos que um processo é pai de outros criados por ele, cada processo do Linux recebe um número para sua identificação conhecido por `PID`.

 Comando para ver os PID's dos processos
```sh
ps aux
```
Output:
USER    PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root        1       0.0        0.1    167124 12212 ?   Ss   08:51   0:02 /sbin/init splash
root        2      0.0        0.0      0     0  ?      S    08:51   0:00 kthreadd
root        3      0.0        0.0      0     0  ?       I<   08:51   0:00 rcu_gp
root        4      0.0        0.0      0     0  ?        I<   08:51   0:00 rcu_par_gp
root        5      0.0        0.0      0     0  ?        I<   08:51   0:00 slub_flushwq
root        6      0.0        0.0      0     0  ?        I<   08:51   0:00 netns


#### O processo INIT
Quando inicializamos o Linux, o primeiro processo criado é o `init`, que é conhecido com o pai de todos os outros. Depois de iniciar o ambiente gráfico, quando abrimos um terminal, um processo é criado para controlar o terminal em questão. De forma semelhante, para cada programa aberto também será criado um processo correspondente. ==O  init é responsável por inicializar todos eles e possui identificação de número 1 no sistema==

Um Processo é identificado por seu `PID`(Process Identifier). Esse número é dado pelo sistema para cada processo, cada PID é único, ou seja nunca haverá dois processos fazendo o uso do PID.

Cada processo também possui um usuário dono, para o sistema verificar as permissões e saber qual usuário pode executar um determinado processo. A identificação de donos é feita pelos números `UID` e `GID`.
No linux, todo usuário possui um número de identificação da mesma forma que os processos. Esse número é conhecido por `UID`(User Identifier) e o `GID`(Group Identifier).

#### Verificando Processos
Gerenciar e Verificar os processos é muito importante, pois as vezes precisamos interromper um processo à força ou verificar quais processos estão consumindo mais recursos no computador(CPU, memória, etc)

Para listar  processos do nosso usuário
```sh
ps
```
Output:
PID TTY          TIME CMD
4535 pts/0    00:00:00 bash
4686 pts/0    00:00:05 evince
5383 pts/0    00:00:00 ps
- Possui 3 processos em execução
	- `bash`: Que é o processo do `shell`
	- `ps`: Processo que foi criado ao executar o comando `ps`
	- `evince`: Evince é um visualizador de documentos para múltiplos formatos de documentos, ele está aberto com o PDF do livro em questão. O objetivo do evince é substituir os múltiplos visualizadores de documentos que existem na área de trabalho GNOME por um único aplicativo simples. Evince foi projetado especificamente para suportar os seguintes formatos de arquivo: PDF, Postscript, djvu, tiff, dvi, XPS, suporte SyncTex com gedit, histórias em quadrinhos (cbr, cbz, cb7 e cbt).

- Opções de comandos para o `ps`
	- `a`: lista todos os processos existentes;
	- `u`: exibe o nome do usuário do processo;
	- `x`: lista os processos que não possuem relação com o terminal
	- `m`: exibe a quantidade de memória consumida por casa processo.

Listar de uma forma mais completa os processos em execução
```sh
ps aux
```
Output:
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0 167112 11884 ?        Ss   09:53   0:00 /sbin/init sp
root           2  0.0  0.0      0     0 ?        S    09:53   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        I<   09:53   0:00 [rcu_gp]
root           4  0.0  0.0      0     0 ?        I<   09:53   0:00 [rcu_par_gp]
root           5  0.0  0.0      0     0 ?        I<   09:53   0:00 [slub_flushwq
root           6  0.0  0.0      0     0 ?        I<   09:53   0:00 [netns]
root           8  0.0  0.0      0     0 ?        I<   09:53   0:00 [kworker/0:0H
root          11  0.0  0.0      0     0 ?        I<   09:53   0:00 [mm_percpu_wq

- Note que podemos ver o usuário dono de cada processo na primeira coluna
USER. Em seguida temos o PID de cada processo, informações de consumo de CPU
e memória, outras informações como data e hora de quando o processo foi inicializado, assim como o nome do processo.

Para contar a quantidade processos rodando
```sh
ps aux | wc -l
```
obs:
- o `wc` basicamente o que ele faz é contar as linhas de um arquivo ou do conteúdo que for exibido no terminal, para isso utilizamos a opção `wc -l`. Para informar ao comando que queremos apenas a quantidade de linhas, o que faremos é executar o ps aux em combinação com o `wc -l`, usando o `|` ==(pipe), que é uma forma de encadeamento de processos==, a saída do do  `wc`nos mostra quantos processos ao todo temos rodando na nossa máquina.

#### Grep
O `grep`procura por uma expressão que pode ser uma palavra ou frase em um arquivo, ou ainda pode funcionar como um filtro na saída de comandos.

Buscar todos os processos apache que estão em execução
```sh
ps -A | grep apache
```
output:     
	773 ?        00:00:00 apache2
    774 ?        00:00:00 apache2
    776 ?        00:00:00 apache2
    777 ?        00:00:00 apache2
Obs: 
- `-A` : serve para exibir sem muitos detalhes
- O `grep`realizou um filtro para ignorar todo o resto e exibir somente o apache

#### Top
Outro comando para verificar processos, o `top`, que acompanha os processos atualizando as informações quase em tempo real.

```sh
top
```

Verificar um usuário especifico
```sh
top -u douglas
```

Outra opção mais amigável é o `htop`, que possui uma interface mais amigável, ele não vêm instalado por padrão então:

Para instalar o `htop`
```sh
sudo apt-get install htop 
```

Para rodar o comando
```sh
htop
```

#### Sinais de Processos
Os sinais são uma forma de comunicação usada pelos processos para que o sistema consiga interferir em seu funcionamento. Ao receber um sinal com instruções, um processo interpreta a ação que foi especificada no sinal e a executa.
Alguns sinais:
- KILL: sinal com função de encerrar um processo;
- TERM: termina o processo após ele finalizar uma tarefa;
- STOP: Interrompe a execução de um processo;
- CONT: Ativa a execução de um processo que foi interrompido.

Interrompendo a execução do `mysql/mariadb` enviando um sinal de STOP para o seu processo
Pegando o número do `PID` do `mysql/mariadb`
```sh
ps -A | grep mariadb
```
Output:
	 742 ?        00:00:01 mariadbd

Enviando Sinal de STOP para o `mysql/mariadb`, interrompendo sua execução
```sh
sudo kill -STOP 742
```

Ao tentar logar no mariadb com `sudo mysql -u root -p`, nada vai acontecer pois o processo foi interrompido. É Necessário para que o processo volte a funcionar enviar o sinal `cont` para reativar a execução do processo.

```sh
sudo kill -CONT 742
```
Obs: O processo do mariadb voltou a funcionar

O comando `kill`pode ser usado com o número do sinal em vez do seu nome, como o `-9`, abrindo o editor vim em outro terminal e matando ele no terminal
```sh
sudo kill -9680 
```
Obs:
	No prompt do vim aparece a mensagem: `killed`, pois a execução foi finalizado á força

Outro comando muito usado é o `killall`, quando não sabemos o `PID`ou quando temos vários processos do mesmo aplicativo com vários `PIDs` em execução:

Pegando os `PDI's` do apache
```sh
ps -A | grep apache
```
Output:
	773 ?        00:00:00 apache2
    774 ?        00:00:00 apache2
    776 ?        00:00:00 apache2
    777 ?        00:00:00 apache2

Interrompendo o processo do apache
```sh
sudo killall -STOP apache2
```

Voltando a execução normal do processo
```sh
sudo killall -CONT apache2
```

>Ler mais sobre o `kill`e o `killall`em suas documentações

#### Estados de um processo
Existem 4 estados para um processo
- `executavel`: Após sua criação, o seu estado é esse
- `dormente`: Quando um processo está aguardando alguma rotina para ser executado.
- `parado`: Quando um processo está congelado e por algum motivo não pode ser executado
- `zumbi`: Um processo é considerado *morto*, ou seja, foi finalizado, não está em execução mas por algum motivo ainda existe.

#### Prioridades
Durante sua execução, um processo pode ter prioridade me relação aos outros. Os processos trabalham com níveis de gentileza, que podem ser definidos através do comando `nice` e um número entre -19 e 19, que determina o quão gentil um processo pode ser. Quanto maior for o número definido, mais gentil o processo será, logo quanto menor for o número, maior a sua prioridade.
Normalmente o Linux determina as prioridades de um processo por si só

Em algumas tarefas de backup, setamos a prioridade para que o processo não consuma de forma inesperada recursos do computador como memória e CPU, nesses casos, podemos usar 2 comando: `nice` e o `renice`

Alterando  a prioridade do processo executando o `mariadb`
```sh
sudo renice -19 742
```
Output:
	742 (process ID) old priority 0, new priority -19
Obs: 
	O comando nos informa a prioridade antiga que era o para a nova prioridade que é -19. Ou seja é um processo pouco gentil e todos os outros deixá-lo-ão passar na frente.

Setando uma prioridade gentil para o  `maridb`
```sh
sudo renice +15 742
```
Output: 
	742 (process ID) old priority -19, new priority 15

Após executar o `htop` a coluna `NI` mostra a prioridade dos processos a maioria com o valor 0 e uma opção com a 15 que foi alterado.

# 10 - Introdução a Shell Script

==Script é um programa não compilado que é enviado para um processador. Em seguida, um interpretador lê o seu código e o traduz, de modo que o processador entende suas instruções, que serão executadas em seguida.==
*Shell Script* é uma linguagem de programação utilizada pelo `shell -` no cado o `shell` é o nosso interpretador que vai ler os nossos programas e dizer ao processador o que fazer.
Programas em `Shell Script` são escritos parra tarefas administrativas e repetitivas no Linus. Ao fazer isso, estamos automatizando procedimentos por meio de scripts.

Utilizar algum editor de código(Nano, Vim), salvar como `primeiro_programa.sh`, preferencialmente com essa extensão `.sh`, alteramos as permissões para que ela se torne um executável e rodamos.

#### Programa simples em Shell
```sh
#!/bin/bash
# Nosso primeiro programa em Shell Script

mkdir ~/relatorio
ps aux > ~/relatorio/processos.txt
echo "Programa executado com sucesso!"
```
Obs:
	Linhas que começam com `#` são comentários ou seja, são desprezadas durante a execução do script, porém a primeira linha, que parece um comentário, é na verdade um indicador para informar qual programa irá executar o script. Nesse exemplo o `bash` que está localizado em `/bin`
	Esse script está criando um pasta chamada `relatorio`no diretório `home` do nosso usuário, e depois executa o comando `ps aux`para listar todos os programas detalhadamente. A saída desse comando é salvada em um arquivo chamado `processos.txt`dentro da pasta que foi criada. E por fim o programa emite uma mensagem no terminal informando que foi "executado com sucesso"

#### Executando o Script
É necessário alterar as permissões de para executar o programa
```sh
ls -l primeiro_programa.sh
chmod 777 primeiro_programa.sh
```

Para executar o programa
```sh
./primeiro_programa.sh
```
Output:
	Programa executado com sucesso!
Obs:
	É necessário utilizar o `./`, já que o arquivo está no diretório corrente. Se você tentar executar simplesmente fazendo `primeiro_programa.sh` verá que o shell não encontrará o arquivo.

Verificar se o script funcionou
```sh
ls -l ~/relatorio
```
Output:
	-rw-rw-r-- 1 douglas douglas 25337 abr 30 09:56 processos.txt


#### Operações básicas
O Shell Script também trabalha com operações numéricas, variáveis e estruturas de controle.

Criando um script para contar linhas(`conta_linhas.sh`)
```sh
#!/bin/bash

echo "Contando as linhas ..."
sleep 5 
LINHAS=`cat ~/relatorio/processos.txt | wc -l`
echo "Existem $LINHAS no arquivo."

```

Alterando permissões e executando
```sh
chmod 777 conta_linhas.sh
./conta_linhas.sh
```
Output:
	Contando as linhas...
	Existem 240 linhas no arquivo
Obs: 
	A instrução sleep 5 realiza uma contagem de 5 segundos antes de executar as próximas instruções – em outras palavras é um enfeite.
	Em seguida criamos uma variável chamada LINHAS e atribuímos a ela a instrução para verificar o conteúdo do arquivo `processos.txt` com o comando cat, e em seguida contar a quantidade de linhas no arquivo, fazendo uso do comando `wc-l`. Esta atribuição foi feita por meio do sinal =. Por fim, é exibida uma mensagem que informa a quantidade de linhas existentes no arquivo.

#### Estruturas de Controle
Criar um programa para verificar se um arquivo existe no diretório(`verificador.sh`)

```sh
#!/bin/bash

echo "Informe o nome do arquivo que deseja buscar: "
read ARQUIVO

CONSULTA=$(ls ~| grep $ARQUIVO)

if [ -z $CONSULTA ]; then
	echo "$ARQUIVO não foi encontrado!"
else
	echo "Arquivo encontrado!"
fi
```

Alterando permissão e Executando
```sh
chmod 777 verificador.sh
./verificar.sh
```
Obs:
	A instrução `read` é responsável por ler o que vamos digitar no terminal e armazenar para o script continuar com a próxima instrução.
	Depois de armazenar a palavra que estamos buscando em uma variável, o script executa uma nova instrução, lindando o conteúdo do diretório `home`e filtrando com o comando `grep` em busca da palavra que foi informada.
	Finalmente entra a estrutura de controle if, e o script verifica se a nossa instrução retorna nulo com o parâmetro -z. Se a instrução de consulta for nula, será exibida a mensagem informando que o arquivo não foi encontrado, caso contrário, se o arquivo realmente existir, ele será encontrado na busca e a mensagem informará que foi localizado.


>O conhecimento de Shell Script é essencial para quem pensa em administrar
servidores. Para conhecer mais detalhes desta poderosa linguagem, visite: http://aurelio.net/shell/

#### Backup de gendamento
O `contrab` é responsável por agenda taregas para serem executadas em um período de tempo determinado. Ele é gerenciado por um serviço chamado `crond`, que verifica a existência de agendamentos que devem ser executados.
O `contrab` realiza dois tipos de agendamento
- Agendamento dos usuários, armazenado em  `var\spool\cron\crontabs` 
- Agendamento do sistema, ficam em `etc`

Verificando tarefas agendadas para um usuário
```sh
crontab -u douglas -l
```
output:
	no crontab for douglas
obs:
	não existe tarefa agendada para douglas

Verificando onde ficam os armazenamentos do sistema
```sh
ls -d /etc/cron.*
```
output: 
	`/etc/cron.d /etc/cron.hourly /etc/cron.weekly /etc/cron.daily /etc/cron.monthly`
obs: 
	Podem ser organizados em agendamentos por hora, dia, semana e mês


Criando um exemplo de tarefa  agendada para ser listado o conteúdo da pasta `home` do nosso usuário a cada 1 min.

Para entrar no arquivo para alterar
```sh
crontab -u douglas -e
```
output: 
	no crontab for douglas - using an empty one
	Select an editor. ==To change later, run 'select-editor'.==
	1. /bin/ed
	2. /bin/nano <---- easiest
	3. /usr/bin/vim.basic
	4. /usr/bin/vim.tiny
Choose 1-4:

O código para executar
```sh
*/1 * * * * ls ~ >> ~/crontab.txt
```
Obs: ==Estudar sobre==
	O que a instrução faz é listar a cada minuto o conteúdo de home do usuário douglas e inserir o output da listagem no arquivo `crontab.txt` que será criado também em home. Note o uso do >>, que significa que sempre será inserido o conteúdo da listagem sempre após a última linha do arquivo `crontab.txt`

Verificando o agendamento
```sh
ls cron*
tail -n 3 crontab.txt
```
output:
	Videos
	Virtual Box VMs
	Windows

#### Script de backup
Implementando um script para realizar u backup do diretório `home` do nosso usuário.
- `tar` vai gerar uma cópia do `home`compactada
- `date`irá incrementar as cópias adicionando a informação do dia, mês, ano, hora e minuto em que o backup foi realizado.

Criando uma pasta no diretório raiz(`/`) do sistema
```sh
sudo mkdir /backup
```

O script `backup.sh`
```sh
#!/bin/bash
#Script de backup /home/douglas

sudo tar cazf /backup/$(date +%d%m%y-%H%M)-home.tar.gz -C /home/douglas
```

> Nota: Na hora de escrever no `nano` ele não permitia salvar arquivos talvez pelo motivo de eu sem querer ter salvado o arquivo `backup.sh` no diretório raiz logo tive que colocar um `sudo nano`para ter permissão de salvar o arquivo.

Alterando permissão e executando
```sh
chmod 777 backup.sh
./backup.sh
```

verificando arquivos(não funcionou kkkk)
```sh
ls -l /backup
```
Output:
	total 12
	-rw-r--r-- 1 root root 9935 Oct 13 23:32 13102013-2332-home.tar.gz
Obs: 
	Note que o nome do arquivo gerado contém a data e hora da criação 13102013-2332-home.tar.gz – para ler melhor, imagine o seguinte formato: 13/10/2013-23:32

Para mudar a saída do date no terminal
```sh
date +%d%m%Y-%H%M
```
Output:
	01052024-1422

Com o script de backup, criaremos a tarefa no `cron` para que ele seja executado a cada 5 minutos.

```sh
crontab -e -u douglas
```

alterando script
```sh
*/5 * * * */home/douglas/backup.sh
```
Obs:
	Estamos informando ao crontab para executar o nosso script backup.sh a cada 5 minutos.

>Se você quiser praticar mais, você pode criar um script que faz o backup de um determinado banco de dados do MySQL. Para isso, utilize o comando `mysqldump`, que é instalado junto com o pacote do MySQL.


#### Personalizando Shell
O `shell` pode ser totalmente personalizado. Sendo Shell Script uma linguagem de programação para o ambiente `shell`, temos recursos da linguagem disponíveis por padrão para personalizar.

Acessando variáveis diretamente no console
```sh
NOME="Douglas Soares"
echo $NOME
```
Output: 
	Douglas Soares
Obs:
	Em Shell Script, ao criar uma variável é possível ter acesso ao seu conteúdo armazenado fazendo uso do operador($) - como acabamos de ver, isso funciona diretamente no `shell`

Existem dois tipos de variáveis:
- **Locais: **São restritas a um escopo definido 
		`VARIAVEL_LOCAL = "valor"
- **Globais:** Ficam disponíveis para todo o sistema, também conhecida como variáveis de ambiente, para fazer uso dele é necessário o uso do comando `export` antes de sua definição
		`export VARIAVEL_GLOBAL="valor"`

Um exemplo de variável global é a `PS1`, que é responsável por guardar as configurações de prompt de comandos. Essas configurações apresentam os dados do computador, nome de usuário, diretórios. Por exemplo `douglas@do-IdeaPad3:~$` essa informação é criada e mantida na variável `PS1` 

Verificar o que está armazenado na `PS1`
```sh
echo $PS1
```
Output:
`\[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$`
Obs: 
	Esses códigos armazenados em `PS1` é que definem a forma do prompt. Podemos alterar isso

Outra variável de arquivo muito importante é o PATH, que armazena os caminhos absolutos de arquivos binários(executáveis) de aplicativos.

Verificar o caminho do `PATH`
```sh
echo $PATH
```
Output:
`/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin`

Para buscar o caminho absoluto de um programa utilize o comando `whereis`

Buscando caminho absoluto do vim
```sh
whereis vim
```
Output:
	`vi: /usr/bin/vi /usr/share/man/man1/vi.1.gz`

Como o `$PATH` armazena o trajeto `usr/bin`, ==não precisamos informar o caminho inteiro ao executar o aplicativo vim==, que seria `/usr/bin/bin`. Isso serve para praticamente todos os aplicativos. Podem aparecer casos em que seja necessário alterar o valor da variável `PATH`, o que pode ser feito em `/etc/profile` ou de maneira mais organizada separando por scripts em `/etc/profile.d`

#### Alias
Cria uma apelido para uma determinada instrução. Sua sintaxe é parecida com a definição de uma variável.

O que o alias define no sistema
```sh
alias
```
Output:
	alias egrep='egrep --color=auto'
	alias fgrep='fgrep --color=auto'
	alias grep='grep --color=auto'
	...



Este recurso é bastante útil para não termos que repetir comandos grandes que recebem parâmetros. Exemplos 
- O comando `ls--color=auto` que ativa um esquema de cores para exibir o conteúdo listado de forma mais agradável. Note que o alias para o comando `ls` recebe como argumento o comando `ls --color=auto`, assim, sempre que fizermos uso do `ls`, ele já vai exibir a saída em cores.

- Podemos criar o nosso próprio alias para o comando `clear`. Em vez de digitarmos o `clear` para limpar o buffer do terminal, podemos ter um apelido chamado `cl`. 
```sh
alias cl='clear'
```
Obs:
	O `cl`só vai existir enquanto esta sessão do `shell`estiver aberta.


#### Arquivos de configuração
Quando nos logamos no sistema e abrimos um shell, esse shell é de ==login interativo==
e executa várias instruções de configurações.
Por padrão, ao logar no `shell`, ele vai ler o arquivo `/etc/profile` e executá-lo, aplicando as configurações para todos os usuários do sistema.
Após ler o `/etc/profile`, irá buscas por um dos seguintes arquivos, na pasta `home` do usuário:
- `~/.profile`
- `~/.bash_profile`
- `~/.login`
- `~/.bashrc`


Caso um script seja executado e na sua programação ele faça uso do bash, ele
irá apenas executar o `~/.bashrc`, já que durante essa chamada não se trata de uma
shell efetuando uma operação de login.

Setando um novo `alias` apenas para o usuário `douglas`. Para isso, precisamos editar o arquivo `bashrcc` que existe na pasta `home`do usuário

Abrindo o arquivo para editar
```sh
nano .bashrc
```

Dentro do arquivo de configuração inserir o comando dentro da marcação
```sh
alias cl='clear'
```


Com essa configuração quando você digitasse o comando `cl`no prompt deveria fazer uma limpeza do terminal(`clear`) mas não acontece pois é preciso que o `shell` leia  o script `.bashrc`, existem duas formas de fazer
- Encerrando o terminal e abrindo novamente
- Usando o comando que irá interpretar o script e aplicar a nova configuração sem fechar o terminal
```sh
source .bashrc
```

Limpando o terminal
```sh
cl
```

Além do `.bashrc` no diretório `home` do nosso usuário ainda podemos encontrar mais dois arquivos de configuração
```sh
ls .b*
```
- `.bashrc`
- `.bash_history`: Armazena tudo o que foi digitado no `shell`(lido pelo comando `history`)
- `.bash_logout`: executa instruções logo que saímos do `shell`, ao rodar `exit` e efetuar logout esse script é executado

# 11 - Compilando arquivos fonte
> Compilar ou recompilar um software a partir do código fonte é necessário sempre que precisamos alterar alguma configuração específica que não veio disponível na sua versão pré-compilada, por exemplo, quando instalamos via apt. Além disso, a compilação é bastante utilizada para aplicar atualizações de segurança e habilitar novas funcionalidades no software.

Sempre que formos instalar um software a partir do seu código fonte, veremos um arquivo chamado `configure`, ele na verdade é um aplicativo que ao ser executado verifica no sistema se existem todas as dependências necessárias para compilar o software em questão.
Após a execução do configure, se for concluído com sucesso, ele irá gerar o arquivo `Makefile` que veremos a seguir.
O arquivo `Makefile` é responsável por automatizar o processo de compilação, além de fazer a verificação para ter certeza de que nada faltou e por fim à instalação do software.

#### Compilando
O `wget` é um aplicativo `shell`para executar tarefas de download muito poderoso e tem várias possibilidade de uso

Instalando o `ruby`
```sh
wget -c \ http://cache.ruby-lang.org/pub/ruby/2.0/ruby-2.0.0-p247.tar.gz
```
Obs:
	`-c`do comando `wget` é para continuar o download de onde parou caso ele seja interrompido.
	O uso do `\`foi apenas para formatar o comando no terminal

Descompactando o arquivo para o diretório `usr/local`
```sh
sudo tar zxvf ruby-2.0.0-p247.tar.gz -C /usr/local
```
Obs:
	O comando `-C` do tar indica o diretório de destino ao descompactar o arquivo

Indo o diretório do código fonte do `ruby`
```sh
cd /usr/local/ruby-2.0.0-p247/
```

>A primeira coisa a fazer nesse momento é ler os arquivos README e INSTALL. Dependendo do desenvolvedor do software, ele pode disponibilizar apenas um dos arquivos com informações sobre o software e procedimentos de instalação.

Desabilitando a instalação da linguagem `ruby` para comunicação com a linguagem `C` e desabilitando a instalação da documentação `rdoc` da linguagem `ruby`(não funcionou)
```sh
sudo ./configure \> --disable-install-capi --disable-install-rdoc
```
Output
	`config.status: creating Makefile`


`make` irá basicamente ler o arquivo `Makefile` com as instruções de compilação e executar cada etapa

Para compilar
```sh
sudo maker
```
Obs: caso não haja nenhuma mensagem de erro

Finalizando a instalação
```sh
sudo make install
```
Obs:
	A função make install é essencialmente mover alguns arquivos que foram compilados para os seus devidos lugares e efetivar a instalação.
	

Durante as etapas foram gerados arquivos binários  que servem de auxílio para  durante a compilação. Agora esses arquivos podem ser removidos.

Removendo arquivos binários
```sh
sudo make clean
```

No home, verificar se o ruby foi instalado
```sh
ruby -v
```

O ruby pode ser instalado via `apt`ou seja, essa instalação pode ser apagada, para isso é necessário voltar para o diretório onde se encontra o código fonte da instalação.

Comando para voltar para o último diretório visitado
```sh
cd -
```

Para remover a nossa instalação
```sh
sudo make unistall
```
Obs:
Existe a possibilidade do comando não funcionar pois o criador não disponibilizou a opção `uninstall` para o `make`

Existem duas formas de desinstalar
- Remover manualmente  todos os arquivos de instalação onde o `ruby` foi instalado no sistema `whereis ruby`
- Utilizar o `shell`para remover tudo de uma vez

Utilizando a Segunda opção, ao realizar o `make` gerou um arquivo chamado `.installed.list`, no qual está exatamente a estrutura dos diretórios e arquivos que foram instalados durante o processo de compilação.

Procurando os arquivos `.installed.list`
```sh
cat .installed.list
```

Com a lista de arquivos com os respectivos caminhos podemos montar uma instrução em uma única linha para remover todos do sistema. 
Utilizaremos o `xargs` para combinar o parâmetro inicial com os armentos recebidos da entrada padrão, e dessa forma ele executa o comando ordena uma ou mais vezes.
- `cat`: Para ler
- `rm`: Para Remover
- `xargs`: Para fazer os dois se comunicarem

Removendo o ruby
```sh
cat .installed.list | xargs sudo rm
```
Obs:
	Algumas mensagens de erro ocorrem que não é possível remover os diretórios, mas o objetivo era somente os arquivos

Testando se o ruby ainda está instalado
```sh
ruby -v
```
Output:
	`bash: /usr/local/bin/ruby: No such file or directory`


#### Sempre ler o README ou INSTALL dos programas que for instalar pelo código fonte

# 12 - O que estudar além
### SSH
é um protocolo que estabelece um canal de comunicação seguro entre dois computadores por meio da criptografia e codificação de mensagens de autenticação.  Ele é muito utilizado para estabelecer uma conexão segura com máquinas remotas ou conectar em um servidor remoto.

Foma comum de utilizar o `ssh`: `ssh usernam@servidor_ip`
```sh
ssh doug@192.168.0.114
```
Output:
	doug@192.168.0.114's password: 

O `SSH` utiliza um sistema de criptografia que requer 2 chaves.
- Chave Pública: Que pode ser usado pelo remetente para criptografar os dados antes de enviá-los.
- Chave Privada: Que é usada para decodificar a mensagem original.

No linux o `OpenSSH` trabalha com dois tipos de chaves
- DSA(Digital Signature Algorithm), padronizadas pelo governo dos EUA e o OpenSSH só cria chaves DSA com no máximo 1024 bits, o que é um problema pois seria possível decodificar uma chave DSA a curto prazo.
- RSA(Rives, Shamir e Adleman), pode gerar chaves com até 4096 bits ou até mais e isso as torna inquebráveis na atualidade.

Utilizando o padrão `OpenSSH` que é de chaves `RSA` de 2048 bits. Para Gerar as chaves usaremos o aplicativo `ssh-keygen`

```sh
ssh-keygen
```
Output:
	Generating public/private rsa key pair.
	Enter file in which to save the key (/home/daniel/.ssh/id_rsa):
	Enter passphrase (empty for no passphrase):
	Enter same passphrase again:
	Your identification has been saved in /home/daniel/.ssh/id_rsa.
	Your public key has been saved in /home/daniel/.ssh/id_rsa.pub.
	The key fingerprint is:
	ce:71:1f:c2:54:b4:e6:53:bf:59:72:64:d5:be:46:a7 daniel@localhost
	The key's randomart image is:
Obs: 
	O `ssh-keygen` pergunta onde desejamos salvar as chaves que serão criadas. Por padrão é salvo na pasta `.ssh` na `home` do nosso usuário.
	Será solicitado uma senha e a confirmação de senha para a geração das chaves.

Para listar as chaves
```sh
ls ~/.ssh
```
Output:
	`id_rsa    id_rsa.pub`
Obs:
	id_rsa: Chave privada
	id_rsa.pub: Chave Pública

O que precisamos fazer é fazer é levar a nossa chave pública para o destinatório para ele que iremos estabelecer comunicação com uso das chaves. Para isso utilizar o `scp(secure copy)`: um aplicativo de cópia de arquivos que utiliza o ssh como canal de envio

Fazendo o envio da chave pública com o `scp`: 
```sh
scp ~/.ssh/id_rsa.pub doug@192.168.0.114:~/chave_publica
doug@192.168.0.114's password:
```

*Após enviar nossa chave pública, precisamos entrar e configurar no servidor para
que o mesmo passe a utilizar a comunicação por chaves no ssh:*

==No servidor== precisamos entrar configurar para que ele leia nossa chave pública:
```sh
cat chave-publica >> ~/.ssh/authorized_keys
```

O arquivo `authorized_keys` é responsável por autorizar  quem pode ou não manter o acesso ao servidor via `ssh`

Verificando se o `OpenSSH` está configurado para aceitar login utilizando chaves
```sh
sudo grep 'PubkeyAuthentication'
```
Output: 
	`PubkeyAuthentication yes`
Obs:
	Se a saída do comando retornar no em vez de yes, abra o arquivo `/etc/ssh/sshd_config` e altere para yes.

Agora é possível manter o acesso seguro via ssh sem a necessidade de informar a senha, **nunca revele o conteúdo da sua chave privada.**

### Proteção por Firewall

==O `firewall` tem por objetivo aplicar uma política de segurança por meio de regra que controlam o fluxo de entrada e saída de dados em uma rede e proteger os computadores==

No linux o aplicativo de firewall é conhecido como `iptables`. Existe uma ferramenta que ajuda na configuração do firewall reduzindo a complexidade do `iptables`: UFW(Uncomplicated Firewall), eventualmente o `iptables` será substituido pelo `nftables` para reduzir a complexidade das regras.

### Upstart e Monit

`upstar`: Com ele é possível criar scripts de inicialização e controle de serviços de forma fácil.
`monit`: é um aplicativo para gerenciamento e monitoramento de processos, aplicativos, arquivos, diretórios etc. Ele pode executar ações planejadas e é bastante indicado para monitorar servidores.ls



```sh

```

```sh

```

```sh

```

```sh

```

```sh

```