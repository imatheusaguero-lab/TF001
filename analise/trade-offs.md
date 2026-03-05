# Identificação de Trade-offs
## Trade-offs: Performance vs Custo de Infraestrutura
Decisão tomada:
Priorizar performance e baixa latência, mesmo com alto custo operacional.

Justificativa:
O Instagram atende bilhões de usuários e precisa entregar:
- Feed quase instantâneo
- Carregamento rápido de vídeos e imagens
- Respostas rápidas em interações (curtidas, comentários)

Para isso, utiliza:
- CDN distribuída globalmente
- Sistemas de cache agressivos
- Processamento distribuído
- Infraestrutura massiva em nuvem

Essa escolha aumenta significativamente o custo com:
- Servidores
- Armazenamento
- Transferência de dados
- Processamento de machine learning

Impacto:
- ✅ Melhor experiência do usuário
- ✅ Maior retenção e tempo de uso
- ❌ Alto custo operacional
- ❌ Dependência de infraestrutura altamente escalável

Esse trade-off faz sentido porque a receita do Instagram (anúncios) depende diretamente do engajamento e tempo de permanência.

## Trade-off: Personalização Algorítmica vs Transparência

### Decisão tomada:
Priorizar um feed altamente personalizado baseado em algoritmos complexos.

### Justificativa:
O feed não é cronológico. Ele é ranqueado com base em:
- Interações anteriores
- Tempo de visualização
- Engajamento
- Perfil comportamental

Isso exige:
- Coleta massiva de dados
- Processamento de comportamento em tempo real
- Modelos de machine learning

Por outro lado, isso reduz:
- Transparência sobre como o conteúdo é exibido
- Controle do usuário sobre o que vê

### Impacto:
- ✅ Maior engajamento
- ✅ Mais tempo na plataforma
- ❌ Questionamentos éticos
- ❌ Possíveis bolhas informacionais

Arquiteturalmente, isso implica forte dependência entre:
- Sistema de ranking
- Sistema de dados comportamentais
- Sistema de cache do feed

## Trade-off: Consistência vs Disponibilidade

### Decisão tomada:
Priorizar disponibilidade em vez de consistência imediata (modelo eventual consistency).

### Justificativa:
Em sistemas distribuídos de grande escala, garantir que todos os dados estejam 100% sincronizados em tempo real aumenta drasticamente:
- Latência
- Complexidade
- Custo

No Instagram:
- Uma curtida pode demorar milissegundos para aparecer para todos.
- Contadores podem apresentar pequenas inconsistências momentâneas.

Isso indica uso provável de:
- Replicação assíncrona
- Bancos NoSQL distribuídos
- Estratégias de cache

### Impacto:
- ✅ Sistema permanece disponível mesmo sob falhas
- ✅ Melhor escalabilidade global
- ❌ Pequenas inconsistências temporárias

Essa decisão é comum em arquiteturas distribuídas de larga escala.

## Trade-off: Segurança vs Usabilidade

### Decisão tomada:
Equilibrar proteção da conta com fluidez da experiência.

### Justificativa:
O Instagram implementa:
- Autenticação de dois fatores
- Alertas de login
- Verificação de identidade

Porém, exigir validações excessivas poderia:
- Aumentar abandono
- Reduzir engajamento

### Impacto:
✅ Proteção contra invasões
✅ Confiança do usuário
❌ Pequeno aumento de fricção no login

Arquiteturalmente, isso exige integração entre:
- Sistema de autenticação
- Sistema de detecção de risco
- Sistema de notificações