# Determinação do melhor substituto numa equipe offshore com a utilização de Algoritmo Genético

#### Aluno: [Roberto Alejandro Tello Echenique](https://github.com/rob-tello)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC).


---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

---

### Resumo

Nos contratos offshore devido a sua distância de terra e ao regime de trabalho 24 x 7 a manutenção das equipes é de muita importância, não somente para enfrentar os desafios técnicos mas também para manter uma carga de trabalho bem distribuída e sem impactos na qualidade ou na segurança dos serviços.
Equipes em geral devem ser bem equalizadas para fornecer um mix de capacidades técnicas e experiências de forma a poder fazer frente ao dia a dia do trabalho.
Devido a diversos fatores tanto no contrato como em terra, podemos acabar tendo como consequência uma equipe incompleta, com uma configuração diferente do planejado e deficitária em algum aspecto, nestes casos a reconstituição de sua capacidade passa a ser um assunto prioritário.
Este trabalho vem propor a utilização de algoritmos genéticos como ferramenta de apoio a decisão na determinação de uma lista otimizada de possíveis substitutos, ordenados por prioridade, para completar uma determinada equipe offshore, recuperando a sua capacidade técnica e operacional, levando em consideração algumas métricas individuais.


### Abstract 

In offshore contracts, due to their distance from shore and to the 24 x 7 working regime, the maintenance of the teams is very important, not only to face the technical challenges but also to maintain a well distributed workload without impacts on the quality or in the services.
Teams in general must be well balanced to provide a mix of technical skills and experience in order to cope with the day-to-day work.
Due to several factors in the contract or onshore, we can end up having as a consequence an incomplete team, with a different configuration from what was planned and deficient in some aspect, in these cases the reconstitution of its capacity becomes a priority issue.
This work proposes the use of genetic algorithms as a decision support tool in determining an optimized list of possible replacements, ordered by priority to complete a given offshore team, recovering its technical and operational capacity, taking into account some individual metrics.


### 1. Introdução

Para as realizações dos testes foi montada uma planilha hipotética com as métricas de funcionários de 5 contratos offshore de ROV e seus correspondentes substitutos em terra. Nesta lista constam os mais diversos casos sejam de status, experiência, local de origem e custo tal como encontrado na prática.  Neste arquivo foram considerados as seguintes métricas :
- função					
- formação
- status
- tempo de experiência
- tempo na função
- tempo no contrato
- tempo com o equipamento
- cidade de origem
- distância ao ponto de embarque
- custo logístico (terrestre + aéreo)
- custo diário do funcionário


### 2. Modelagem

A determinação da função objetivo foi fundamental para permitir ordenar os funcionários disponíveis para embarque e para isto foi criada uma função que leva em conta as seguintes variáveis:
**Função Objetivo** = *Min* (função + experiência + tempo + custo)
Valor da função = função original – função proposta
Valor da experiência = experiência original – experiência proposta
Valor do tempo = dias de deslocamento até o ponto de embarque.
Valor do custo = custo da logística (terrestre + aérea) + custos dos dias de embarque.
** no caso da função do funcionário e da sua experiência se procura a menor diferença entre quem desembarca e seu substituto. 
Para dar início as simulações se começa com uma ordenação qualquer dos funcionários desembarcados e o algoritmo ordenará os individuos procurando minimizar a função objetivo proposta.


### 3. Resultados

Os resultados encontrados nas diversas simulações foram bastante promissores mostrando que num intervalo de tempo relativamente pequeno (1min <) foi possível classificar e ordenar todos os funcionários desembarcados de 5 contratos indicando as melhores opções de embarque para completar a equipe deficitária.


| Parâmetros para as Simulações    |  Valor |
| :------------------------------- | -----: |
| Convergence                      | 0,0001 |
| Taxa de mutação                  |    0,1 |
| Population Size                  |    100 |
| Random Seed                      |      0 |
| Time without Improvement         |     30 |
| Require Bounds on Variables      |    Not | 

Dentro dos resultados foi verificada uma pequena variabilidade nos candidatos propostos, completamente em linha com a natureza randômica deste processo de otimização.
 

### 4. Conclusões

A utilização de algoritmos genéticos como ferramenta de opoio na determinação dos melhores indivíduos para completar uma equipe offshore se mostrou viável e com as seguintes vantagens:
- possibilidade de aumentar a complexidade da função objetivo;
- possibilidade de inclusão de mais métricas (individuais ou coletivas);
- possibilidade de aumento da lista de possíveis candidatos;
- tempo de simulação curto;
- sistema de classificação impessoal.

Muitas vantagens se considerarmos que normalmente a escolha dos candidatos para preencher a vaga é unicamente baseada na experiência do pessoal de suporte, e como consequência distante de um possível ótimo em termos de experiência, tempo e seu respectivo custo.

Para trabalhos futuros, sugere-se o fechamento do caso com a determinação de como e quando o funcionário original (desembarcado) irá preferencialmente retornar a sua escala de trabalho no navio de origem.


---

Matrícula: 201.110.465

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
