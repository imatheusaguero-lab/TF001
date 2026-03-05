# TF001 - Análise Arquitetural: Instagram

## Alunos
- **Nome:** Matheus Santos Aguero, Rian do Prado Oliveira, Manuelly Businari Vilas Boas, Eduardo Oliveira Ceschielli Ferreira, Gabriel Hamzeh Rubião
- **RA:** 6326149, 6326066, 6326156, 6326249, 6126070
- **Curso:** Análise e Desenvolvimento de Sistemas

## Sistema Analisado
- **Nome:** Instagram
- **Categoria:** Rede Social
- **Plataforma:** Mobile, Web
- **Justificativa da Escolha:** O Instagram foi escolhido por ser uma rede social amplamente utilizada pelos integrantes do grupo, permitindo uma análise baseada na experiência real de uso da plataforma e na observação de suas funcionalidades.

---

# Estrutura da Análise

## 📋 Descrição do Sistema
- Funcionalidades principais
- Tipos de usuários
- Contexto de uso

## 🏗️ Princípios Arquiteturais
- Separação de responsabilidades
- Análise de coesão
- Avaliação de acoplamento

## ⚖️ Trade-offs Identificados
- Performance vs Custo de Infraestrutura
- Personalização Algorítmica vs Transparência
- Consistência vs Disponibilidade
- Segurança vs Usabilidade

## 📊 Requisitos Não Funcionais
- Desempenho
- Escalabilidade
- Disponibilidade
- Segurança
- Usabilidade
- Manutenabilidade
- Portabilidade

## 💡 Propostas de Melhoria
- Maior transparência e controle do algoritmo de feed
- Arquitetura orientada a eventos para processamento de interações

## Diagramas
- `diagramas/arquitetura-atual.png` — Representação da arquitetura atual do sistema (interpretação baseada na análise).
- `diagramas/arquitetura-proposta.png` — Arquitetura proposta considerando as melhorias sugeridas.

## Como Navegar
1. Leia a descrição do sistema em `analise/descricao-sistema.md`
2. Veja a análise dos princípios em `analise/principios-arquiteturais.md`
3. Confira os trade-offs em `analise/trade-offs.md`
4. Analise os requisitos em `analise/requisitos-nao-funcionais.md`
5. Veja as propostas em `analise/propostas-melhoria.md`

# Conclusões
A análise arquitetural do Instagram demonstra como sistemas de grande escala utilizam arquiteturas baseadas em microserviços para garantir escalabilidade, disponibilidade e alta performance.

A separação de responsabilidades permite que diferentes partes do sistema evoluam de forma independente, enquanto o baixo acoplamento entre serviços facilita a manutenção e a evolução da plataforma. Entretanto, alguns componentes críticos, como o sistema de recomendação do feed, apresentam dependências mais fortes devido à complexidade do processamento de dados comportamentais e algoritmos de machine learning.

Os trade-offs identificados demonstram que decisões arquiteturais em sistemas de grande escala envolvem equilíbrio entre fatores como performance, custo, transparência, consistência e usabilidade.

As propostas de melhoria apresentadas buscam aumentar a transparência do algoritmo e melhorar os mecanismos de descoberta de conteúdo, mantendo a escalabilidade e a experiência do usuário como prioridades arquiteturais.