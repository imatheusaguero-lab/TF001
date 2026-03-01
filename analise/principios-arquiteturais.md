# **Analise dos Principios Arquiteturais**
***
## **Separação de Responsabilidades**

**Módulos Identificados :**

1. Módulo do Usuário(Front-end)
- Aplicativos para android e IOS
- Versão Web 
- Feed,reels,stories,perfil

2. Módulo de Microserviços
- Serviço de usuários 
- Serviço de mídia
- Serviço de geração do Feed
- Serviço de pesquisa e Recomendação
- Serviço de mensagem(Direct)

3. Módulo de Armazenamento
- Armazenamento de fotos e videos.
- Banco de dados e metadados .
- Gerenciamento de dados.

4. Módulo de Segurança
- Autenticação de dois fatores.
- Proteção de conta e recuperação .
- Privacidade e Segurança do Perfil.

**Como estão divididas as responsabilidades:**

- A divisão das responsabilidades entre módulos do Instagram é separada em partes funcionais entre cliente e servidor.
- O módulo de usuário é responsável pela interface e a experiência do usuário na web e em aplicativos mobile, focando na renderização do feed,stories,reels,navegação e interação em tempo real. 
- O Módulo de Microserviços gerencia perfis, autenticação e informação do usuário, compila e personaliza o feed de cada usuário com base em suas atividades, curtidas e seguidores. É responsável pelo upload, processamento da mídia, armazenamento e entrega de fotos e videos. Gerencia a troca de mensagem em tempo real entre bilhões de usuários.
- O módulo de armazenamento gerencia informações como usuários, fotos , videos, comentários e interações. As informações estruturadas são armazenadas sobre o conteúdo, perfis e interações.
- O módulo de segurança é crucial para a segurança e privacidade do usuário, tendo autenticação de dois fatores, selfie de verificação, alertas de login e atividade de login.

**Exemplo**

O front-end não se conecta a cada microserviço individualmente. A arquitetura utiliza um intermediário, uma API para gerenciar as solicitações para um 'ponto de entrada', a API recebe o pedido e o distribui para o microserviço específico
(feed, usuário, mídia ). Com essa abordagem não é necessaário múltiplas chamadas de rede do cliente para o servidor e permite alterar e atualizar um microserviço sem prejudicar o front-end.

## **Coesão**

O instagram apresenta alta coesão pois a arquitetura é baseada em microserviços em vez de um único bloco de código. O sistema de feed é separado do sistema de stories, cada serviço foca em uma uníca tarefa funcional. Caso o sistema de curtida falhe o sistema de feed e stories iriam continuar funcionando.