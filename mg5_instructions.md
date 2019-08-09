Em anexo todos os arquivos utilizados para rodar o MadGraph. São 4 arquivos no formato ".dat" e uma pasta comprimida que contém todos os arquivos do modelo. Essa pasta DarkHiggs2MDM deve ser salva dentro da pasta "models" que se encontra dentro da pasta do MadGraph.

O arquivo "param_card.dat" contém todos os parâmetros do modelo dark Higgs e do modelo padrão (MP). No início estão os acoplamentos com o MP e com o setor escuro, gq e gx, respectivamente, e o ângulo de mistura do dark Higgs com o bóson de Higgs, th. Em seguida estão as massas das partículas, e as do setor escuro são denominadas MDM (matéria escura), MHs (dark Higgs) e MZP (mediador vetorial Z'). Você pode usar o comando "scan:[m1, m2, m3, ...]" para rodar o programa para diferentes massas. Além disso, se você utilizar como "scan:[m1,m1,m1,m1]", o MadGraph irá gerar 4x o número de eventos do run_card, cada um com uma seed diferente, mas com a mesma massa (foi o que eu fiz para gerar 300k eventos de uma vez).

O arquivo "run_card.dat" contém informações para o MadGraph. É exatamente o mesmo card que o pessoal do paper seguido como referência utilizou. Encontrado em https://its.cern.ch/jira/si/jira.issueviews:issue-html/ATLMONOSWW-1/ATLMONOSWW-1.html no comentário do Oleg Brandt.

O arquivo "delphes_card.dat" é usado na simulação do Delphes (dentro do MadGraph), com as especificações do paper do dark Higgs, e com um filtro inicial nas partículas de matéria escura e nos neutrinos.

Finalmente, o arquivo "steering.dat" permite rodar todas essas etapas de uma só vez. Basta salvar todos esses arquivos dentro da pasta do MadGraph (com exceção da pasta DarkHiggs2MDM que deve ser salva dentro de models) e rodar o software utilizando o comando "./bin/mg5_aMC steering.dat" (se você estiver dentro da pasta do MadGraph). É possível alterar o processo a ser gerado, o nome da pasta de saída (na linha "output nome_do_folder") e outras informações para o MadGraph dentro desse arquivo.

Testado nas versões MG5_aMC_v2_6_4 e MG5_aMC_v2_6_5, e ambas funcionam sem problemas. 
