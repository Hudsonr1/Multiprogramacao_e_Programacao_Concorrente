
# SISTEMA DE MULTIPROGRAMAÇÃO

<p align="justify">
Um conceito fundamental em sistemas operacionais é o conceito de processo. Um processo é basicamente um programa em execução.
Ele consiste de um programa executável, os seus dados e pilha, o seu stack pointer e registradores, enfim todas as informações necessárias para executar o programa. 
Periodicamente o sistema operacional decide se a execução de um processo deve ser interrompida e a execução de um outro processo deve ser iniciada--pela razão do primeiro já ter tido mais do que a sua `fatia' de tempo de CPU. Em um sistema de multiprogramação a CPU fica se alternando entre a execução de vários processos, cada um por dezenas ou centenas de milisegundos. 
</p>
<Strong>Um processo pode estar em um dos seguintes estados: </Strong>

<pre>
1.Running: usando a CPU naquele instante; 
2.Ready: pronto para ser executado, temporariamente parado para que outro processo possa ser executado; e 
3.Blocked: impossibilitado de ser executado até que algum evento externo ocorra. 
</pre>

<p align="justify">
Em um sistema de multiprogramação temos frequentemente a situação onde vários processos estão prontos para serem executados.
Quando mais de um processo está ready, o sistema operacional deve decider qual processo deve ser executado primeiro.
A parte do sistema operacional que toma esta decisão é chamada de scheduler, e o algoritmo que é usado é chamado de scheduler algorithm.
A cada interrupçao do relógio o sistema operacional toma o controle e decide se o processo que está sendo executado deve continuar a ser executado ou deve ser suspenso para que outro processo passe a ser executado.
A estratégia que permite que um processo que está sendo executado seja suspenso temporariamente é chamada de preemptive schedule. 
Existem scheduling algoritms que assumem que todos os processos são iguais. Entretanto, existem muitas pessoas que possuem e administram centros de computação que discordam disto.
Por exemplo, em um centro de computação de uma universidade pode ser dada a mais alta prioridade aos processos de diretores, depois aos de professores, depois aos de secretarias, depois aos de porteiros, ...e finalmente aos de alunos.
Isto é chamado de um priority schedule (alguns podem chamar isto de injustiça). 
Para evitar que processos que têm alta prioridade fiquem sendo executados indefinidamente o scheduler pode baixar a prioridade do processo que esta sendo executado a cada interrupção do relógio. 
Alguns priority schedulers fazem uso de classes de prioridade. Os processos na classe de prioridade mais baixa podem ser executados sem serem suspensos por no máximo uma QUANTA (uma quantidade de tempo de CPU).
Processos na próxima classe de prioridade pode ser executado por no máximo duas QUANTAS, e assim por diante. Sempre que um processo usa toda as QUANTAS alocadas para ele este processo é rebaixado de classe. 
Quando um processo deseja imprimir um arquivo, ele coloca o nome do arquivo em um diretório especial chamado de spooler directory.
Um outro processo, o printer daemon, periodicamente verifica se existe algum arquivo a ser impresso, se existir ele imprime o arquivo e remove o nome do arquivo do diretório spooler. 
</p>

## PROGRAMAÇÃO CONCORRENTE

<p align="justify">
Do inglês Concurrent Programming, onde Concurrent signifca "acontecendo ao mesmo tempo". Programação Concorrente é diferente de programação paralela!
Tradicionalmente, a grande maioria dos programas escritos são programas sequenciais Para serem executados em um único computador com uma única CPU. O problema é dividido em uma série de instruções que são executadas uma após a outra, uma única instrução pode executar em um determinado instante de tempo. Nesse caso, existe somente um fluxo de controle (fluxo de execução, linha de execução, thread) no programa. Isso permite, por exemplo, que o programador realize uma "execução imaginária" de seu programa apontando com o dedo, a cada instante, o comando que está sendo executada no momento.
Um programa concorrente pode ser visto como se tivesse vários fluxos de execução. 
Para o programador realizar agora uma "execução imaginária", ele vai necessitar de vários dedos, um para cada fluxo de controle
Em programação cncorrente é definido o uso simultâneo de múltiplos recursos computacionais para resolver um problema, para ser executado em diversas CPUs, o problema é quebrado em partes que podem ser executadas (resolvidas) concorrentemente Cada uma destas partes é representada por uma série de instruções, sendo que as instruções de cada parte são executadas concorrentemente em diferentes CPUs.
  É comum em sistemas multiusuário que um mesmo programa seja executado simultaneamente por vários usuários.
Por exemplo, um editor de texto. Entretanto, ter 10 execuções simultâneas do editor de texto não faz dele um programa concorrente. O que se tem são 10 processos independentes executando o mesmo programa seqüencial (compartilhando o mesmo código). Cada processo tem a sua área de dados e ignora a existência das outras execuções do programa, esses processos não interagem entre si (não trocam informações). Neste caso, é usado o termo programação paralela, pois vários programas/processos independentes são executados em paralelo pelo computador. Um programa é considerado concorrente quando ele (o próprio programa, durante a sua execução) origina diferentes processos que  irão interagir entre si para realizar alguma tarefa.

# Paralelismo
<pre> Processamento simultâneo físico </pre>

# Concorrência
<pre>
-> Processamento simultâneo lógico (aparente)
-> Requer entrelaçamento (interleaving) de ações
</pre>

# Processo
<pre> Execução de um programa </pre>

# Programa Concorrente
<pre> Vários processos que cooperam para a realização de uma tarefa </pre>




