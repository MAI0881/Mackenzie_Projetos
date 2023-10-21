# Sobre os Dados
Dimensões das imagens: 640x640 pixels
Classes incluídas: Bispo preto, Rei preto, Cavalo preto, Peão preto, Rainha preta, Torre preta, Bispo branco, Rei branco, Cavalo branco, Peão branco, Rainha branca e Torre branca. 
Quantidade de classes: 12
Quantidade de imagens por classe: 25

# Pré Processamento

Primeiramente, os dados foram devidamente rotulados e inseridos em um DataFrame onde cada imagem recebeu seus respectivos rótulos e um código identificador para cada rótulo. Esta organização permitiu uma fácil identificação e categorização das imagens de peças de xadrez, possibilitando uma manipulação mais eficiente dos dados.

Para preparar as imagens para treinamento, elas foram redimensionadas para um tamanho padrão de 160x160 pixels, mantendo a representação RGB, resultando em 3 canais de cores. Redimensionar as imagens para um tamanho padrão é crucial para garantir que elas possam ser processadas pela rede neural de forma uniforme.

Uma etapa fundamental no pré-processamento de dados para treinamento de modelos de aprendizado de máquina é a divisão do dataset em subconjuntos de treino, validação e teste. Inicialmente, o dataset foi dividido em conjuntos de treino e "test_val" com 20% dos dados reservados para este último. Posteriormente, esse subconjunto "test_val" foi novamente dividido em teste e validação, garantindo que exista uma separação adequada dos dados que ajudará a avaliar a performance do modelo em dados nunca antes vistos.

Além disso, foi aplicada a chamada técnica 'one-hot encoding' para os rótulos, transformando-os de rótulos categóricos em uma representação binária. Esta etapa é essencial para a classificação multiclasse, facilitando o treinamento e avaliação do modelo.

Outro passo importante no pré-processamento foi a implementação de técnicas de data augmentation. Isso envolveu a criação de versões modificadas das imagens de treino por meio de operações como rotação, zoom e flip horizontal. Esta etapa tem o objetivo de aumentar a diversidade dos dados de treinamento e, consequentemente, melhorar a robustez do modelo, permitindo que ele generalize melhor para novas imagens.

# Rede Neural Convolucional: VGG16

## Breve descrição da sua arquitetura:

Arquitetura da Rede: A VGG16 é composta por 16 camadas convolucionais e completamente conectadas. As camadas convolucionais são responsáveis por extrair características das imagens. Elas utilizam filtros (ou kernels) que são convoluídos com a imagem de entrada (ou com a saída da camada anterior) para produzir mapas de características. A arquitetura é bastante uniforme, consistindo principalmente em camadas convolucionais 3x3 com uma função de ativação ReLU seguida por camadas de pooling máximas 2x2. Elas são conectadas pois cada neurônio na camada está conectado a todos os neurônios na camada anterior e na camada seguinte, a função de ativação softmax é aplicada na saída desta camada para obter as probabilidades de classe.

Tamanho de Filtro Pequeno: O uso de filtros 3x3 nas camadas convolucionais é uma característica marcante da VGG pois é capaz de capturar padrões locais, como bordas, texturas e outras características pequenas, em uma imagem. O filtro é uma pequena matriz que é usada para extrair características de uma imagem, convoluindo-se (deslizando) através da imagem para produzir um mapa de características. A ideia por trás disso é que duas convoluções 3x3 em sequência com uma função de ativação ReLU têm um campo receptivo equivalente a uma convolução 5x5, mas com menos parâmetros treináveis. Isso torna o modelo mais eficiente em termos de computação. Garantindo assim a eficiência computacional trabalhando com menos parâmetros para aprender e atualizar durante o treinamento além de ajudar a melhorar a generalização do modelo para novos dados reduzindo o risco de overfitting.

Transferência de Aprendizado: A VGG16 é frequentemente usada como base para tarefas de transferência de aprendizado. É uma técnica em aprendizado de máquina onde um modelo desenvolvido para uma tarefa é reutilizado como ponto de partida para um modelo em uma segunda tarefa. É uma técnica popular em aprendizado profundo, pois pode treinar modelos com menos dados e de maneira mais eficiente. Os pesos pré-treinados da VGG16, treinados no conjunto de dados ImageNet, aprendendo a identificar diversas características e padrões visuais ao ser treinada para classificar imagens em milhares de categorias, capturam características de nível superior úteis em imagens gerais. Ao remover as camadas totalmente conectadas e substituí-las por camadas personalizadas, podemos ajustar a rede para tarefas específicas com um conjunto de dados menor. Além disso, ela aumenta a eficiência já que reduz a necessidade de treinar uma rede do zero. Pode ser adaptada para uma ampla variedade de tarefas de visão computacional, como classificação de imagens, detecção de objetos, segmentação de imagens.

## Detalhe do  Método

### São realizados os ajustes finos onde as camadas do modelo base são definidas como não treináveis, mantendo a transferência de aprendizado nessas e as demais camadas (densas a partir do final) são definidas como treináveis aprendendo os novos padrões;
### Foram armazenados os parâmetros para aplicação da técnica de Data Augmentation -  é um conceito fundado por técnicas computacionais com o objetivo de aumentar a quantidade de exemplos rotulados em um conjunto de dados e assim, melhorar os resultados obtidos [Taylor and Nitschke 2018, sendo realizado o espelhamento horizontal com rotação aleatória em entre -0.1 e +0.1 e zoom definido entre 90% e 110% do tamanho original da imagem; 
### O modelo é do tipo Sequential que é um tipo de modelo de rede neural usado para criar arquiteturas de redes neurais feedforward simples e lineares, em que a saída de uma camada serve como entrada para a próxima e onde os dados fluem em uma direção: da entrada para a saída. Neste modelo, você empilha camadas de forma que cada camada tem pesos que correspondem apenas à camada imediatamente anterior e à camada imediatamente seguinte, formando uma pilha linear de camadas.  Os dados fluem através das camadas do modelo sequencial em uma única direção, da camada de entrada para a camada de saída. Não há conexões de feedback ou loops na arquitetura, tornando-o um modelo feedforward;
### Foi ajustada a taxa de dropout (responsável por desativar aleatoriamente uma porcentagem das unidades de saída durante o treinamento);
### O pooling médio global foi calculado para reduzir as dimensões espaciais dos dados antes de passá-los para camadas densas para classificação ou regressão. O Pooling é utilizado para desamostrar os dados e reduzir a quantidade de dados a serem processados.
### A primeira camada densa foi ajustada com a quantidade de unidades da rede ativadas pela função ReLU que é responsável por decidir se cada neurônio deve ou não reagir à informação que está recebendo. A ReLU ajuda a mitigar o problema do desaparecimento do gradiente, que é comum em funções de ativação sigmoidais e tangentes hiperbólicas, especialmente em redes profundas.
### A última camada densa foi ajustada , com um número de unidades igual ao número de classes juntamente a função Softmax de classificação multiclasse. A função Softmax converte os logits em valores que podem ser interpretados como probabilidades, pois os valores de saída estão no intervalo (0, 1) e a soma de todas as saídas é 1.É comumente usada em problemas onde uma entrada pode pertencer a uma entre várias classes e A classe prevista pelo modelo é geralmente aquela que tem a maior probabilidade;
### No compilador o otimizador Adam - é um método de otimização utilizado para minimizar a função de perda durante o treinamento de um modelo,  com uma taxa final de aprendizado que será testada;
### Para cálculo do custo utilizaremos o cálculo de entropia cruzada baseada na técnica one hot encoding;
### Foi ajustada a quantidade de épocas - uma época é uma iteração completa do conjunto de dados de treinamento através do modelo durante o treinamento, que melhor funciona com a taxa de aprendizado determinada.

