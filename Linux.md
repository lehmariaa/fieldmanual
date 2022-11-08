# Introdução ao Linux

Para quem está começando, esta será uma área que a princípio parecerá bastante complicada. O Linux pode demorar um pouco para se familiarizar, mas vale a pena o investimento para se familiarizar com ele.

No Linux, você encontrará ferramentas incrivelmente poderosas para  computação em geral, mas mais especificamente para segurança cibernética e o Linux você consegue muitas ferramentas para possibilitar seus estudos de maneira mais prática.
Sob o banner do Linux você encontrará muitas 'distribuições' diferentes. Uma distribuição Linux reúne o kernel Linux - o núcleo do sistema operacional que será praticamente o mesmo - com um gerenciador de pacotes, permitindo instalar diferentes tipos de software e personalizar o sistema operacional. Cada distribuição parecerá e funcionará um pouco diferente, mas na prática, o que vai diferenciar cada uma delas é a forma de uso.

Para algumas pessoas, principalmente iniciantes, é bem comum começarem com o Ubuntu ou Mint. Já para quem gosta de cibersegurança, o Kali se torna bem desejado, devido ao fato de possuir diversas ferramentas já instaladas por padrão no software. Porém, basta voce ter um linux rodando com um terminal e pronto, você ja pode começar aestudar sobre cibersegurança, sem necessariamente ter um Kali instalado, porém, a diferença será em  ter que instalar diversas ferramentas que já vem inclusas no Kali.

Diferentes 'distros' provavelmente também incluirão uma GUI (Graphical User Interface - a parte visual com a qual você interage na tela) semelhante ao que você provavelmente já conhece. 

Embora seja familiar, é provável que haja algumas diferenças. Um dos principais recursos que você pode não ter encontrado muito antes é o terminal, também conhecido como linha de comando. Este é o lugar onde você vai gastar muito tempo! Aqui, você pode executar comandos e ferramentas. 

Aqui eu vou focar em mostrar alguns comandos bastante úteis para quem quer iniciar com Linux e segurança cibernética.

## Linha de comando
Executar comandos na linha de comando do Linux é muito fácil quando você conhece alguns truques e fatos simples.
### **Você pode executar comandos e programas a partir de um shell**

Se você abrir o Terminal em seu sistema, obterá um shell. Esta é uma linha de comando onde você pode executar comandos digitando-os. Por exemplo, digite o seguinte e pressione enter.

```
$ echo "Há $RANDOM garrafas de água na parede"
Há 32057 garrafas de água na parede
```

Isso deve executar o comando echo e, em seguida, imprimir o texto. Se você pressionar a seta para cima no teclado, poderá pressionar enter novamente e executá-lo mais uma vez.
### **Os comandos são encontrados no $PATH**

Quando você digita um comando como `ping` seu sistema Linux procura nos locais especificados no caminho. Esta é uma variável especial que lista os locais onde se espera que os comandos sejam encontrados; locais como `/bin` ou `/usr/bin`. Se você quiser ver quais locais estão incluídos, execute `echo $PATH`. Seria um pouco parecido com o abaixo, dependendo do seu sistema.

```
$ echo $ PATH
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/go/bin
```

### **Você pode usar tabulação dupla para encontrar comandos que não consegue lembrar completamente**

Vá para a linha de comando e digite a letra `p`. Agora pressione o botão 'tab' no seu teclado duas vezes. Você deve ver uma longa lista de nomes de comandos que você pode executar. Agora digite `pi` e tabulação dupla novamente. A lista deve ser reduzida ao subconjunto que corresponde.

### **`apropos` pode encontrar comandos correspondentes por palavras-chave**

Não tem certeza de qual comando usar para um caso de uso específico? `apropos` pode ajudar com isso pesquisando comandos no diretório da documentação de ajuda.

```
diretório de lista $ apropos
IO::Async::Listener (3pm) - escuta nos soquetes de rede para conexões de entrada
acl (5) - Listas de controle de acesso
acpi_listen (8) - ouvinte de eventos ACPI
add-apt-repository (1) - Adiciona um repositório no /etc/apt/sources.list ou ...
add-shell (8) - adiciona shells à lista de shells de login válidos
...

$ apropos ping
Compose (5) - mapeamentos de cliente X para sequências de entrada de várias teclas
a2ping (1) - - converter entre PS, EPS e PDF e outras páginas descr...
avahi-publish (1) - Registra um serviço mDNS/DNS-SD ou nome de host ou endereço...
avahi-publish-address (1) - Registra um serviço mDNS/DNS-SD ou nome de host ou um...
avahi-publish-service (1) - Registra um serviço mDNS/DNS-SD ou nome de host ou um...
...
```

Veja como eles retornam correspondências em potencial para você experimentar? Que maneira legal de aprender novos comandos!

### **Em caso de dúvida, pesquise na Internet!**

Há um grande número de comandos Linux por aí. Alguns padrão e bem conhecidos e alguns mais obscuros para problemas específicos. Você pode usar gerenciadores de pacotes para instalar novos softwares que possa precisar ou até mesmo criar seus próprios binários. Se você está lutando para encontrar o comando que precisa, pesquise na web! A comunidade de usuários avançados do Linux e da linha de comando é enorme, e eles provavelmente têm 10 maneiras diferentes de você resolver seu problema.

## Whoami
 **Encontrando-se**

O comando `whoami` : o nome é bastante descritivo! Como diz o manual (`man whoami`) - este comando exibe o id do usuário efetivo; ou seja, o usuário com o qual estamos logados no sistema.

Isso pode parecer desnecessário a princípio. Em muitos terminais, o usuário atual é mostrado no 'prompt' (a parte comum do texto mostrada antes da entrada que você digita), por exemplo:

```
mainuser@ubuntu: $
```

Aqui podemos ver o que parece ser o usuário: `mainuser`.

No entanto, às vezes em cenários de segurança, talvez por meio da descoberta de uma falha que você conseguiu explorar, você acabará com um shell com o qual está interagindo, onde não é tão óbvio com qual usuário você está operando.

Nesses casos, é muito útil saber quais permissões de usuário você tem. É aqui que entra o comando `whoami`. Ao executar este comando, você verá as informações do usuário que podem não estar disponíveis no prompt:

```
$ whoami
usuário principal
```

> whoami é um comando curto, prático e útil para ajudar você a identificar com qual usuário você está executando. Particularmente importante quando você obteve acesso a um novo sistema e deseja explorar mais.


## **Listar pastas e arquivos**

O comando `ls` , como as notas do manual (`man ls`), listará o conteúdo do diretório. Por exemplo, basta executar `ls` para mostrar o conteúdo do diretório em que você está atualmente:

```
$ ls
dir1 arquivo1 arquivo2 ping
```

Dependendo do conteúdo do diretório, você deverá ver uma série de arquivos e/ou pastas. Estes podem ter cores diferentes representando os diferentes tipos de itens mostrados. Por exemplo, um diretório terá uma cor diferente de um arquivo e outra cor para um arquivo *executável* . Isso é interessante, mas há mais informações que podemos ver.

Há muitos argumentos que podemos fornecer para personalizar o comando `ls` - se passarmos o argumento `-a` para o comando, podemos ver alguns arquivos ocultos que não foram mostrados antes:

```
$ ls -a
. .. dir1 arquivo1 arquivo2 .hiddenfile ping
```

Aqui podemos ver um novo arquivo: `.hiddenfile`. No Linux, qualquer arquivo precedido por um ponto fica oculto por padrão. Embora isso possa parecer uma coisa potencialmente obscura que seria usada por invasores para ocultar arquivos maliciosos - e às vezes é - na verdade, destina-se apenas a ocultar um arquivo do usuário médio para que você possa armazenar facilmente configurações, preferências, informações de cache e em breve.

Você também pode ver `.` que é um link para o diretório atual, bem como `..` que é um link especial para o diretório pai.

Podemos executar o comando com outro argumento - `-l` para mostrar o conteúdo do diretório em formato de listagem longa. Em vez de fornecer argumentos separados `-a -l` no entanto, podemos juntá-los em um, `-al`:

```
$ ls -al
total de 96
drwxrwxr-x 3 mainuser mainuser 4096 Set 5 09:49 .
drwxr-x--- 21 mainuser mainuser 4096 Set 5 09:49 ..
drwxrwxr-x 2 mainuser mainuser 4096 Set 5 09:49 dir1
-rw-rw-r-- 1 mainuser mainuser 0 Set 5 09:49 file1
-rw-rw-r-- 1 usuário principal usuário principal 22 de setembro 5 09:49 arquivo2
-rw-rw-r-- 1 mainuser mainuser 25 de setembro 5 09:49 .hiddenfile
-rwxr-xr-x. 1 usuário principal usuário principal 76744 5 de setembro 09:49 ping
```

Isso nos mostra as permissões associadas a esses arquivos (a primeira coluna de d, r, w, x e -), bem como o tamanho do arquivo (a 5ª coluna, por exemplo, 76744 bytes). 

Como fornecemos vários argumentos com `-al`, ainda podemos ver o arquivo oculto, bem como o formato de listagem longa. Está cobrindo os dois conforme solicitado.

Outro argumento útil pode ser fornecido para mostrar os tamanhos dos arquivos como versões legíveis por humanos:

```
$ ls -alh
total de 96
drwxrwxr-x 3 mainuser mainuser 4.0K Set 5 09:49 .
drwxr-x--- 21 mainuser mainuser 4.0K Set 5 09:49 ..
drwxrwxr-x 2 mainuser mainuser 4.0K Set 5 09:49 dir1
-rw-rw-r-- 1 mainuser mainuser 0 Set 5 09:49 file1
-rw-rw-r-- 1 usuário principal usuário principal 22 de setembro 5 09:49 arquivo2
-rw-rw-r-- 1 mainuser mainuser 25 de setembro 5 09:49 .hiddenfile
-rwxr-xr-x. 1 usuário principal usuário principal 75K Set 5 09:49 ping
```

Aqui podemos ver o tamanho do arquivo representado com o mais comum e legível `K`.

> Você vai usar muito esse comando, então se acostume!

## **Diretórios**

O comando `cd` significa **alterar diretório**, e é exatamente para isso que ele é usado. Você usará o comando `cd` **muito** e, embora tenha algumas funcionalidades extras, há algumas noções básicas que você precisa saber.

O comando `cd` será alterado para um diretório (geralmente chamado de 'dir') com base nas informações adicionais que você fornecer. Há duas maneiras de fazer referência a essas informações adicionais do diretório: **absoluto** e **relativo**.

Um caminho **absoluto** começa no 'início' do sistema de arquivos - a 'raiz' - que pode ser apontada com `/`. Por exemplo, você pode executar `cd /bin` para mudar para a raiz do sistema de arquivos e, em seguida, para o diretório bin.

Um caminho **relativo** é baseado em onde você está atualmente. Por exemplo: se um diretório 'tmpdir' existir dentro do diretório em que você está atualmente, você pode referir-se a ele 'relativo' ao seu local atual simplesmente com `cd tmpdir`. Observe que não há `/` no início!

Se você digitar `cd` por si só, onde quer que esteja, ele mudará para o diretório inicial do seu usuário (por exemplo, `/home/mainuser`). Além disso, se você estiver em outro lugar e quiser fazer referência rapidamente ao seu diretório pessoal, poderá usar o caractere `~` . Por exemplo, se você quiser mudar para o diretório 'tmpdir' acima (supondo que esteja dentro do seu diretório inicial), você pode usar `cd ~/tmpdir`.

Você pode navegar pelos diretórios um por um, por exemplo executando `cd /`, seguido por `cd home`, `cd mainuser` e depois `cd tmpdir`. Você também pode encadear diretórios e fazer a mesma coisa com `cd /home/mainuser/tmpdir`. Vale a pena notar que o `/` por si só aponta para a raiz do sistema de arquivos, mas o caractere '/' também é usado entre os diretórios para separá-los. Pense no '/' no início como um separador entre *nada* e o primeiro diretório. Como não há *nada* antes do primeiro '/', ele aponta para o início do sistema de arquivos!

Um outro uso especial para saber: se você quiser voltar para o diretório anterior, pode fazê-lo com `cd ..`. Isso também pode ser usado várias vezes, bem como entre outros diretórios. (Esse aqui é o que você vai mais usar pra tudo nessa vida, então se apegue principalmente.)

Por exemplo, digamos que você esteja no diretório inicial do seu usuário - `/home/mainuser` - que contém o diretório 'tmpdir' acima. Você poderia executar `cd ../../home/mainuser/tmpdir/../` e terminaria no mesmo diretório em que já está! Você mudou para o diretório pai (`/home`), para o diretório pai novamente (`/`), depois de volta para o diretório `home` , para o diretório do usuário, para o diretório tmpdir e, finalmente, para o seu diretório do usuário novamente.

Este é um comando muito usado e você o usará com frequência, então pratique um pouco! Não se esqueça de usar `ls` para verificar o que está disponível para saber em quais diretórios você pode acessar.

## **Ler conteúdo de arquivos**

O comando `cat`. Este comando tem muita funcionalidade! É frequentemente usado como *cola* entre outros comandos, mas também é uma maneira muito rápida de imprimir informações de um ou mais arquivos na tela.

Por exemplo, digamos que você esteja em um diretório que contém um arquivo - `starwars`. Você pode imprimir o conteúdo desse arquivo com o comando `cat` :

```
$ cat starwars
Que a força esteja com você
```

Se você tivesse outro arquivo - `terminator`, você poderia inspecionar o conteúdo de ambos com um único comando:

```
$ cat starwars terminador
Que a força esteja com você
Eu voltarei
```

Aqui nós conjugamos os dois arquivos; daí o nome do comando!

O comando `cat` não se limita a arquivos de texto. Você pode inspecionar praticamente qualquer arquivo, mas a menos que o conteúdo seja um texto legível, você provavelmente verá um monte de jibberish ilegível!

```
$ cat /bin/ping
@@@@��!�!0001�1����P3P3� 
 ����@ �A� 
 ����0888 XXXDDS�td888 P�td������ttQ�tdR�td� 
 ������/lib64/ld-linux-x86-64.so.2GNU�GNU~ Ȼ��qY˓�L��ZX���ZGNUc�cef(��e�m9�2��� �����1�hd�����������=�"��$OWn
 �_��-����8 #`�S����*����"��n��#��� 
...
```

Assim como a maioria dos comandos, você pode obter mais informações no manual: `man cat`. Isso mostrará os vários argumentos disponíveis, como os úteis `-s` para suprimir linhas vazias repetidas. Na maioria das vezes, no entanto, é apenas uma maneira rápida e fácil de imprimir dados.

Observe que, assim como alterar diretórios, você pode usar isso **relativo** ao seu diretório atual conforme acima para os arquivos 'text' e 'text2' ou para uma referência **absoluta** a um arquivo como o exemplo de ping.

Por fim, a saída do comando `cat` (juntamente com muitos outros comandos) pode ser passada para outro comando ou salva em outro arquivo.

Se você quiser passar a saída para outro comando, você pode usar o caractere 'pipe': `|`:

```
$ cat starwars terminador | base64
TWF5IHRoZSBmb3JjZSBiZSB3aXRoIHlvdQpJJ2xsIGJlIGJhY2sK
```

Ou, se você quiser pegar a saída e colocá-la em um arquivo, você pode usar os operadores `>` ou `>>` . `>` substituirá qualquer conteúdo existente pelos novos dados, enquanto `>>` será anexado - portanto, tenha muito cuidado para usar o correto para sua necessidade!

```
$ cat starwars terminador > moviequotes
citações do filme $ cat
Que a força esteja com você
Eu voltarei
```
## Permissões 
O Linux possui um extenso sistema de permissões e módulos que podem estendê-lo de maneiras incríveis. Ele pode controlar quem pode acessar dispositivos, processos ou arquivos específicos.

Vamos nos concentrar nas permissões de arquivo mais importantes e básicas aqui. Estes são os que controlam quem pode ler, escrever, executar e alguns casos especiais.

O Linux por padrão organiza as permissões em torno de três grupos de usuários:

- O dono. O usuário proprietário nomeado, separado de outros usuários.
- O grupo. Por exemplo, você pode ter um grupo de usuários com esses direitos, por exemplo. 'Usuários de banco de dados'
- Todos os usuários. O padrão que se aplica a todos os outros no sistema

Cada grupo pode então ter uma combinação de permissões, que são ler, escrever e executar. Por exemplo, se você deseja executar um programa, você precisa ter a permissão de execução.

Por exemplo, se listarmos arquivos usando `ls -al` podemos ver os dois arquivos a seguir:

```
-rw-r--r-- 1 usuário AgentJ 887 4 out 13:20 AgentJ.pem
-rw-r--r-- 1 usuário AgentJ 272 4 out 13:24 AgentJ_public.pem
```

Chamemos aqui a atenção para alguns elementos específicos. Observe a sequência `-rw-r--r--`. O primeiro `-` é usado para permissões especiais, então ignore-o por enquanto. Os próximos 3 caracteres são permissões relacionadas ao proprietário (o proprietário é a primeira coluna após o `1` - AgentJ). Aqui vemos `rw-` - isso significa que o proprietário pode ler e escrever, mas não pode executar. Em seguida, o grupo - usuários (a coluna após o proprietário) - pode ser somente leitura, pois exibe `r--`. Os 3 caracteres finais também são `r--` o que significa que todos os usuários também podem ler apenas os arquivos.

Se quisermos atribuir permissões, usamos uma representação numérica das sequências acima. Isso é um pouco mais complexo e existem vários ótimos artigos para você encontrar online. Em poucas palavras, r = 4, w = 2, x = 1. Então, se você quer que um usuário seja capaz de ler, escrever e executar (`rwx`), eles são definidos como 7 (4 + 2 + 1). Se você quiser que eles leiam e executem (`r-x`), eles são definidos como 5 (4 + 1). Leia e escreva? 6! Isso significa que você pode escrever as permissões acima `-rw-r--r--` como 644 - 6 para o proprietário, 4 para o grupo e 4 para todos os usuários.

E se quisermos alterá-los e ver como eles são exibidos? Podemos usar o comando `chmod` para alterar as permissões. Digamos que queremos alterar as permissões para `-rw-r-----`. Isso seria 640 numericamente.

```
$ chmod 640 AgentJ.pem
$ ls -al
-rw-r----- 1 usuário AgentJ 887 4 out 13:20 AgentJ.pem
-rw-r--r-- 1 usuário AgentJ 272 4 out 13:24 AgentJ_public.pem
```

Observe como os 3 caracteres para 'todos os usuários' agora não mostram permissões?

Também podemos usar este comando para controlar as permissões de execução. Vamos copiar um binário e remover as permissões de execução, depois adicioná-los de volta.

```
$ cp /bin/ping ping2
$ ls -al
-rwxr-xr-x 1 usuários do AgentJ 202944 4 de outubro 14:10 ping2
```

Observe como o ping2 tem permissões 'x'? Podemos tirá-los!

```
$ chmod -x ping2
$ ls -al
-r--r--r-- 1 usuários do AgentJ 202944 4 de outubro 14:10 ping2
```

Veja como não há permissões de execução restantes? Você não pode executá-lo agora!

```
$ ./ping2
-bash: ./ping2: Permissão negada
```

Se desejar, você pode adicioná-los novamente para testar o inverso.

```
$ chmod + x ping2
$ ./ping2
```

> As permissões do Linux são muito poderosas, e isso é apenas arranhar a superfície. Eles estão muito bem documentados, então considere uma tarefa de pesquisa para aprender mais. Você pode achar os direitos de suid e sguid especialmente interessantes!


## Executando binários
Executar programas no Linux é muito importante! Talvez você tenha baixado algum utilitário personalizado que deseja executar, talvez tenha um binário com o qual deseja trabalhar em um diretório local. Geralmente, você não quer ficar restrito apenas às ferramentas fornecidas pela distribuição Linux escolhida.

Por padrão, há uma variável importante no Linux; o `CAMINHO`:

```
$ echo $ PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/snap/bin
```

Ele contém os vários locais onde o Linux procurará por binários ou comandos que você deseja executar. Por exemplo, se você perguntar ao Linux qual comando `ping` ele usará para executá-lo, ele estará em um dos diretórios listados no `PATH`:

```
$ qual ping
/usr/bin/ping
```

Às vezes, você pode querer executar um binário fora dos diretórios listados em `PATH`. Se você tiver um arquivo binário em seu diretório atual, poderá executá-lo com o prefixo `./`:

```
$ ./custombinary
bash: ./custombinary: Permissão negada
```

Muitas vezes, se esta for a primeira vez que você está tentando executar um arquivo binário personalizado, você receberá um erro de permissão semelhante ao acima. Como abordamos na seção [Permissões do Linux](https://play.cyberstart.com/field-manual/8fbbbdf0-d7eb-11eb-9d1f-0242ac140009) , você precisará conceder a este arquivo permissões executáveis:

```
$ chmod + x custombinary
$ ./custombinary
Fui executado com sucesso!
```

Assim como outros comandos que vimos, você também pode executar um binário com uma referência absoluta em vez de relativa:

```
$ /home/usuário principal/custombinary
fui executado com sucesso
```

Esta seção é curta, mas importante! Às vezes você inicia um comando e ele simplesmente não para! Talvez você o tenha enviado para calcular pi para um número infinito de lugares? Um bom exemplo é este:

```
$ topo
topo - 15:51:27 até 6:34, 1 usuário, carga média: 0,73, 1,31, 1,47
Tarefas: 552 no total, 1 em execução, 536 dormindo, 15 paradas, 0 zumbi
%Cpu(s): 2,9 us, 1,3 sy, 0,0 ni, 95,6 id, 0,0 wa, 0,0 hi, 0,2 si, 0,0 st
MiB Mem: 31953,4 total, 12456,1 livre, 9597,7 usado, 9899,7 buff/cache
Troca MiB: 976,0 total, 976,0 grátis, 0,0 usado. 20265.2 disponibilidade Mem

    USUÁRIO PID PR NI VIRT RES SHR S %CPU %MEM TIME+ COMMAND
   2720 ​​usuário principal 20 0 4807024 303224 111800 S 10,5 0,9 43:26,26 shell
   2579 usuário principal 20 0 749756 103404 52320 S 8.2 0.3 37:54.08 Xorg
  26238 usuário principal 20 0 5268648 352428 204040 S 7.2 1.1 49:03.33 zoom
   4043 usuário principal 20 0 32,6g 106508 67996 S 5,9 0,3 4:15,92 folga
   4109 usuário principal 20 0 41,1g 303472 100936 S 4,9 0,9 8:42,60 folga
   5381 usuário principal 20 0 32,6g 345900 190540 S 3,3 1,1 10:30,53 cromo
...
```

Se você executou este comando, agora terá uma linda lista de processos em seu sistema, atualizando a cada segundo. Isso é ótimo, mas sua casca se foi! E se você quiser sair?

Você pode pressionar `Ctrl-C` para encerrar o processo. Isso envia uma mensagem para o processo em questão e diz por favor encerrar.

Isso pode não funcionar em todas as situações. Se isso não acontecer, você precisa usar uma ferramenta como `kill` para encerrar o processo.

## ssh
Disclaimer: Aqui será falado sobre o **comando SSH e não o protocolo SSH**.
O comando `ssh` permite que você se conecte de uma máquina a outra, fornecendo acesso **seguro** ao **shell** da máquina conectada.

Isso é muito útil para administração remota de máquinas. Digamos que você tenha um servidor em um data center em outro país e precise controlá-lo. Isso é exatamente o que o SSH permite que você faça!

> Os primeiros s em ssh significam seguro! ssh tem muitas configurações de segurança excelentes e os dados são criptografados por padrão.
>

Há dois componentes principais em uma conexão ssh: o **cliente** e o **daemon**.

O **client** é a ferramenta `ssh` que fica na máquina da qual você está se conectando, o que ajuda você a se conectar a outra máquina.

O **daemon** é responsável por hospedar um agente de escuta na porta ssh (o padrão comum é 22), aguardar as conexões de entrada e tratá-las à medida que elas chegam.

Vamos detalhar um exemplo de comando `ssh` e o que ele fará:

```
$ ssh -p 22 -v mainuser@172.16.6.4
... muitas informações de depuração ...
senha de mainuser@172.16.6.4:
... mensagens de boas vindas ...
Último login: qua 29 de setembro 09:36:19 2021 de 172.16.6.1
mainuser@ubuntu:~$
```

Aqui vemos que o comando `ssh` é executado com alguns argumentos e dados fornecidos. Com o argumento `-p` podemos especificar a porta à qual se conectar. Aqui está a porta 22 - o padrão - mas nem sempre é, então você pode ajustar se necessário.

Depois disso, você verá o argumento `-v` , que solicita a saída *verbose* . Isso é útil para exibir informações adicionais se você estiver vendo erros inesperados.

Por fim, fornecemos o usuário e o endereço ao qual queremos nos conectar - `mainuser` 'no' endereço `172.16.6.4`.

O exemplo acima tem as informações de depuração do argumento `-v` cortadas. Em seguida, vemos uma solicitação para a senha do `mainuser` e, depois que ela for inserida, recebemos as mensagens de boas-vindas do sistema e o prompt para o usuário solicitado na máquina agora conectada.

Neste ponto, podemos fazer qualquer coisa que o `usuário principal` poderia fazer por meio de um terminal na máquina diretamente - navegar no sistema de arquivos, executar comandos, inspecionar arquivos e assim por diante.

Outro argumento digno de nota é `-i`. Isso nos permite fornecer um arquivo de **chave privada** relacionado ao usuário para o qual estamos tentando fazer o ssh, por exemplo:

```
$ ssh -i key.pem mainuser@172.16.6.4
```

Isso significa que você precisa do arquivo 'key.pem' criado anteriormente. Vale a pena examinar esses arquivos de chave SSH se você quiser usar o SSH nos servidores regularmente, pois eles fornecem um nível de segurança mais alto do que as senhas digitadas.

## Comando Grep
O comando grep é notável! Ele permite que você pesquise padrões em arquivos ou dados. É um dos comandos mais poderosos e versáteis que existem!

Você terá muita prática de `grep`, então aqui estão alguns snippets de comando úteis que você pode personalizar:

**Pesquise um arquivo por um termo específico com distinção entre maiúsculas e minúsculas**

```
$ grep "Termo de pesquisa" arquivo.txt
file.txt: Aqui você encontra o termo de busca no conteúdo.
```

**Pesquisar um arquivo por um termo específico ignorando maiúsculas**

```
$ grep -i "Termo de pesquisa" file.txt
file.txt: Aqui você encontra o termo de busca no conteúdo.
file.txt: Também temos sEarCh-tErm posteriormente no mesmo arquivo.
```

**Pesquise todos os arquivos em seu diretório por uma string correspondente**

```
$ grep "Termo de pesquisa" *
file.txt: Aqui você encontra o termo de busca no conteúdo.
other.txt Você verá que o termo de pesquisa também estava em outro arquivo.
```

**Pesquise todos os arquivos em seu diretório por uma string correspondente e todos os diretórios abaixo também!**

```
$ grep -R "Termo de pesquisa" *
file.txt: Aqui você encontra o termo de busca no conteúdo.
other.txt Você verá que o termo de pesquisa também estava em outro arquivo.
some-dir/extra.txt O termo Search-term estava em um arquivo em um dir também.
```

**Pesquise um termo específico em um arquivo, mas mostre algumas linhas antes e depois**

```
$ grep -A 1 -B 2 "Termo de pesquisa" arquivo.txt
file.txt: Algumas linhas acima
file.txt: o conteúdo será exibido.
file.txt: Aqui você encontra o termo de busca no conteúdo.
file.txt: Além disso, um abaixo.
```

Isso mostrará 1 linha depois e 2 linhas antes, e você pode alterá-lo como quiser!

**Procure qualquer linha que não corresponda à string fornecida - inverta-a!**

```
$ grep -v "Termo de pesquisa" file.txt
file.txt: Primeira linha de conteúdo, sempre no topo
file.txt: e então a segunda linha aqui.
file.txt: Algumas linhas acima
file.txt: o conteúdo será exibido.
file.txt: Além disso, um abaixo.
file.txt: Observe que a linha correspondente não é exibida!
file.txt: Também temos sEarCh-tErm posteriormente no mesmo arquivo.
file.txt: A linha acima foi mostrada no entanto (devido ao caso).
file.txt: Última linha do arquivo para completar nosso exemplo.
```

Isso mostrará 1 linha depois e 2 linhas antes, e você pode alterá-lo como quiser!

## SUDO
Sudo significa Super User Do e esse comando é utilizado toda vez que você executar algum comando para instalar alguma ferramenta ou derivados que precise de permissão de administrador no sistema.
Normalmente ao executar um comando `sudo` você precisa digitar a senha de administrador do sistema, portanto, qualquer comando que você rode em um terminal utilizando sudo você estará executando com o máximo de privilégios do sistema.

## APT Install <ferramenta> 
 
Apesar de ainda ser do tempo do `apt-get` hehe, então sempre que você precisar instalar algum pacote do Linux através da linha de comando, basta digitar `apt install <ferramenta/pacote>` que a instalação começará. Algumas vezes pode ser necessário digitar `sudo apt install <ferramenta/pacote>`, que nesse caso, é quando a ferramenta necessita de permissões de administrador no sistema para poder instalar.
  
## Root
  Apesar de não se tratar de um comando, `root` é o usuário com maior privilégio do sistema Linux, logo, acesso root a um sistema significa que você possui mais permissões dos usuários, logo, suas ações como usuário root precisam ser bem cautelosas para não executar nenhuma besteira. De maneira geral, prefira sempre utilizar um usuário comum e utilize o `sudo` para executar ou instalar pacotes no sistema.

