<h2 align="center"> PROCESSAMENTO DE IMAGEM </h2>
<h3 align="center">  APLICAÇÃO DE ÁLGEBRA LINEAR PARA MANIPULAÇÃO DE IMAGENS EM PYTHON </h3>
<p align="center"><img src="https://user-images.githubusercontent.com/106626661/200182178-9525b376-715d-46d2-b000-038413b3bd7b.jpg"></p>

## Descrição do Projeto
<p align="justify">
Trabalho da matéria de Álgebra Linear II da Ilum Escola de Ciência.
</p>
<p align="justify">
Esse repositório tem como intuito demonstrar o processo metodológico utilizado para o desenvolvimento da pesquisa. Inicialmente, os desenvolvedores definiram um objeto de estudo de interesse comum, entre os temas apresentados pelo professor, e posteriormente, dividiram as tarefas do trabalho. Como citado, o objeto de estudo é Processamento de Imagens por meio de conceitos estudados na disciplina de álgebra linear.</p>
<p align="justify">
Este projeto foi elaborado pelas estudantes durante o segundo semestre de graduação da Ilum - Escola de Ciência, para a disciplina de Álgebra Linear II. O grupo desenvolvedor é composto pelas estudantes: </p>
<p>:heavy_check_mark: Eduarda Veiga Carvalho  </p>
<p> :heavy_check_mark: Gabriel Xavier Pereira </p>
<p> :heavy_check_mark: Isabela Bento Beneti </p>
<p> :heavy_check_mark: Ygor Fagundes Ruas </p>

## Processo Metodológico
<details><summary><b>Objeto de Análise</b></summary>
<p align="justify">
Durante a primeira aula, discutimos a respeito das áreas em comum que nos interessavam, e percebemos que nossos interesses convergiam para as áreas ecológicas e sociais. Por isso, decidimos explorar um tema relacionado à área socioambiental.
</p>
<p align="justify">
Tendo isso em mente, analisamos algumas das bases disponibilizadas no arquivo "Material de Estudo" e nos interessamos pelas APIs e pelas Databases do INPE. A partir disso, passamos a desenvolver a ideia de um projeto que relacionava as queimadas na vegetação brasileira com outros fatores, tais como precipitação e quantidades de dias sem chuva.
</p>
<p align="justify">
Por fim, decidimos que, a partir desses dados e fatores analisados, tentaríamos fazer uma previsão de focos de incêndio pelo método de regressão linear, utilizando Machine Learning.
</p>
</details>
<details><summary><b>Recortes</b></summary>
<p align="justify">
Uma das grandes discussões realisadas pelo nosso grupo foi sobre quais recortes utilizaríamos para elaborar o projeto. Acabamos por decidir o bioma Cerrado, que é o segundo bioma mais afetado por queimadas em todo o Brasil, e sobre o qual há muitos dados disponíveis para estudo. A escolha do bioma se deu fortemente por pelo aumento de focos de incêndio na região e pela proximidade de uma das desonvolvedoras com o local. Além disso, não optamos pelo bioma da Amazônia devido o grande número de pesquisas quanto a este e a vontade de ressaltar outros biomas negligenciados pela mídia. 
</p>
</details>
<details><summary><b>Divisão de trabalho</b></summary>
<p align="justify">
O projeto tem o intuito de ser dividido em 4 blocos, cada um separado especificamente para as etapas do trabalho, que devem ser concluídas até o final do semestre. Ao analisar a lista de tarefas para o Bloco 1 de Aprendizado de Máquina, decidimos que seria válido que cada uma das integrantes ficasse responsável por um dos tópicos da lista. Ao final, o trabalho foi realizado de maneira bem mais conjunta do que o previsto, já que nós ajudamos umas as outras durante o processo!
</p>
</details>

## Bloco 1
<details><summary><b>Coleta de Dados</b></summary>
<p align="justify">
Durante, principalmente, as primeiras duas semanas desde a definição do nosso tema, pesquisamos intensamente por bancos de dados e APIs que nos auxiliassem no desenvolvimento do nosso sistema de aprendizado de máquina. Priorizamos dados confiáveis e em formatos que facilitassem a manipulação pelo Jupyter na linguagem Python. Concluímos, por fim, após discussões com nossos professores, que os dados do INPE eram de fato os mais seguros e também os mais completos para se trabalhar, contendo neles não apenas a localização exata das queimadas, como também o risco de fogo, o bioma ao qual aquela região pertence, a precipitação, o número de dias sem chuva, entre outros.
 <br>
Coletamos, pois, todos os dados de queimadas do INPE desde o começo de 2022 até julho de 2022. Esse conjunto de dados, para nossa surpresa, não incluía somente informações sobre o Brasil, mas sobre o mundo inteiro. Por isso, na tarefa seguinte (de preparação), foi essencial que filtrássemos os dados.
</p>
</details>
<details><summary><b>Preparação dos Dados</b></summary>
<p align="justify">
Em um primeiro momento, identifica-se os tipos de dados, em nosso caso, são todos do tipo float. Os dados foram normalizados, como o caso do número de dias sem chuva e a precipitação, utilizando o máximo e o mínimo dos valores para que todos os dados fiquem na mesma escala. Posteriormente, os dados começaram a ser analisados.  
</p>
</details>
<details><summary><b>Análise Exploratória dos Dados</b></summary>
<p align="justify">
Após todo o processo de coleta, filtragem e preparação dos dados, pudemos finalmente analisar tudo o que conseguimos obter através do nosso DataFrame. Os resultados que esperamos ter, devem demonstrar que meses em que existe uma baixa taxa de precipitação tendem a ter probabilidades mais altas de queimas em pontos da região, além de também procurarmos ter uma correlação entre os fatores de precipitação e os níveis de risco de fogo, que poderão ser previstos. Assim, a utilização de comandos de matrizes de covariância e correlação é imprescíndível para explorar e computar essas probabilidades, podendo, ao final, gerar gráficos que apresentam tais taxas e variações.
</p>
</details>

## Bloco 2
<p align="justify">
O Bloco 2 tem como intuito, realizar a aplicação de técnicas de modelo de Machine Learning, de modo a identificar qual modelo combina melhor com o código e dataset usufruido. De modo a analisar as divergências de cada técnica e a interferência dos dados normalizados e não-normalizados, desenvolve-se um Jupyter Notebook dividido em duas grandes seções: Treino com dados normalizados e Treino com dados não-normalizados. 
</p>
<details><summary><b>Treino, teste e baseline</b></summary>
<p align="justify">
De modo a iniciar os treinos dos modelos, inicia-se com o modelo mais básico e que será um valor de referência aos demais: o modelo Baseline! Este modelo realiza uma média dos valores da target e geralmente, não apresenta bom resultado preventivo. Utilizamos o RMSE como métrica, obtendo um valor de 25% de erro de predição.
</p>
</details>
<details><summary><b>Treinamento de modelo de <i>k</i> vizinhos mais próximos</b></summary>
<p align="justify">
Dada a parametrização inicial com RMSE de 25%, o objetivo das discentes passou a encontrar um modelo cuja o RMSE fosse menor e se possível, mais próximo de zero. Deste modo, surge o k-nn vizinhos como um modelo cujo a hipótese consiste na ideia de que a similaridade dos dados é condizente com as regiões próximas no espaço de entrada. Os k determinam a quantidade de vizinhos que serão analisados na região, este modelo apresentou um RMSE próximo a zero e observou-se que conforme for menor o número de k menor será o RMSE.
</p>
</details>
<details><summary><b>Regressão linear</b></summary>
<p align="justify">
O modelo de regressão linear não obteve uma boa métrica, chegando a 23%. Este modelo tem como objetivo relacionar linearmente as nossas features e o nosso target, logo, este resultado demonstra que a relação entre as features e o target não estão linearmente relacionadas o que corrabora com a proposta de features de climatologia do nosso modelo, visto que o clima não é uma concepção linear.
</p>
</details>
<details><summary><b>Árvore de decisão</b></summary>
<p align="justify">
Seguindo a série de treinamentos de modelos, introduzimos o algoritmo de árvore de decisão para descobrir a performance desse modelo e compará-la em relação aos outros modelos, podendo observar que é melhor que os modelos anteriormente treinados. Definidos hiperparâmetros para a árvore para reduzir 'overfittings' criados a partir das diferenças entre os dados treinados e não treinados, foi possível perceber que tanto o número de 'nodes' quanto a profundidade da nossa árvore afetam na complexidade e performance do nosso modelo. Ao alterá-los, com a intenção de evitar ajustes excessivos, pode-se concluir que o comportamento do erro quadrático médio não possui grande variação conforme definimos diferentes valores de hiperparâmetro de curtos intervalos de diferença.
</p>
</details>
<details><summary><b>Floresta aleatória</b></summary>
<p align="justify">
Este modelo pode ser compreendido como uma complementaridade ao modelo de Árvore de Decisões. Ok! Mas em que sentido? As árvores de decisões podem apresentar modelos simples e explicativos, mas possuem a desvantagem de nem sempre apresentarem uma boa perfomance, logo, de modo a melhorar essa performance, usufrui-se da Floresta Aleatória cujo o objetivo é o de desenvolver um comitê que contenha diversas árvores de decisão onde cada uma realiza sua previsão individual, cada previsão individual pode ser considerada como um voto e ao ser relacionada com outros votos, possibilita-se a determinação de uma resposta final. O RMSE apresentou resultados próximos a zero e se mostrou eficaz.
</p>
</details>
<details><summary><b>Comparando os desempenhos dos modelos de regressão</b></summary>
</p>
<p align="justify">
Para comparar os cinco modelos preditivos desenvolvidos, comparamos os valores de RMSE e de precisão, a fim de determinar qual deles possuia o melhor desempenho. Para tanto, nós colocamos esses valores em uma tabela, e obtemos o seguinte resultado: 
</p>

| Modelo | Normalizado | Não Normalizado |
| :---       |     :---:      |   ---:        |
| Baseline   | 0,25423701     | 0,25297497    |
| 1 K-NN     | 0,06953842     | 0,08039338    |
| 2 K-NN     | 0,07485483     | 0,084071208   |
| 3 K-NN     | 0,08021297     | 0,088340406   |
| 4 K-NN     | 0,08474465     | 0,092532391   |
| 5 K-NN     | 0,08843453     | 0,096188816   |
| 6 K-NN     | 0,09124067     | 0,099139877   |
| 7 K-NN     | 0,09396136     | 0,1021576465  |
| 8 K-NN     | 0,09655897     | 0,1046688394  |
| Regressão  | 0,23769020     | 0,2370621     |
| Árvore     | 0,08           | 0,08          |
| Floresta   | 0,066630042    | 0,0667153531  |
</p>
Podemos perceber, pois, que tanto para o s dados normalizados quanto para os dados não normalizados, os melhores modelos preditivos (isto é, os que resultam em melhor previsão) são os de FLoresta aleatória e o de K-NN. 
</p>
Direcionando nosso olhar para o K-NN, podemos perceber, também, que os melhores resultados desse modelo são obtidos com menores números de vizinhos selecionados.
<\p>
Isso ocorre pois, no caso dos nossos dados, quando realizamos o modelo K-NN com uma grande quantidade de vizinhos, nós estamos nos "afastando" muito da área que está sendo utilizada para predição, o que torna as previsões menos precisas.
<\p>
O gráfico presente no notebook "Bloco 2" mostra exatamente como o erro desse modelo cresce conforme aumentamos o número de vizinhos analisados:
</P>
<p align="center">
<img width="574" alt="ERRO" src="https://user-images.githubusercontent.com/106626661/192491037-3d8cb660-27f1-4189-8447-d7a3126b8a17.png">
</details>
<details><summary><b>Classificação</b></summary>
O metódo de classificação utilizado foi o K-NN. Em um primeiro momento, necessita-se de dados categóricos, por isso, desenvlve-se uma coluna de classificação categória sobre as chances do risco de fogo. Após esta criação, aplica-se o metódo de classificação e análisa sua accuracy.  
</details>
<details><summary><b>Bloco 2 - Teste.ipynb</b></summary>
<p align="justify">
Esse arquivo presente nosso repositório não faz parte da lista de tarefas oficial do Bloco 2, mas foi necessário para estudarmos o comportamento dos dados de maneira gráfica com a utilização de uma 'target' diferente da original, uma vez que os gráficos plotados de Modelo de Previsão X Modelo Real estavam muito estranhos e ruins. Foi escolhida, dentre as possíveis no nosso Dataframe, uma menos complexa e, supostamente, mais fácil de prever, sendo essa, então, a Precipitação.
</p>
<p align="justify">
Sendo assim, separadamente, os modelos propostos no trabalho foram reproduzidos para essa nova target. Ao plotar todos os gráficos, realmente os modelos estão ruins, comom possível ver no arquivo. Surgimos assim, com algumas hipóteses sobre o que pode ter acontecido, podendo ser, inclusive, uma união de fatores:
</p>
<ol>
<h5>
<li>O primeiro ponto que pensamos, foi a pouca quantidade de features que coletamos, podendo influenciar fortemente nos resultados dos modelos, uma vez que não temos informações básicas como temperatura, umidade do ar e do solo e até o uso de solo;</li>
<li>Em segundo, a falta de especificação e diferenciação de dados numéricos em casas decimais pode ter causado essas linhas verticais de distâncias iguais em determinados valores de <i>x</i> com diversos pontos sobrepostos, de forma que o modelo compreendou que existem muitos valores de <i>y</i> de um mesmo fator para um único <i>x</i>;</li>
<li>Por fim, a falta de normalização de dados (que foi sugerida) em metade do código, em Bloco 2.ipynb, uma vez que os gráficos do modelo de Floresta Aleatória para dados normalizados está muito melhor que o gráfico dos dados não-normalizados.</li>
</h5>
</ol>
</details>

## Bloco 3
<p align="justify">
Neste bloco, trabalhamos com modelos de aprendizagem não-supervisionados. A aprendizagem não supervisionada consiste em identificar padrões nos dados não tabelados e agrupá-los com base nas similaridades e diferenças de valores. As principais tarefas associadas a esse método são agrupamento, associação e redução de dimensionalidade.
</p>

<details><summary><b> Redução de dimensionalidade </b></summary>
<p align="justify">
Iniciamos com o algoritmo de Análise de Componentes Principais (PCA), que reduz a dimensionalidade do conjunto de dados enquanto mantém o máximo de informações possível. O cada eixo resultante dessa análise é um vetor corresponde ao grau de variância dos dados em ordem crescente. Em nosso caso, a PC1 apresentou destaque em relação às outras e observamos que podemos selecionar até três princpais componentes para explicar a variância do nosso dataset. Dessa forma, a aplicação do PCA ajuda a evitar o overfitting do modelo.
</p>
</details>

<details><summary><b> Agrupamento (clustering) </b></summary>
<p align="justify"> O algoritmo de clustering é eficiente para exploração e análise de dados crus e não tabelados, pois agrupa os dados de acordo com suas similidades e diferenças, demonstrando assim o comportamento das diferentes atributos do dataset. Para isso, definimos os atributos e o número de clusters (avaliamos a quantidade adequada de clusters de acordo com a "curva do cotovelo") e plotamos para visualizar a relação entre os valores. 
</p>
</details>

<details><summary><b> Detecção de outliers </b></summary>
<p align="justify">
 É um método de detecção de valores anômalos (outliers) com base na avaliação dos valores de cada ponto de dados em relação aos valores dos dados vizinhos mais próximos. Definimos hiperparâmetros para indicar quantos vizinhos devem ser levados em consideração e plotamos a dispersão dos mesmos.
</p>
</details>

<p align="justify">
 Status do Projeto: Em desenvolvimento :warning:
