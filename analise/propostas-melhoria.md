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
- Isso reduziria o acoplamento entre:
- Algoritmo de ML
- Serviço de entrega do feed

## Benefícios Esperados
- Maior transparência e confiança
- Redução de críticas sobre manipulação algorítmica
- Melhor experiência personalizada
- Redução do risco regulatório

⚖️ Trade-offs da Proposta
- ❌ Maior complexidade arquitetural
- ❌ Aumento do custo computacional
- ❌ Possível redução do tempo médio de permanência
É uma melhoria estratégica, mas pode impactar receita publicitária.

# Proposta 2 – Arquitetura Unificada de Search & Discovery

## Problema Identificado
O sistema de busca não parece centralizado como principal ponto de descoberta, diferentemente de YouTube e TikTok.

Arquiteturalmente pode haver:
- Múltiplos mecanismos de indexação
- Diferentes pipelines de ranking
- Dependência forte do feed como mecanismo principal de retenção

## Proposta de Solução
Implementar uma Search Platform unificada, com:
- Indexação semântica (embedding + ML)
- Ranking contextual baseado em intenção
- Unificação de perfis, vídeos, hashtags e áudios em um único motor
- Autocomplete inteligente
- Sugestões preditivas

## Arquitetura
envolveria:
- Camada dedicada de Search Service
- Motor de indexação distribuído (ex: ElasticSearch-like)
- Pipeline de atualização near real-time
- Integração com sistema de recomendação

## Benefícios Esperados
- Aumento do tempo médio de uso
- Maior retenção
- Melhor descoberta orgânica de conteúdo
- Redução da dependência exclusiva do feed

⚖️ Trade-offs da Proposta
- ❌ Aumento significativo de custo computacional
- ❌ Maior complexidade na indexação de vídeos
- ❌ Maior processamento de dados comportamentais
- ❌ Risco de sobreposição com sistema de recomendação