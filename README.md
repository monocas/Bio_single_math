
</head>
<body>
    <h1>Autores</h1>
    <p>Monyque K. de Paula Silva, João Pedro Aroucha de Brito, Caio Eduardo Palatin</p>
<h1>Palavras-chave</h1>
<p>scRNA-seq; expressão gênica; Método de Leiden</p>

<h1>Resumo e Motivação</h1>
<p>O estudo de single-cells no intestino humano desempenha um papel crucial na compreensão da saúde e doença intestinal. A aplicação de técnicas de análise de células únicas e a integração de aprendizado de máquina na interpretação da expressão gênica e epigenética proporcionam uma abordagem abrangente e de alta resolução, que lança luz sobre a diversidade celular, dinâmica e regulação genética no intestino. Esses avanços têm o potencial de impulsionar o desenvolvimento de terapias mais direcionadas e eficazes para doenças intestinais, melhorando assim a qualidade de vida dos pacientes. Neste trabalho, aplicou-se métodos de redução de dimensionalidade, clusterização e métricas de análise de eficiência para determinação de genes que serão aplicados para o treinamento de uma rede neural categórica que determina o perfil da célula do intestino grosso e delgado dada a expressão gênica.</p>

<p>No corpo humano a maioria das células possuem o mesmo genoma, entretanto, a maneira como cada célula utiliza e expressa a informação deste reflete a atividade única de um subconjunto de genes. Os métodos tradicionais do sequenciamento só obtém a convolução de informações de muitas células, portanto, sendo incapazes de analisar um pequeno número de células, perdendo as características heterogênicas destas (Jovic et al., 2022).</p>

<p>O entendimento das características únicas da célula, permite a análise detalhada das funções e interações célula-célula, comutando na identificação de populações celulares raras mas funcionalmente importantes, células tumorais malignas dentro de uma massa tumoral e células imunológicas hiper-responsivas dentro de um grupo aparentemente homogêneo. O sequenciamento de RNA unicelular (scRNA-seq) é o método utilizado para análise da expressão gênica da célula de modo a determinar o estado, função e resposta celular em nível unicelular para mais de milhões de células em um único estudo, permitindo a classificação, distinção e caracterização de cada célula ao nível do transcriptoma (Haque et al., 2017).</p>

<p>No corpo humano a maioria das células possuem o mesmo genoma, entretanto, a maneira como cada célula utiliza e expressa a informação deste reflete a atividade única de um subconjunto de genes. Os métodos tradicionais do sequenciamento só obtém a convolução de informações de muitas células, portanto, sendo incapazes de analisar um pequeno número de células, perdendo as características heterogênicas destas (Jovic et al., 2022). 😮

<p>O entendimento das características únicas da célula, permite a análise detalhada das funções e interações célula-célula, comutando na identificação de populações celulares raras mas funcionalmente importantes, células tumorais malignas dentro de uma massa tumoral e células imunológicas hiper-responsivas dentro de um grupo aparentemente homogêneo. O sequenciamento de RNA unicelular (scRNA-seq) é o método utilizado para análise da expressão gênica da célula de modo a determinar o estado, função e resposta celular em nível unicelular para mais de milhões de células em um único estudo, permitindo a classificação, distinção e caracterização de cada célula ao nível do transcriptoma (Haque et al., 2017). 🧬

<p>Uma região de extremo interesse para análise unicelular é a do intestino, um órgão complexo que promove a digestão, a extração de nutrientes, atuação na vigilância imunológica ao ponto que mantém relações simbióticas críticas com a microbiota e compreende diferentes linhagens celulares no seu trato intestinal que se dobram em milhões de criptas e vilosidades (Hua et al., 2022). 🍽️

<p>Os estudos de scRNA-seq no intestino promoveram perspectivas na identificação de subtipos celulares raros e suas vias de sinalização, além de revelarem funções anteriormente inexploradas. De acordo com Ren et al. (2018), um método analítico para se identificar novos tipos e estados celulares é a clusterização, a qual busca agrupar diferentes tipos de células, representando seus estados funcionais, inferindo a sua potencial dinâmica celular. 🧐

<p>Em tratamento de dados de single-cells, o método mais utilizado para inferir a identidade de células semelhantes é o Método de Leiden, responsável por criar clusters levando em consideração o número de links entre células em um cluster vs o número geral esperado de links no conjunto de dados. 🧪

<p>Uma aplicação da clusterização é por meio de aprendizado semi supervisionado, responsável por incorporar informações anteriormente fornecidas, como rótulos de uma classe, no cluster para orientar o processo de agrupamento de modo a melhorar o seu desempenho (Cai et al., 2023). Aprimorando a clusterização e adaptando-a de modo a agrupar melhor os tipos celulares de células únicas e as expressões gênicas, obtemos parâmetros de dados que podem ser aplicados como inputs de modelos preditivos de redes neurais para a determinação de qual são as células únicas de acordo com a expressão genética. 📊

<p>Neste trabalho, iremos utilizar do aprendizado semi supervisionado para quantificação da eficiência do cluster do Método de Leiden para identificação do tipo celular encontrado nas células únicas do intestino humano, após este tratamento, quantifica-se os genes mais expressos em cada tipo celular e encontra-se os seus marcadores genéticos para posteriores aplicações em redes neurais. 🤓

<h1>Objetivos</h1>
  <ul>
      <li>Clusterização pelo Método de Leiden por aprendizado semi-supervisionado, quantificando sua acurácia em relação aos tipos celulares das células únicas do intestino grosso e delgado. 🧩</li>
      <li>Determinar os genes mais expressos em cada tipo celular para marcação gênica. 🧬</li>
      <li>Utilizar dos parâmetros de genes e marcadores gênicos como inputs para prever o tipo celular de acordo com a expressão gênica. 🧠</li>
   </ul>

<h1>Metodologia</h1>
<p>Os materiais e métodos aplicados neste trabalho dizem respeito a técnicas para redução da dimensionalidade e clusterização das informações obtidas, por fim, será realizado uma previsão dos tipos celulares das células de acordo com features anatômicas e antológicas. Os dados foram extraídos do banco do Tabula Sapiens (Consórcio Tabula Sapiens) que é um atlas humano de células únicas que contém informações unicelulares de órgãos com o controle individual para antecedentes genéticos, idade, ambiente e efeitos epigenéticos, o que possibilita uma análise detalhada e também comparativa dos tipos de células que são compartilhados entre os tecidos.</p>

<p>Neste grande conjunto de dados com mais de 500 mil células de 24 órgãos de 15 seres humanos normais diferentes, selecionou-se como escopo o intestino grosso e delgado que são compostas por cinco grandes regiões: duodeno, jejuno, íleo e cólon ascendente e sigmóide. Cada uma destas regiões teve de três a nove amostras coletadas de cada local, seguidas de amplificação e sequenciamento do gene 16S RNA ribossômico (rRNA), sendo o kit utilizado para a obtenção das informações o 10x 3’ v3 e o Smart-seq2. Os conjuntos de região do intestino podem ser observadas na Figura 1. 🧪</p>

<h2>Aproximação e projeção de variedade uniforme (UMAP) 🌐</h2>
<p>A redução de dimensionalidade de dados é uma técnica fundamental para o pré-processamento e visualização de dados em que se há a diminuição do número de variáveis (dimensões) de um conjunto de dados visando a menor perda de informações possíveis. Considerando que os datasets de single-cells nos fornecem milhares de contagem de expressão gênica por célula individual, torna-se essencial a utilização de um método que reduza sua dimensão ao ponto que preserva sua informação.</p>

<p>De acordo com McInnes et al. (2018), o Uniform Manifold Approximation and Projection (UMAP) é um algoritmo que utiliza transformações não-lineares com o objetivo de agrupar informações a partir da semelhança de seus componentes.</p>

<p>O algoritmo é baseado em três determinações a respeito do conjunto de dados: i) os dados são uniformemente distribuídos na variabilidade de Riemannian; ii) a métrica de Riemannian é localmente constante (ou pode ser aproximada); iii) a variabilidade é localmente conectada. Respeitada as suposições, o UMAP realiza a modelagem fuzzy topográfica por meio de dois passos importantes, sendo estes, a construção de um gráfico em dimensões altas seguida de uma etapa de otimização para encontrar o gráfico mais semelhante em dimensões inferiores (Dong e Moses, 2021).</p>

<h2>Método de Leiden 🕵️‍♂️</h2>
<p>O Método de Leiden ou Algoritmo Leiden é um método usado para detectar comunidades ou agrupamentos em redes complexas, especialmente em redes de dados biológicos, como redes de interações de proteínas ou redes de expressão gênica. Ele é uma variação do algoritmo Louvain, que é amplamente utilizado para a detecção de comunidades em redes.</p>

<p>A ideia principal do algoritmo Leiden é aprimorar a estabilidade e a interpretabilidade dos resultados da detecção de comunidades, introduzindo etapas de otimização adicionais e sendo útil quando se trata de detectar comunidades em redes de grande escala.</p>

<p>A primeira etapa é a inicialização, onde o algoritmo começa com uma atribuição inicial de nós das comunidades, "nós" referem-se aos pontos ou elementos individuais em uma rede. Os nós são representados por pontos (ou vértices) interconectados por arestas (ou ligações). Cada nó em uma rede pode representar entidades distintas, dependendo do contexto da análise. Geralmente, os nós são alocados aleatoriamente em comunidades ou com base em algum método de partição inicial.</p>

<p>A segunda etapa é o refinamento, onde o algoritmo começa a sua otimização, onde ele tenta melhorar a qualidade das comunidades encontradas. Ele percorre repetidamente os nós na rede e considera movê-los para outras comunidades vizinhas, se isso melhorar uma métrica de qualidade. A métrica de qualidade mais comum usada é a modularidade, que mede a densidade de conexões dentro de comunidades em comparação com as conexões entre comunidades.</p>

<p>Na terceira etapa, realiza-se otimizações locais até que não seja mais possível melhorar a qualidade da partição. Isso envolve a tentativa de mover cada nó para a comunidade vizinha que produz o maior aumento na qualidade.</p>

<p>A quarta etapa é a mais crítica do algoritmo Leiden que é a verificação da estabilidade da partição obtida. Ele verifica se a partição é estável, o que significa que não é sensível a pequenas perturbações na rede. Isso ajuda a evitar a criação de comunidades instáveis e superespecializadas.</p>

<p>A quinta é uma fusão de comunidades. Após a verificação da estabilidade, o algoritmo pode fundir comunidades que não são significativamente diferentes em termos de qualidade. Isso reduz o número de comunidades e melhora a interpretabilidade do resultado.</p>

<p>Na sexta etapa o algoritmo realiza uma convergência. O algoritmo continua a refinar e otimizar a partição até que uma convergência seja alcançada, e nenhum movimento adicional dos nós resulte em uma melhoria significativa na qualidade (V. A. Traag, 2019).</p>

<p>Em síntese, o funcionamento do Método de Leiden pode ser compreendido de acordo com o esquemático abordado na Figura 2, em que se há uma partição inicial em que cada nó tem sua própria comunidade e o algoritmo move os nós únicos de uma comunidade para outra até que encontre uma participação adequada.</p>

<h2>Aprendizado semi-supervisionado para clusters</h2>
<p>O aprendizado semi-supervisionado é uma ferramenta que treina um modelo por meio de uma pequena quantidade de dados rotulados e uma grande quantidade de dados não rotulados com o objetivo de que uma função possa prever com precisão a variável de saída com base nas variáveis de entrada. No contexto da clusterização, este aprendizado se distoa dos clusters convencionais que ignoram informações prévias dos dados ao ponto que promove um melhor treinamento e eficiência de agrupamento já que não se ignora as informações.</p>

<p>Tendo em vista essa concepção, podemos comparar com dados reais a eficiência do modelo de agrupamento utilizado. No estudo de células únicas, a análise do tipo celular é uma métrica de extremo interesse para categorizar a qual tecido a célula pertence, sua morfologia e as expressões gênicas que mais ocorrem naquele espaço, dada a relevância desse atributo, analisou-se a eficiência do Modelo de Leiden para agrupar as células enquanto o seu tipo celular por meio do aprendizado não-supervisionando utilizando o nosso conjunto de dados reais - já expressos no dataset pelo Consórcio Tabula Sapiens; com os dados previstos pelo algoritmo.</p>

<h2>Acurácia</h2>
<p>Propõe-se e estabelece-se uma métrica capaz de determinar a acurácia do método a fim de obter dados quantitativos com relação a sua eficácia na classificação correta dos dados de tipos celulares de ambas as bases de dados estudadas. Inicialmente foi necessária a definição de uma correlação entre os clusters formados pelo método e os dados reais de tipos celulares, para isso, foi feita uma análise de cada cluster formado, obtendo-se os valores reais para cada célula presente neste. Com os dados reais, pegou-se a moda destes dados como métrica para determinar a classificação para tal cluster, obtendo-se, desta forma, uma correlação entre cada agrupamento formado e qual dado real este seria referente.</p>

<p>Após a obtenção da classificação formada pelos clusters, buscou-se comparar os valores reais com os previstos de forma par a par, com isso, obtêm-se um valor numérico para o número de acertos do método, podendo este ser dividido pela quantidade total para determinar a acurácia do algoritmo em classificar os dados com relação aos tipos celulares.</p>

<h2>Resultados</h2>
<p>...</p>
</body>
</html>

