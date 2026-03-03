# Requisitos Não Funcionais

Os requisitos não funcionais definem como o sistema deve se comportar em relação à velocidade, segurança, estabilidade e capacidade de crescimento. Em uma plataforma do porte do Instagram, não basta apenas oferecer funcionalidades; o sistema precisa continuar rápido, estável e disponível mesmo com milhões de usuários conectados ao mesmo tempo.


## Desempenho e Consistência

- **Velocidade como prioridade:**  
  O feed precisa carregar rapidamente, os vídeos não podem travar e as interações devem responder quase de forma imediata. Uma navegação fluida é essencial para manter o usuário ativo na plataforma.

- **Consistência eventual:**  
  Informações como número de curtidas e comentários podem levar alguns segundos para atualizar. Isso acontece porque o sistema prioriza desempenho e disponibilidade em vez de garantir atualização instantânea de todos os dados.

- **Processamento em segundo plano:**  
  Algumas tarefas, como atualização de métricas e envio de notificações, são realizadas sem afetar diretamente a experiência principal do usuário.

- **Uso de múltiplos servidores:**  
  A carga é distribuída entre vários servidores para manter a rapidez mesmo em momentos de grande volume de acessos.

**Análise arquitetural:**  
Existe um trade-off entre consistência imediata e alto desempenho. A arquitetura da plataforma prioriza velocidade e disponibilidade, aceitando pequenos atrasos na atualização de dados para manter a experiência fluida.


## Escalabilidade e Disponibilidade

- **Crescimento conforme a demanda:**  
  Novos servidores podem ser adicionados conforme o número de usuários aumenta.

- **Distribuição de requisições:**  
  Os acessos são distribuídos entre diferentes servidores para evitar sobrecarga.

- **Funcionamento contínuo:**  
  A estrutura é organizada para que o sistema permaneça disponível mesmo diante de falhas técnicas em determinadas regiões.

**Análise arquitetural:**  
A arquitetura distribuída reduz riscos de indisponibilidade e elimina pontos únicos de falha, aumentando a confiabilidade do sistema.


## Segurança e Usabilidade

- **Proteção de dados:**  
  As informações dos usuários são protegidas por criptografia e mecanismos de segurança.

- **Autenticação em dois fatores:**  
  Adiciona uma camada extra de proteção contra acessos indevidos.

- **Interface simples e intuitiva:**  
  Apesar da complexidade interna, o usuário encontra uma navegação fácil e objetiva.

**Análise arquitetural:**  
A arquitetura busca equilíbrio entre segurança e experiência do usuário, garantindo proteção sem comprometer a simplicidade da interface.


## Manutenabilidade e Portabilidade

- **Sistema dividido em módulos:**  
  A separação em partes independentes facilita correções e atualizações.

- **Integração entre plataformas:**  
  O aplicativo mantém funcionamento semelhante em Android, iOS e versão web.

- **Atualizações contínuas:**  
  Melhorias podem ser implementadas sem interromper totalmente o serviço.

**Análise arquitetural:**  
A modularização favorece manutenção, evolução do sistema e adaptação a novas tecnologias, mantendo estabilidade ao longo do tempo.

Os requisitos não funcionais são fundamentais para sustentar a qualidade do Instagram. Eles garantem que o sistema seja rápido, confiável, seguro e preparado para crescer, mantendo a experiência do usuário mesmo diante de alta complexidade.