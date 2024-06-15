<h1 align="center">Arquitetura do Sistema de Recomendação - TikTok</h1>

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

Os dados de log são coletados e agregados através do Flume e Scribe. Eles são canalizados para a fila do Kafka. Em seguida, o Apache Storm processa fluxos de dados em tempo real com outros componentes do ecossistema Apache Hadoop.

O ecossistema Apache Hadoop é um sistema distribuído para processamento e armazenamento de dados. Isso inclui o MapReduce, a primeira geração de sistema de processamento de dados distribuído, que processa dados em paralelo com processamento em lote. 
O YARN é uma estrutura para agendamento de tarefas e gerenciamento de recursos de cluster. O HDFS é um sistema de arquivos distribuído. O HBase é um banco de dados distribuído escalável que suporta armazenamento de dados estruturados para grandes tabelas. 
O Hive é uma infraestrutura de data warehouse que fornece sumarização e consulta de dados. O Zookeeper é um serviço de coordenação de alto desempenho.

À medida que os volumes de dados crescem rapidamente, frameworks de processamento de dados em tempo real entram em cena. O Apache Spark é a terceira geração de framework que auxilia no processamento distribuído quase em tempo real para cargas de trabalho de big data. 
O Spark melhora o desempenho do MapReduce realizando o processamento na memória. Nos últimos anos, o TikTok aplicou o framework de quarta geração Flink, que é projetado para fazer o processamento de streaming em tempo real de forma nativa.

Os sistemas de banco de dados incluem MySQL, MongoDB e muitos outros.

<h2>Machine Learning</h2>

Este é o centro de como o TikTok ganhou o renomado título de "algoritmo hiperpersonalizado e viciante".

<p align="center">
  <img src="https://github.com/victorcaldeira/Trabalho-pr-tico-Arq-Soft---Tiktok/assets/85370066/c9410474-b4f2-4ce9-85e8-3a0cc6bf9d8e">
</p>

Após a entrada de vastos conjuntos de dados, o próximo passo é a análise de conteúdo, a criação de perfis de usuários e a análise de contexto. 
Frameworks de aprendizado profundo de redes neurais, como o TensorFlow, são utilizados para realizar visão computacional e processamento de linguagem natural (PLN). A visão computacional decifrará imagens com fotos e vídeos. 
O PLN inclui classificação, rotulagem e avaliações.

Alguns algoritmos clássicos de aprendizado de máquina são utilizados, incluindo regressão logística (LR), redes neurais convolucionais (CNN), redes neurais recorrentes (RNN) e árvores de decisão por impulso de gradiente (GBDT). 
São aplicadas abordagens comuns de recomendação, como filtragem baseada em conteúdo (CBF), filtragem colaborativa (CF) e fatorização de matriz mais avançada (MF).

As armas secretas que o TikTok utiliza para entender sua mente são:

1. Plataforma experimental de algoritmos: os engenheiros experimentam a combinação de múltiplos algoritmos de aprendizado de máquina, como LR e DNN. Em seguida, realizam testes (teste A/B) e fazem ajustes.

2. Classificação e rotulagem extensivas: Os modelos são baseados no envolvimento dos usuários, como tempo de visualização e deslize, além dos likes ou compartilhamentos comumente utilizados (não é o que você diz em público, mas o que você faz como reflexo do seu subconsciente diz mais sobre você). O número de recursos, vetores e categorias do usuário é maior do que a maioria dos sistemas de recomendação no mundo. E eles continuam adicionando mais.

3. Motor de feedback do usuário: Ele atualiza os modelos após obter feedback dos usuários em múltiplas iterações. A plataforma de gerenciamento de experiência é construída com base neste motor e, em última análise, melhora as previsões e recomendações.

Para resolver o problema de inicialização a frio na recomendação, é utilizada a estratégia de recall. Isso envolve a seleção de milhares de candidatos entre dezenas de milhões de vídeos que provaram ser populares e de alta qualidade.

Enquanto isso, parte do trabalho de IA foi transferida para o lado do cliente para uma resposta super rápida. Isso inclui treinamento em tempo real, modelagem e raciocínio em tamanhos menores realizados nos dispositivos. 
Frameworks de aprendizado de máquina, como TensorFlow Lite ou ByteNN, são utilizados no lado do cliente.

<h2>Microservices Architecture</h2>

O TikTok adotou uma infraestrutura nativa de nuvem. Os componentes de recomendação, como criação de perfil de usuário, previsões, inicialização a frio, recall e motor de feedback do usuário, estão sendo disponibilizados como APIs. 
Os serviços são hospedados na nuvem, como Amazon AWS e Microsoft Azure. Como resultado do sistema, a curadoria de vídeos será enviada aos usuários por meio da nuvem.

<p align="center">
  <img src="https://github.com/victorcaldeira/Trabalho-pr-tico-Arq-Soft---Tiktok/assets/85370066/293766e4-d479-4f6a-83a1-4bbfc0b81c13">
</p>

O TikTok emprega tecnologia de containerização baseada em Kubernetes. O Kubernetes é conhecido como um orquestrador de contêineres. Ele é o conjunto de ferramentas para automatizar o ciclo de vida da aplicação. 
O Kubeflow é dedicado a facilitar os deployments de fluxos de trabalho de aprendizado de máquina no Kubernetes.

Como parte do stack nativo de nuvem, o service mesh é outra ferramenta para lidar com a comunicação de serviço para serviço. Ele controla como diferentes partes de uma aplicação compartilham dados entre si. 
Ele insere recursos ou serviços nas camadas da plataforma, em vez da camada de aplicação.

Devido à necessidade de alta concorrência, os serviços são construídos com a linguagem Go e gRPC. No TikTok, Go se tornou a linguagem dominante no desenvolvimento de serviços por causa de seu bom suporte embutido para rede e concorrência. 
O gRPC é um framework de Controle de Procedimento Remoto para construir e conectar serviços de forma eficiente.

O sucesso do TikTok está em ir além para fornecer a melhor experiência do usuário possível. Eles desenvolvem ferramentas internas para maximizar o desempenho em um nível baixo (nível do sistema). 
Por exemplo, o ByteMesh é uma versão aprimorada do Service Mesh, o KiteX é um framework Golang gRPC de alto desempenho e o Sonic é uma biblioteca Golang JSON aprimorada. 
Outras ferramentas ou sistemas internos incluem servidores de parâmetros, ByteNN e abuso, para citar alguns.

Como disse Xiang Liang, principal de aprendizado de máquina do TikTok, às vezes a infraestrutura subjacente é mais importante do que os algoritmos acima.
