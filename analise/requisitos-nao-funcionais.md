# Requisitos Não Funcionais
Os requisitos não funcionais determinam como o sistema deve operar em termos de desempenho, escalabilidade, segurança e qualidade estrutural. Em uma plataforma do porte do Instagram, não é suficiente apenas executar funcionalidades; o sistema deve manter estabilidade, alta disponibilidade e desempenho mesmo com milhões de usuários ativos simultaneamente.

## Desempenho e Consistência

- **Velocidade como prioridade estratégica:**  
  O carregamento rápido do feed, reprodução fluida de vídeos e resposta imediata às interações são fatores críticos para retenção de usuários.

- **Consistência eventual:**  
  O sistema aceita que dados como curtidas e comentários possam apresentar pequenos atrasos na atualização. Essa decisão arquitetural prioriza disponibilidade e desempenho em detrimento da sincronização instantânea.

- **Processamento assíncrono:**  
  Operações secundárias (atualização de métricas, notificações e indexações) são executadas em segundo plano, evitando impacto direto na interface principal.

- **Arquitetura distribuída:**  
  A divisão da carga entre múltiplos servidores reduz latência e aumenta a capacidade de resposta.

**Análise arquitetural:**  
Há um trade-off claro entre consistência imediata e alta performance, optando-se por um modelo que favorece escalabilidade e experiência do usuário.


## Escalabilidade e Disponibilidade

- **Escalabilidade horizontal:**  
  A plataforma adiciona novos servidores conforme o crescimento do tráfego, evitando dependência de uma única máquina de grande porte.

- **Balanceamento de carga (Load Balancing):**  
  As requisições são distribuídas entre diferentes servidores para evitar sobrecarga.

- **Redundância geográfica:**  
  Data centers distribuídos garantem continuidade do serviço mesmo em caso de falhas regionais.

- **Alta disponibilidade (24/7):**  
  O sistema é projetado para operar continuamente, minimizando indisponibilidades.

**Análise arquitetural:**  
O modelo distribuído reduz pontos únicos de falha e aumenta a resiliência do sistema.


## Segurança e Usabilidade

- **Criptografia de dados:**  
  Protege informações sensíveis durante transmissão e armazenamento.

- **Autenticação em dois fatores (2FA):**  
  Camada adicional de proteção contra acessos não autorizados.

- **Defesa em profundidade:**  
  Implementação de múltiplas camadas de segurança para mitigar vulnerabilidades.

- **Separação entre backend e interface:**  
  A complexidade técnica é isolada no backend, preservando simplicidade na experiência do usuário.

**Análise arquitetural:**  
Existe equilíbrio entre robustez de segurança e facilidade de uso, evitando que mecanismos de proteção prejudiquem a experiência.


## Manutenabilidade e Portabilidade

- **Código modular e baixo acoplamento:**  
  Componentes independentes permitem atualizações sem comprometer outras partes do sistema.

- **APIs padronizadas:**  
  Facilitam integração entre serviços internos e externos.

- **Suporte multiplataforma (Android, iOS e Web):**  
  A arquitetura permite adaptação para diferentes dispositivos sem reconstrução completa.

- **Evolução contínua:**  
  Atualizações frequentes são implementadas sem interrupções totais do serviço.

**Análise arquitetural:**  
A modularização favorece manutenção, escalabilidade futura e adaptação tecnológica.

Entretanto, os **requisitos não funcionais** sustentam a confiabilidade e estabilidade do Instagram. Eles asseguram que o sistema seja estável, rápido, seguro e capaz de crescer sem perder qualidade. Sem eles, a complexidade da plataforma comprometeria diretamente a experiência do usuário.