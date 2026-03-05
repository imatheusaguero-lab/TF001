# Proposta 1 – Maior Transparência e Controle do Algoritmo de Feed
## Problema Identificado
O feed do Instagram é altamente dependente de algoritmos de recomendação baseados em aprendizado de máquina.
Apesar de eficiente em gerar engajamento, ele apresenta:
- Baixa transparência sobre critérios de ranqueamento
- Formação de bolhas de conteúdo
- Redução do controle do usuário sobre o que consome
- Forte acoplamento entre sistema de ranking e sistema de dados comportamentais

Arquiteturalmente, o algoritmo atua como um “núcleo crítico” do sistema.

## Proposta de Solução
Implementar um mecanismo híbrido de feed configurável, permitindo ao usuário escolher entre:
- Feed 100% algorítmico (modelo atual)
- Feed cronológico
- Feed baseado em categorias selecionadas (ex: amigos, criadores, negócios)

## Alteração Arquitetural
- Introduzir uma camada de abstração no serviço de geração de feed
- Separar o mecanismo de ranking da lógica de entrega
- Criar múltiplos "strategies" de ranqueamento (Strategy Pattern arquitetural)

Isso reduziria o acoplamento entre:
- Algoritmo de ML
- Serviço de entrega do feed

## Benefícios Esperados
- Maior transparência e confiança
- Redução de críticas sobre manipulação algorítmica
- Melhor experiência personalizada
- Redução do risco regulatório

## Trade-offs da Proposta
- ❌ Maior complexidade arquitetural
- ❌ Aumento do custo computacional
- ❌ Possível redução do tempo médio de permanência
É uma melhoria estratégica, mas pode impactar receita publicitária.

# Proposta 2 – Arquitetura Orientada a Eventos para Interações

## Problema Identificado
O Instagram processa um volume extremamente alto de interações entre usuários, como:
- Curtidas
- Comentários
- Compartilhamentos
- Visualizações de conteúdo
- Seguimentos de perfis

Essas interações geram um fluxo massivo de atualizações que precisam ser processadas rapidamente por diversos sistemas, como:
- Atualização de contadores de curtidas
- Atualização do ranking do feed
- Sistemas de recomendação
- Sistemas de analytics
- Sistemas de notificação

Caso esse processamento seja feito de forma síncrona entre os serviços, isso pode gerar:
- Alto acoplamento entre microserviços
- Aumento de latência
- Gargalos de processamento
- Baixa escalabilidade

## Proposta de Solução:
Implementar uma arquitetura orientada a eventos (Event-Driven Architecture), na qual as interações dos usuários são publicadas como eventos em um sistema de mensageria distribuído.
Exemplo de evento:
- `like_created`
- `comment_created`
- `follow_created`
- `video_viewed`
Esses eventos seriam consumidos de forma assíncrona por diferentes serviços do sistema.

## Alteração Arquitetural
A arquitetura passaria a incluir:
- Um **Event Broker** (ex: Kafka-like ou Pub/Sub)
- Serviços produtores de eventos (serviço de interação do usuário)
- Serviços consumidores de eventos, como:
  - Serviço de recomendação
  - Serviço de analytics
  - Serviço de notificações
  - Serviço de atualização de métricas
Esse modelo reduz a comunicação direta entre serviços e permite que múltiplos sistemas reajam aos mesmos eventos.

## Benefícios Esperados
- Redução do acoplamento entre serviços
- Melhor escalabilidade horizontal
- Processamento assíncrono de grandes volumes de dados
- Maior flexibilidade para adicionar novos serviços consumidores de eventos
- Melhor suporte para sistemas de recomendação e analytics

## Trade-offs da Proposta
❌ Maior complexidade arquitetural  
❌ Necessidade de gerenciamento de filas e eventos  
❌ Possibilidade de inconsistências temporárias entre serviços

Mesmo com esses desafios, arquiteturas orientadas a eventos são amplamente utilizadas em sistemas distribuídos de grande escala.