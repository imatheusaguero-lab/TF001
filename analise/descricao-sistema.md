# Descrição do Sistema

## Nome e Propósito
O Instagram é uma rede social focada no compartilhamento de imagens, vídeos e conteúdo efêmero.

## Principais Funcionalidades
- Publicação de fotos e vídeos
- Stories
- Reels
- Feed personalizado
- Curtidas e comentários
- Mensagens diretas
- Lives
- Anúncios patrocinados

## Tipos de Usuários
- Usuários comuns
- Criadores de conteúdo
- Empresas e marcas
- Anunciantes

## Contexto de Uso
- Mobile (principal)
- Web
- APIs externas para anúncios e analytics
O sistema possui múltiplas funcionalidades, organizadas em diferentes domínios de negócio:

1. 📸 Publicação de Conteúdo
    - Postagens de fotos e vídeos no feed
    - Carrossel de imagens
    - Reels (vídeos curtos com algoritmo de recomendação)
    - Stories (conteúdo temporário de 24h)
    - Transmissões ao vivo (Live)

2. 💬 Interação Social
    - Curtidas
    - Comentários
    - Compartilhamentos
    - Salvamentos
    - Mensagens diretas (Direct)
    - Reações rápidas em Stories

3. 🔍 Descoberta de Conteúdo
    - Página “Explorar”
    - Sistema de hashtags
    - Recomendações baseadas em algoritmo
    - Sugestões de perfis

4. 🛍️ Funcionalidades Comerciais
    - Instagram Shopping
    - Perfis comerciais
    - Anúncios patrocinados
    - Métricas e insights para criadores

5. ⚙️ Configurações e Gestão de Conta
    - Controle de privacidade
    - Bloqueio e restrição de usuários
    - Autenticação em dois fatores
    - Configuração de conta pública ou privada

A diversidade de funcionalidades indica que o sistema possui alta complexidade arquitetural e múltiplos módulos internos especializados.

## 1.3 Tipos de Usuários

O Instagram atende a bilhões de usuários globalmente, com diferentes perfis:
1. 👤 Usuário Comum
    - Consome conteúdo
    - Publica fotos pessoais
    - Interage com amigos

2. 🎥 Criador de Conteúdo / Influenciador
    - Produz conteúdo profissional
    - Monetiza audiência
    - Utiliza métricas e ferramentas de engajamento

3. 🏢 Empresas e Marcas
    - Divulgam produtos e serviços
    - Utilizam anúncios pagos
    - Integram loja ao perfil

4. 📢 Anunciantes
    - Criam campanhas publicitárias
    - Segmentam público
    - Monitoram desempenho
    - Essa segmentação implica requisitos arquiteturais distintos, especialmente em relação a escalabilidade, segurança, personalização e processamento de dados.

## 1.4 Contexto de Uso
O Instagram é um sistema multiplataforma, operando principalmente em:
- 📱 Aplicativo mobile (Android e iOS) — principal canal de uso
- 🌐 Aplicação Web (navegador)
