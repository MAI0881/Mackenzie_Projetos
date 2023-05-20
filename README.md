# Análise Exploratória Amazon
Análise completa: https://www.notion.so/Vendas-Amazon-em-2023-48ccc4cea37b409ab11138e3adbb64a2?pvs=4

# **Objetivos do projeto**

<aside>
🎯 O objetivo do projeto consiste em realizar uma análise exploratória sobre os dados da empresa `Amazon` a fim de entender quais produtos mais alavancaram as vendas da empresa, que atualmente medida pela receita e capitalização de mercado, é a `maior vendedora virtual do mundo`, provedora e assistente de [IA](https://pt.wikipedia.org/wiki/Intelig%C3%AAncia_artificial), plataforma de transmissão ao vivo e plataforma de computação em nuvem.[[7]](https://pt.wikipedia.org/wiki/Amazon#cite_note-7)
 Além de ser a maior empresa de Internet em receita no mundo, o segundo maior empregador privado dos [Estados Unidos](https://pt.wikipedia.org/wiki/Estados_Unidos) e uma das empresas mais valiosas do mundo.[[8]](https://pt.wikipedia.org/wiki/Amazon#cite_note-8)

</aside>

🎲 3. Metadados

### Informações dos dados

| Nome | Informação |
| --- | --- |
| Tipo de Arquivo | CSV |
| Origem dos dados | Aberto |
| Sensibilidade | Não possui dados sensíveis |
| Validade | Gerados em 03/2023 - Poderão ser usados sempre para análises futuras |
| Proprietário | Lokesh Parab (Kaggle) |
| Restrições de uso | Dados abertos retirados do site da Amazon através de técnicas de Webscraping. Logo, existem algumas medidas e permissões que devem ser seguidas por quem extrai esses dados do site. |

### Descrição dos atributos

| Atributo | Tipo | Definição |
| --- | --- | --- |
| name | object | Nome do produto |
| main_category | object | Principal categoria a qual o produto pertence |
| sub_category | object | A subcategoria a qual o produto pertence |
| image | object | A imagem que o produto tem |
| link | object | Link do produto no site da Amazon |
| ratings | float | A nota dada para o produto segundo os usuários |
| no_of_ratings | float | A quantidade de avaliações que o produto recebeu |
| discount_price | float | Desconto que o produto recebeu |
| actual_price | float | Real preço do produto |


# 3. Dataset

[Amazon Products Sales Dataset 2023](https://www.kaggle.com/datasets/lokeshparab/amazon-products-dataset)

# Análise Exploratória - Vendas Amazon 2023


# 🙌  1 Apresentação da Amazon

Não é novidade que o comércio virtual revolucionou a maneira de se fazer compras e o impacto das lojas **`e-commerce`** na vida cotidiana é inegável. **Hoje, 74% das pessoas brasileiras preferem fazer compras online e 37% dessas pessoas costumam comprar com uma regularidade mensal** de acordo com um [levantamento daNZN Intelligence](https://www.ecommercebrasil.com.br/noticias/compra-online-preferencia-de-consumidores-brasileiros/#:~:text=Compra%20online%20%C3%A9%20prefer%C3%AAncia%20de%2074%25%20dos%20consumidores%20brasileiros,-3.3%2F5.0&text=Agilidade%2C%20comodidade%2C%20melhores%20pre%C3%A7os%20e%20condi%C3%A7%C3%B5es.&text=Segundo%20levantamento%20realizado%20pelo%20NZN,compras%20realizadas%20em%20lojas%20f%C3%ADsicas.).

Dentre as lojas e-commerce, uma que vem alcançando popularidade e ganhando espaço no mercado digital do país é a ****Amazon. `**Desde 2012`, a Amazon comercializa livros em solo nacional, mas foi em 2019 que a empresa deu um boom no mercado brasileiro**, colocando à disposição de clientes o catálogo próprio de produtos, ou seja, que seriam vendidos e entregues diretamente pela Amazon.

Em 2022 a **gigante do varejo** já contava com mais de **`1.500.000`** funcionários próprios e terceirizados.

- **Missão/visão e valores da Amazon**
    
    O site [Amazon.com](http://amazon.com/) foi lançado no ano de `**1995** **por Jeff Bezos**`, mesmo com muitas pessoas lhe dizendo que era difícil que esse novo modelo de negócios desse certo. O empresário não se intimidou e ao criar a sua companhia definiu para ela uma missão um tanto quanto ousada:
    
    “Ser a empresa com mais `**foco no cliente**` do mundo todo e se esforçar para oferecer os menores preços possíveis de maneira que os clientes consigam encontrar e descobrir tudo o que desejem comprar.”
    
    A missão continua a mesma, porém, o alcance da organização se expandiu, hoje em dia, a Amazon é uma empresa global que atende a milhões de clientes em todo o globo terrestre. Buscando atender a diferentes perfis de clientes que existem no mundo todo, a Amazon, criou novas soluções ao longo dos anos.
    
    A visão da Amazon está fortemente ligada ao desejo de Jeff Bezos de sempre **`inovar`** e atender as demandas criadas pelo mercado e pelos consumidores. Se em 1995 o criador da companhia revolucionou o mercado ao criar uma das **`primeiras lojas virtuais do mundo`**, atualmente, está sempre buscando as soluções mais inovadoras para atender aos desejos dos clientes e potenciais clientes da Amazon. **Um dos focos principais dessa criação de soluções é manter a melhor relação custo e benefício possível.**
    
- **Principais segmentos de atuação**
    
    ****Amazon Marketplace:****
    
    A companhia nasceu como uma loja digital de livros, mas ampliou suas atividades e se tornou a maior empresa de comércio eletrônico do mundo. Atualmente a **Amazon comercializa produtos de `todos os tipos`, incluindo brinquedos, eletrônicos, vestuários e acessórios.** Além disso, pequenas empresas confiam na Amazon como um parceiro para alcançar milhões de clientes por todo o mundo e que ajuda a fazer seus negócios crescerem. Ao mesmo tempo, oferece um local seguro para venderem seus produtos. **A Amazon é responsável por encontrar, engajar, cooperar e inovar em nome de `pequenas empresas` para ajudá-las a ter sucesso** dentro e fora do ambiente virtual da Amazon.
    
    ****Serviços e Dispositivos Amazon:****
    
    A Amazon apresentou o primeiro **`Kindle`** em 2007. Naquela época, oferecia 90 mil e-books e vendeu todo o estoque em cinco horas e meia após o lançamento. Desde então, expandiu e passou a ter a família de **e-readers mais vendidos do mundo**. Indo além do Kindle, lançaram os tablets Fire, feitos para trabalho e lazer com o sistema operacional Fire. **Para os amantes de mídia por `streaming`**, foram criados a **Amazon Fire TV**, o **Fire TV Stick** e a edição com comando por voz da Fire TV. Os dispositivos Fire TV vêm com acesso a 500 mil filmes, programas de TV e dezenas de milhares de canais, aplicativos e habilidades da **`Alexa`**. Recentemente, introduziram o **Amazon Echo e a Alexa, o serviço de voz que ativa o Echo e outros dispositivos para os clientes tocarem música, controlarem suas smart homes e obterem informações, notícias, previsão do tempo e muito mais usando apenas o comando de voz.**
    
    **Amazon Web Services:**
    
    O Amazon Web Services (AWS) **é uma plataforma segura de `serviços na nuvem` que oferece potência de computação, armazenamento de bancos de dados, entrega de conteúdo e outras funcionalidades para ajudar as empresas em sua distribuição e crescimento.** Milhões de clientes atualmente aproveitam os produtos e as soluções de nuvem do AWS para criarem aplicativos sofisticados com maior flexibilidade, capacidade de distribuição e confiança. Milhares de consumidores utilizam as diversas possibilidades de serviços do AWS. Isso acelerou o desenvolvimento do AWS em aprendizado de máquina, inteligência artificial, internet das coisas e computação sem servidores.
    
- **Market Share/posicionamento no mercado**
    
    De acordo com o site **[https://financesonline.com/amazon-statistics/](https://financesonline.com/amazon-statistics/)**, a Amazon é atualmente a **líder do comércio eletrônico nos Estados Unidos**, tendo uma participação de mercado significativa de `49,1%`. Isso significa que quase metade de todas as vendas on-line nos EUA é feita pela Amazon, tornando-a a empresa líder neste mercado.
    
    No entanto, a Amazon ocupa o **segundo lugar** em termos de volume de **mercadorias `globais**` vendidas, ficando atrás da Alibaba, uma empresa chinesa de comércio eletrônico. Apesar disso, a Amazon ainda é uma empresa globalmente reconhecida, com um alcance global significativo e uma ampla gama de produtos disponíveis para compra em seu site.
    
- **Iniciativas na área de Data Science**
    
    Como uma empresa líder em comércio eletrônico e tecnologia, a Amazon depende fortemente do uso de dados para impulsionar sua tomada de decisões e melhorar seus produtos e serviços. Algumas das áreas em que a Amazon utiliza Data Science incluem:
    
    - **Recomendação de produtos:** a Amazon usa algoritmos de **`aprendizado de máquina`** para **recomendar produtos aos clientes** com base em suas compras e pesquisas anteriores. Isso ajuda a melhorar a experiência do cliente e aumentar as vendas da empresa.
    - **Previsão de demanda:** a Amazon usa **`modelos de previsão`** de demanda para **gerenciar seus estoques** e garantir que os produtos estejam disponíveis quando os clientes precisam deles. Isso ajuda a reduzir os custos de armazenamento e melhorar a eficiência operacional da empresa.
    - **Detecção de fraudes:** a Amazon usa técnicas de **`análise de dados`** para **detectar e prevenir fraudes em suas transações de comércio eletrônico**. Isso ajuda a proteger os clientes e a empresa contra atividades fraudulentas.
    - **Análise de comentários de clientes:** a Amazon usa **`análise de sentimentos` para entender os comentários e as avaliações dos clientes** e melhorar seus produtos e serviços com base nessas informações.
    
    Além disso, a Amazon investe em pesquisa e desenvolvimento de tecnologias avançadas, incluindo inteligência artificial, machine learning e análise de dados, para aprimorar ainda mais suas iniciativas em Data Science.
    
    *Fontes:*
    
    [https://medium.com/dataflair/how-data-science-has-taken-amazon-on-top-360043e146ec](https://medium.com/dataflair/how-data-science-has-taken-amazon-on-top-360043e146ec)
    
    [https://aws.amazon.com/blogs/apn/amazon-fraud-detector-can-accelerate-how-ai-is-embedded-your-business/#:~:text=Amazon Fraud Detector is a,online activities and prevent them](https://aws.amazon.com/blogs/apn/amazon-fraud-detector-can-accelerate-how-ai-is-embedded-your-business/#:~:text=Amazon%20Fraud%20Detector%20is%20a,online%20activities%20and%20prevent%20them).
    
    [https://aws.amazon.com/what-is/forecast/](https://aws.amazon.com/what-is/forecast/)
    
    [https://aws.amazon.com/blogs/machine-learning/](https://aws.amazon.com/blogs/machine-learning/)
    
- **Trabalhos em destaque na área de Data Science**
    - **Amazon Go:** A loja sem caixas da Amazon é um exemplo de aplicação de tecnologias de Data Science. A Amazon Go usa uma combinação de **visão computacional, sensores e machine learning para `rastrear` os movimentos dos clientes e os produtos que eles retiram das prateleiras.** Essas informações são usadas para cobrar automaticamente os clientes pelos produtos que compraram, sem a necessidade de passar por um caixa.
    - **Amazon SageMaker:** A Amazon SageMaker é uma plataforma de aprendizado de máquina totalmente gerenciada que permite que os usuários criem, **`treinem`** e **`implementem`** modelos de aprendizado de máquina em grande escala. A plataforma inclui uma série de ferramentas de **pré-processamento de dados, algoritmos de aprendizado de máquina pré-configurados e recursos de infraestrutura de computação em nuvem escaláveis.**
    - **Amazon Alexa:** A assistente de voz da Amazon, Alexa, usa tecnologias de **processamento de linguagem natural e machine learning para entender e responder a perguntas dos usuários.** A Alexa também pode ser **`integrada`** a outros dispositivos e serviços, permitindo que os usuários controlem seus dispositivos domésticos inteligentes, peçam comida, comprem produtos e muito mais usando apenas comandos de voz.
    - **Amazon Prime Air:** O serviço de entrega por **`drone`** da Amazon é outro exemplo de aplicação de tecnologias de Data Science. Os drones **usam algoritmos de navegação autônoma para evitar obstáculos e encontrar o caminho mais rápido para o destino de entrega.** Os dados coletados pelos drones também podem ser usados para otimizar as rotas de entrega e melhorar a eficiência operacional da empresa.
    - **Amazon Rekognition:** O serviço de **`reconhecimento de imagens`** da Amazon **usa tecnologias de aprendizado de máquina para analisar e identificar objetos, pessoas e outras informações em imagens e vídeos.** O Rekognition pode ser usado para melhorar a segurança em eventos públicos, identificar suspeitos em imagens de câmeras de segurança e muito mais.

# ❓ Problema do Estudo

A análise exploratória tem como objetivo **`responder perguntas`** importantes do negócio para alcançar determinados objetivos. Para que essa análise seja eficaz, é necessário realizá-la de forma sistemática, seguindo um processo bem definido e organizado.

Para isso, é importante estabelecer com clareza quais são as perguntas que precisam ser respondidas, quais são os dados disponíveis e quais ferramentas e técnicas podem ser usadas para analisá-los.

Nesse processo, o **`pensamento computacional`** é uma habilidade fundamental, pois permite abordar o problema de forma estruturada e lógica, além de ajudar na criação de algoritmos para limpar e organizar os dados.

Ao seguir um processo sistemático de análise exploratória, utilizando o pensamento computacional, é possível coletar informações precisas e relevantes, facilitando a tomada de decisões informadas e eficazes no negócio.

- **Perguntas que pretendemos responder**
    1. Quais categorias de produtos têm maior e menor demanda?
    2. Como está a avaliação do meu público dentro da categoria mais popular?
    3. Os descontos estão correlacionados com a quantidade de vendas dos produtos?
    4. Quais categorias estão dentro da média de avaliações?
    5. Quais categorias estão abaixo da média de avaliações?
    6. Qual é a relação entre a quantidade de avaliações e a popularidade do produto?
- **Pensamento computacional para encontrar soluções**
    
    Podemos usar o pensamento computacional para responder essas perguntas através de uma abordagem sistemática de resolução de problemas que envolve algumas etapas como:
    
    1. Decomposição: dividir o problema em partes menores para entender cada aspecto e identificar as informações necessárias para respondê-lo. Por exemplo, podemos dividir o problema de identificar os produtos mais vendidos em categorias e subcategorias para analisá-los separadamente.
    2. Reconhecimento de Padrões: identificar padrões nos dados para descobrir insights ocultos e tendências que possam ajudar a responder às perguntas. Por exemplo, podemos usar técnicas de mineração de dados para identificar correlações entre as avaliações de produtos e seus preços ou descontos.
    3. Abstração: reduzir a complexidade dos dados para focar apenas nas informações relevantes para responder às perguntas. Por exemplo, podemos focar apenas nos produtos que têm uma alta relação entre a qualidade e o preço, ou naqueles que recebem descontos significativos.
    4. Algoritmos: criar uma sequência de passos lógicos e precisos para analisar os dados e extrair insights relevantes. Por exemplo, podemos criar um algoritmo que ordena os produtos por número de vendas e filtra aqueles que têm uma relação qualidade-preço adequada.
    5. Automação: criar processos automatizados para coletar e analisar dados em tempo real, permitindo uma resposta mais rápida às mudanças nas tendências do mercado. Por exemplo, podemos usar bots de rastreamento de preços para monitorar as mudanças de preços dos produtos e alertar a equipe de vendas para ajustar as estratégias de precificação.
    
    Em resumo, o pensamento computacional pode nos ajudar a abordar essas perguntas de maneira mais eficiente e eficaz, fornecendo insights valiosos que podem ser usados para melhorar os resultados do negócio na Amazon.
    
    # 📖 Glossário

[Dicionário de termos](https://www.notion.so/5f357f3a6100420b96d993c50fbe3fd3)
