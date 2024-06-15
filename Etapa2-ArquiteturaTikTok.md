<h1 align="center">Arquitetura do Sistema - TikTok</h1>

<h2>Descrição</h2>
TikTok é um aplicativo de compartilhamento de vídeos que permite aos usuários criar e compartilhar vídeos curtos. Ele impressiona os usuários com suas recomendações personalizadas feitas "para você" de forma precisa.
É altamente viciante e muito popular entre os jovens. Por trás disso, está impulsionado por tecnologias de inteligência artificial.

<h2>Arquiteturas do TikTok</h2>

A arquitetura do sistema de recomendação do TikTok inclui três componentes:

- __Big Data Framework__: Ponto de partida do sistema. Eles fornecem processamento de dados em tempo real, computação de dados e armazenamento de dados.
- __Machine Learning__: O cérebro por tras do sistema de recomendação. Uma variedade de algoritmos e técnicas de aprendizado de máquina e aprendizado profundo são aplicados para construir modelos e gerar recomendações que atendam às preferências individuais.
- __Microservices__: É a infraestrutura subjacente que permite que todo o sistema funcione de forma rápida e eficiente.

- <h2>Big Data Framework</h2>
A maioria dos dados vem dos smartphones dos usuários, incluindo o sistema operacional e os aplicativos instalados, entre outros. 
Mais importante ainda, o TikTok presta atenção especial aos registros de atividades dos usuários, como tempo de visualização, deslizes, curtidas, compartilhamentos e comentários. 
<p align="center">
  <img src="https://github.com/victorcaldeira/Trabalho-pr-tico-Arq-Soft---Tiktok/assets/85370066/dd441452-471e-4db5-ae4f-f9a6c334b76b">
</p>

Os registros são coletados e consolidados por meio de ferramentas como Flume e Scribe, antes de serem direcionados para a fila do Kafka. Em seguida, o Apache Storm entra em ação, processando fluxos de dados em tempo real, em conjunto com outros componentes do ecossistema Apache Hadoop.

O ecossistema Apache Hadoop é uma plataforma distribuída amplamente utilizada para processamento e armazenamento de dados em grande escala. Inclui o MapReduce, pioneiro no processamento distribuído de dados em lote. O YARN, por sua vez, oferece um framework para agendamento de tarefas e gerenciamento eficiente de recursos em clusters. O HDFS, outro componente-chave, é um sistema de arquivos distribuído, enquanto o HBase é um banco de dados escalável, ideal para armazenamento de dados estruturados em grandes tabelas. Além disso, o Hive proporciona uma infraestrutura de data warehouse, permitindo a sumarização e consulta eficiente de dados, enquanto o Zookeeper atua como um serviço de coordenação confiável e de alto desempenho.

À medida que a quantidade de dados cresce exponencialmente, torna-se essencial contar com frameworks de processamento em tempo real. O Apache Spark surge como a terceira geração desses frameworks, aprimorando significativamente o desempenho do MapReduce ao realizar processamento em memória. Recentemente, o TikTok adotou o Flink, uma quarta geração de frameworks projetada para processamento de streaming em tempo real de maneira nativa.

Além dos componentes do ecossistema Hadoop, diversos sistemas de banco de dados, como MySQL, MongoDB e outros, desempenham papéis importantes no cenário de armazenamento e processamento de dados.

<h2>Machine Learning</h2>

O TikTok conquistou sua reputação como o "algoritmo hiperpersonalizado e viciante" através de uma combinação sofisticada de processamento de dados e técnicas de aprendizado de máquina.

<p align="center">
  <img src="https://github.com/victorcaldeira/Trabalho-pr-tico-Arq-Soft---Tiktok/assets/85370066/c9410474-b4f2-4ce9-85e8-3a0cc6bf9d8e">
</p>

Após receber volumes significativos de dados, o TikTok inicia um processo crucial que envolve análise de conteúdo, criação de perfis de usuários e análise de contexto. Aqui, faz uso de frameworks de aprendizado profundo, como o TensorFlow, para conduzir tarefas de visão computacional e processamento de linguagem natural (PLN). A visão computacional decodifica imagens em fotos e vídeos, enquanto o PLN engloba tarefas como classificação, rotulagem e avaliação.

Dentro deste contexto, o TikTok emprega uma variedade de algoritmos clássicos de aprendizado de máquina, como regressão logística (LR), redes neurais convolucionais (CNN), redes neurais recorrentes (RNN) e árvores de decisão por impulso de gradiente (GBDT). Além disso, são aplicadas abordagens comuns de recomendação, como filtragem baseada em conteúdo (CBF), filtragem colaborativa (CF) e fatorização de matriz mais avançada (MF).

Para aprimorar sua compreensão dos usuários, o TikTok utiliza três "armas secretas":

1. **Plataforma experimental de algoritmos:** Engenheiros exploram combinações de múltiplos algoritmos de aprendizado de máquina, como LR e DNN. Em seguida, conduzem testes A/B para ajustes.

2. **Classificação e rotulagem extensivas:** Os modelos são construídos com base no comportamento dos usuários, considerando métricas como tempo de visualização, deslize, likes e compartilhamentos. O TikTok investe em uma ampla gama de recursos, vetores e categorias de usuário, constantemente expandindo essa base.

3. **Motor de feedback do usuário:** Modelos são continuamente atualizados com base no feedback dos usuários, refinando assim as previsões e recomendações. Uma plataforma de gerenciamento de experiência é construída em torno desse motor, permitindo melhorias contínuas.

Para enfrentar o desafio de inicialização a frio na recomendação, o TikTok adota a estratégia de recall, selecionando milhares de candidatos entre milhões de vídeos populares e de alta qualidade.

Além disso, parte do processamento de IA é movido para o lado do cliente, permitindo uma resposta mais rápida. Isso inclui treinamento em tempo real, modelagem e raciocínio em dispositivos de menor porte. Frameworks de aprendizado de máquina, como TensorFlow Lite ou ByteNN, são empregados nessa abordagem voltada para o cliente.

<h2>Microservices Architecture</h2>

<p align="center">
  <img src="https://github.com/victorcaldeira/Trabalho-pr-tico-Arq-Soft---Tiktok/assets/85370066/293766e4-d479-4f6a-83a1-4bbfc0b81c13">
</p>

O TikTok optou por uma infraestrutura nativa de nuvem, onde os componentes de recomendação, como criação de perfil de usuário, previsões, inicialização a frio, recall e motor de feedback do usuário, são disponibilizados como APIs. Esses serviços são hospedados em plataformas de nuvem como Amazon AWS e Microsoft Azure. Como resultado, a curadoria de vídeos é entregue aos usuários através da nuvem.

A tecnologia de containerização baseada em Kubernetes é empregada pelo TikTok. O Kubernetes, um orquestrador de contêineres, automatiza o ciclo de vida da aplicação. Para facilitar os deployments de fluxos de trabalho de aprendizado de máquina no Kubernetes, é utilizado o Kubeflow.

Como parte do stack nativo de nuvem, o TikTok utiliza o service mesh para gerenciar a comunicação entre diferentes partes da aplicação. Esta ferramenta controla como os dados são compartilhados entre os serviços, inserindo recursos ou serviços nas camadas da plataforma em vez da camada de aplicação.

Devido à necessidade de alta concorrência, os serviços são desenvolvidos utilizando a linguagem Go e gRPC. O Go se tornou a linguagem dominante no TikTok devido ao seu suporte integrado para rede e concorrência. O gRPC é um framework eficiente de Controle de Procedimento Remoto utilizado para construir e conectar serviços.

O TikTok destaca-se por desenvolver ferramentas internas para maximizar o desempenho em nível de sistema. O ByteMesh é uma versão aprimorada do Service Mesh, o KiteX é um framework Golang gRPC de alto desempenho e o Sonic é uma biblioteca Golang JSON aprimorada. Outras ferramentas e sistemas internos incluem servidores de parâmetros, ByteNN e abuso.

Como mencionado por Xiang Liang, principal de aprendizado de máquina do TikTok, a infraestrutura subjacente muitas vezes é mais importante do que os próprios algoritmos. Isso destaca o compromisso do TikTok em fornecer a melhor experiência possível aos usuários, investindo em uma infraestrutura robusta e eficiente.

<h2>Arquitetura de Algoritmos do TikTok</h2>

O TikTok é impulsionado por algoritmos considerados fundamentais para as operações da ByteDance. Estes algoritmos são tão essenciais que a empresa preferiria encerrar o aplicativo a vendê-lo. Eles são a base do sucesso global do TikTok, não apenas por sua sofisticação técnica, mas também por sua capacidade de trabalhar em harmonia com o formato de vídeo curto característico do aplicativo.

Enquanto outras plataformas sociais tradicionais, como Facebook e Instagram, se concentram em conectar usuários através de conexões sociais, o TikTok adotou uma abordagem diferente. Em vez disso, seu algoritmo é baseado em "sinais de interesse" dos usuários, o que lhe permite oferecer uma experiência altamente personalizada e dinâmica.

A tecnologia de algoritmo do TikTok é particularmente eficaz devido ao formato de vídeo curto utilizado pela plataforma. Esse formato permite uma coleta de dados mais rápida sobre as preferências dos usuários em comparação com plataformas tradicionais de vídeo, como YouTube. Além disso, o TikTok recomenda regularmente conteúdo fora dos interesses declarados dos usuários, uma estratégia essencial para manter a experiência do usuário envolvente e diversificada.

Outra estratégia eficaz do TikTok é incentivar os usuários a formarem grupos públicos por meio de hashtags. Isso não apenas promove o engajamento dos usuários, mas também fornece ao TikTok insights valiosos sobre o comportamento e interesses de seus membros.

Além disso, é importante observar que o algoritmo de recomendação do TikTok foi em grande parte inspirado pelo aplicativo irmão chinês Douyin. A capacidade do Douyin de marcar meticulosamente todo o conteúdo e usuários na plataforma foi uma parte fundamental na criação do algoritmo do TikTok.

Esses elementos combinados destacam não apenas a importância dos algoritmos para o sucesso do TikTok, mas também a complexidade e a sofisticação por trás de sua arquitetura de software

<h2>Referencias</h2>

- https://www.lavivienpost.com/how-tiktok-works-architecture-illustrated/

- https://www.reuters.com/technology/what-is-so-special-about-tiktoks-technology-2024-04-26/

- https://learningenglish.voanews.com/a/how-tiktok-s-technology-makes-the-service-popular/7593709.html

- https://intuji.com/exploring-tiktoks-technology-stack/
