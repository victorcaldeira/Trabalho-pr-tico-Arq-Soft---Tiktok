# Trabalho-pr-tico-Arq-Soft---Tiktok

•  Nome dos integrantes do grupo: Victor Menezes, Matheus Augusto
•  Sistema escolhido: TikTok
•  Link do projeto no GitHub: https://github.com/victorcaldeira/Trabalho-pr-tico-Arq-Soft---Tiktok




O TikTok é uma rede social que permite aos utilizadores criar, editar, compartilhar e descobrir vídeos curtos. Os vídeos podem ter entre 15 segundos e três minutos e podem incluir conteúdos como música, dança e dublagem. A plataforma oferece recursos para editar os vídeos, como filtros, legendas, trilha sonora, gifs e cortes. 



Caracterização do Sistema
Nicho de Mercado
O TikTok é uma plataforma de mídia social que atrai principalmente a geração Z e os millennials. Seu conteúdo é centrado em vídeos curtos, geralmente com temas de entretenimento, dança, comédia e desafios virais. A plataforma também é popular entre criadores de conteúdo, influenciadores e marcas que desejam alcançar um público jovem e engajado.

Número de Clientes
Com mais de 1 bilhão de downloads em todo o mundo, o TikTok possui uma vasta base de usuários ativos. Estima-se que o número de usuários mensais ultrapasse os 800 milhões, tornando-o uma das maiores plataformas de mídia social do mundo.

Número de Acessos Simultâneos
O TikTok experimenta picos significativos de acessos simultâneos durante eventos ao vivo, desafios virais e momentos de alta popularidade de determinados conteúdos. A infraestrutura do sistema é projetada para lidar com milhões de usuários ativos simultâneos, garantindo uma experiência estável e de baixa latência.

Requisitos de Segurança
Devido à natureza interativa da plataforma e à coleta de dados dos usuários, os requisitos de segurança são uma prioridade. O TikTok implementa medidas robustas de segurança, incluindo criptografia de dados, autenticação de dois fatores e monitoramento contínuo de atividades suspeitas para proteger a privacidade e a segurança dos usuários.

Escalabilidade
Para lidar com o rápido crescimento da base de usuários e o aumento do volume de conteúdo gerado diariamente, o TikTok investe em infraestrutura escalável e tecnologias de computação em nuvem. Isso permite que o sistema se expanda horizontalmente conforme necessário, mantendo a performance e a disponibilidade em alta demanda.

Integrações
O TikTok integra-se com uma variedade de plataformas e serviços externos, incluindo ferramentas de análise de dados, APIs de publicidade e parcerias com criadores de conteúdo e marcas. Essas integrações ampliam a funcionalidade da plataforma e proporcionam oportunidades de monetização para os usuários e parceiros.



Possíveis problemas arquiteturais:

Escalabilidade: Com milhões de usuários ativos simultaneamente, a capacidade do sistema para lidar com picos de tráfego é crucial. Se a arquitetura não for projetada para escalabilidade, pode resultar em falhas, lentidão ou até mesmo interrupções do serviço.

Latência: O TikTok é uma plataforma que requer tempos de resposta rápidos para proporcionar uma experiência de usuário fluida. Latências excessivas podem prejudicar a experiência do usuário, especialmente em recursos como streaming de vídeo ao vivo.

Armazenamento e recuperação de conteúdo: O TikTok lida com uma enorme quantidade de vídeos gerados pelos usuários. Problemas relacionados ao armazenamento eficiente e recuperação rápida desses vídeos podem surgir se a arquitetura de armazenamento não for otimizada.

Consistência de dados: Manter a consistência dos dados em uma plataforma onde milhões de usuários estão enviando e interagindo com conteúdo constantemente pode ser desafiador. Problemas como conflitos de dados e inconsistências podem surgir se os sistemas não forem adequadamente projetados para lidar com essas situações.

Segurança: A segurança é uma preocupação crítica para qualquer plataforma online, especialmente aquelas que lidam com dados pessoais e conteúdo gerado pelo usuário. Vazamentos de dados, violações de privacidade e ataques cibernéticos são algumas das ameaças que o TikTok pode enfrentar se não tiver medidas de segurança robustas em vigor.

Localização e distribuição geográfica: Como uma plataforma global, o TikTok precisa garantir uma distribuição eficiente do conteúdo para usuários em todo o mundo. Isso pode exigir arquiteturas de rede complexas para lidar com diferenças de latência e demanda em diferentes regiões.

Manutenção e atualização contínua: Com o crescimento e a evolução do TikTok, é essencial que a arquitetura seja facilmente mantida e atualizada para incorporar novos recursos, corrigir bugs e lidar com mudanças nas demandas dos usuários.



Arquitura do Sistema:

Aplicativos Móveis (iOS e Android):
O TikTok é acessado principalmente por meio de aplicativos móveis nativos que oferecem funcionalidades de gravação de vídeo, edição, navegação e interação com outros usuários.

Arquitetura Nativa de Aplicativos: Os aplicativos móveis são desenvolvidos nativamente para iOS e Android, utilizando linguagens como Swift para iOS e Kotlin/Java para Android.
Servidores de Backend:
Responsáveis pelo processamento de dados, gerenciamento de usuários, autenticação, recomendação de conteúdo e outras operações de back-end.

Arquitetura de Microserviços: O TikTok adotou uma arquitetura de microserviços para modularizar e escalar diferentes partes do sistema de forma independente.
Armazenamento de Dados:
O TikTok lida com enormes volumes de vídeos, metadados de usuário, informações de interação e outras informações.

Bancos de Dados Distribuídos: Utiliza sistemas de armazenamento escaláveis e de alta disponibilidade, como bancos de dados distribuídos (ex: Cassandra, MongoDB).
Sistemas de Arquivos Distribuídos: Para armazenar e acessar vídeos e outros arquivos de mídia.
Algoritmos de Recomendação:
Para personalizar a experiência do usuário, o TikTok emprega algoritmos sofisticados de recomendação que analisam o comportamento do usuário, preferências e tendências de conteúdo.

Big Data e Processamento em Tempo Real: Utiliza tecnologias como Apache Spark e Kafka para processar grandes volumes de dados e realizar análises em tempo real.
Rede de Distribuição de Conteúdo (CDN):
Para garantir uma entrega rápida e confiável de vídeos aos usuários em todo o mundo.

CDNs Globais: Utiliza CDNs globais para armazenar em cache e distribuir conteúdo de forma eficiente.

Serviços de Segurança:
Criptografia e Autenticação:
Utiliza técnicas avançadas de criptografia e autenticação para garantir a segurança dos dados do usuário.
Criptografia de Dados em Repouso e em Trânsito: Utiliza algoritmos de criptografia robustos para proteger os dados armazenados nos servidores (em repouso) e durante a transmissão entre o cliente e o servidor (em trânsito). Isso pode incluir algoritmos como AES (Advanced Encryption Standard) para criptografia simétrica e RSA (Rivest-Shamir-Adleman) para criptografia assimétrica.
Mecanismos de Autenticação Segura: Implementa mecanismos de autenticação segura, como OAuth 2.0, para garantir que apenas usuários autorizados tenham acesso aos dados e funcionalidades do TikTok. Isso ajuda a prevenir acesso não autorizado e proteger a privacidade dos usuários.
Gestão de Chaves Criptográficas: Gerencia de forma segura as chaves criptográficas utilizadas para criptografar e descriptografar os dados, garantindo que apenas usuários autorizados possam acessar as informações protegidas.
Medidas de Segurança Adicionais:
Implementa outras medidas de segurança para proteger dados do usuário, prevenir spam, moderar conteúdo e detectar atividades maliciosas.
Firewalls e Sistemas de Detecção de Intrusão (IDS): Utiliza firewalls e sistemas de detecção de intrusão para proteger os servidores contra ataques externos e atividades maliciosas.
Filtros de Spam e Moderação de Conteúdo: Implementa filtros de spam e técnicas de moderação de conteúdo para identificar e remover conteúdo inapropriado, protegendo os usuários de experiências negativas na plataforma.
Análise de Comportamento e Detecção de Anomalias: Utiliza técnicas de análise de comportamento e detecção de anomalias para identificar atividades suspeitas, como contas falsas, comportamento de spam ou tentativas de violação de segurança.
Requisitos Importantes:
Escalabilidade:
Arquitetura altamente escalável que pode dimensionar horizontalmente para lidar com a carga.
Desempenho:
Plataforma otimizada para proporcionar uma experiência de usuário fluida.
Personalização:
Capacidade de personalizar a experiência do usuário com base em seus interesses e comportamentos.
Segurança e Privacidade:
Medidas para proteger os usuários de exploração, spam e outros abusos.
Decisões de Projeto:
Microserviços: Modularização e escalabilidade com arquitetura de microserviços.
Uso de Cloud Computing: Utilização de serviços em nuvem para escalabilidade dinâmica e disponibilidade.
Tecnologias de Big Data: Utilização de tecnologias de Big Data para processamento de dados.
Machine Learning e IA: Investimento em algoritmos de aprendizado de máquina e inteligência artificial.
Histórico de Mudanças:
Expansão Global: Adaptação da arquitetura para lidar com aumento na diversidade de conteúdo e idiomas.
Melhorias de Desempenho: Otimização contínua do desempenho do sistema.
Ênfase na Segurança: Fortalecimento das medidas de segurança ao longo do tempo.
Integração de Novas Tecnologias: Avaliação e integração de novas tecnologias para aprimorar a arquitetura.
