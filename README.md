# Detecção de tumores cerebrais usando redes neurais convolucionais (CNN)
![brain](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/tac.gif)

## Objetivo
<p align="justify"> Centenas de milhares de pessoas são diagnosticados todo ano com tumores cerebrais. Um tumor cerebral ocorre quando células anormais se formam dentro do cérebro. Existem dois tipos principais de tumores: tumores cancerosos (malignos) e tumores benignos. Podendo estes tumores serem classificados em dois tipos: originados no próprio cérebro (tumores primários) ou vindo como metástase de outras partes do corpo (tumores secundários). Naturalmente independente da origem do tumor, eles podem causar muitos problemas de saúde para as pessoas. Usando métodos de imageamento como a ressonância magnética podemos identificar a presença de tumores. Esse tipo de trabalho é feito na maioria das vezes por profissionais médicos. Contudo erros de intepretação das imagens são comuns atrasando o diagnóstico. Então, um ferramenta que auxilie no diagnóstico terá, sem dúvida, impacto direto nesse campo médico. As redes neurais convolucionais (CNN) são poderosa ferramenta de reconhecimento e classificação de imagens. Logo neste trabalho usaremos imagens reais de ressonância magnética para treinar uma CNN de modo que esta seja capaz de fornecer uma alta acurácia no processo de diagnóstico de tumores cerebrais. </p>

<p align="justify"> O reconhecimento de imagem é um clássico problema de classificação, e as Redes Neurais Convolucionais possuem um alta desepenho para esse problema. O conceito da arquitetura da CNN é análogo ao  que encontramos na natureza. Em 1962, Hubel e Wiesel fizeram um experimento mostrando que alguns neurônios são ativados juntos quando expostos a algumas linhas ou curvas, gerando assim o reconhecimento visual. As CNN funcionam do mesmo modo filtrando os principais detalhes de uma imagem passando adiante paras próximas camadas e ativando os neurônios destas camadas.</p>

## Entradas dos dados
<p align="justify"> Vamos apresentar uma breve descrição da arquitetura da CNN. As entradas dos dados são matrizes tridimensionais, com altura e largura definidas pelas dimensões das imagens e a profundidade determinada geralmente pelos três canais RGB, como esquematizado na imagen abaixo.</p>

![max](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/rede2.png)
## Convoluções
<p align="justify"> As camadas de convoluções podem ser entendidas como pequenos filtros quadrados que varrem a imagens em busca dos detalhes mais importantes. O filtro têm dimensões ajustáveis que varrem a imagem em saltos (o chamado de stride). Este processo vai gerar um activation map. A profundidade da saída de uma convolução é igual a quantidade de filtros aplicados. Quanto mais profundas são as camadas das convoluções, mais detalhados são os traços capitados com o activation map. Temos que nos preocupar com padding que diz respeito ao controle das dimensões do output da camada de convolução, veja a figura abaixo. Para maiores detalhes veja o artigo </p>

[Understanding ConvNets (CNN)](https://medium.com/neuronio/understanding-convnets-cnn-712f2afe4dd3). 

![oi](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/convulu%C3%A7%C3%A3o.gif)

## Função de ativação
<p align="justify"> As funções de ativação tem o objetivo de tornar o sistema da rede não-linear, permitindo a aprendizagem dos principais aspectos dos dados. Temos vários tipos de funções de ativação, citando algumas como por exemplo temos sigmoid, tanh e softmax e Relu. No caso das CNN a função de ativação mais adequada é a Relu, devido ao fato apresentarem maior eficiência de computação.</p>

## Pooling
O pooling tem como função reduzir a complexidade da camada de convolução anterior. De modo equivalente a convolução, escolhemos um quadrado que varre toda a saída da camada anterior. Então resumimos toda a informação naquela região em um único número. O processo de resumo de toda a informação é o maxpooling, no qual apenas o maior número da unidade é passado para a saída. O pooling além de reduzir a complexidade da aprendizagem da rede também evita o overfitting. O esquema do maxpooling pode ser resumido na figura abaixo.

![pooling](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/pooling.gif)

## Fully connected
No final das camadas de convolução temos uma rede neural 'convencional', onde sua entrada é a saída da última camada e sua siada são N neurônios que representam o número de classes a serem identificadas.

## Criando o modelo CNN
<p align="justify"> Como  dito antes, temos  como objetivo construir um modelo de detecção de tumores cerebrais mediante a análise de imagens de ressonância magnética usando uma CNN. Uma vez que treinemos nosso modelo temos que avaliar se seu desempenho na classificação é satisfatório.</p>

 Para alcançar esse objetivo  crie um notebook para mostrar o carregamento dos dados a até a avaliação da métrica de desempenho do modelo. A base de dados usada para alimentar o modelo foi conjunto de mais 3700 imagens de ressonância magnética (MRI) e  um dataset .csv com múltiplas informações das imagens de MRI. Inclusive o dataset nos diz a classificação das imagens que indicam a presença de tumores (classe 1) e imagens que indicam ausência de tumores (classe 0). Uniremos as informações das classes com cada imagem. A base de dados pode ser encontrada no link [Extracted features for brain tumor](https://www.kaggle.com/jakeshbohaju/brain-tumor?select=Brain+Tumor). O código original do notebook esta em [Detecção de tumores cerebrais usando rede neural convolucional](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/Brain_detector.ipynb)

![01](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/01.png)

![02](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/02.png)

![03](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/03.png)

![04](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/04.png)

![05](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/05.png)

![06](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/06.png)

![07](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/07.png)

![08](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/08.png)

![09](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/09.png)

![10](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/10.png)

![11](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/11.png)

![12](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/12.png)

![13](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/13.png)

![14](https://github.com/RondinellyMorais/Deteccao-de-tumores-cerebrais-usando-rede-neural-convolucional/blob/master/imagens/14.png)
