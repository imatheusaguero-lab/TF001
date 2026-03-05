# Requisitos Não Funcionais
Os requisitos não funcionais garantem que o sistema seja rápido, seguro, escalável e fácil de manter, mesmo com milhões de usuários simultâneos.

## Desempenho e Consistência
- Feed e vídeos devem carregar rápido  
- Interações precisam ser imediatas  
- Atualizações de curtidas/comentários podem ter atraso de segundos (consistência eventual)  
- Processos secundários (notificações, métricas) não devem afetar a experiência principal  
- Uso de múltiplos servidores para manter velocidade  
*Análise arquitetural:* Prioriza desempenho e disponibilidade, aceitando pequenos atrasos nos dados.

## Escalabilidade e Disponibilidade
- Adição de servidores conforme aumento de usuários  
- Balanceamento de requisições para evitar sobrecarga  
- Estrutura resiliente a falhas regionais  
*Análise arquitetural:* Arquitetura distribuída elimina pontos únicos de falha e garante alta confiabilidade.

## Segurança e Usabilidade
- Dados protegidos por criptografia  
- Autenticação em dois fatores  
- Interface simples e intuitiva  
*Análise arquitetural:* Equilíbrio entre segurança e experiência fluida para o usuário.

## Manutenabilidade e Portabilidade
- Sistema modular para facilitar correções e evoluções  
- Compatibilidade entre Android, iOS e web  
- Atualizações contínuas sem interrupção total do serviço  
*Análise arquitetural:* Modularização garante manutenção fácil e adaptação tecnológica sem comprometer