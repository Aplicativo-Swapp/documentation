# README - Arquitetura de Microserviços para Sistema de Economia Colaborativa

## Descrição Geral
Este projeto é uma plataforma de economia colaborativa que permite aos usuários trocarem habilidades e serviços sem transações financeiras. A solução é baseada em uma arquitetura de microserviços para garantir escalabilidade, modularidade e manutenção simplificada. Cada microserviço é projetado para gerenciar funcionalidades específicas e opera de forma independente, comunicando-se por meio de APIs.

## Componentes da Arquitetura de Microserviços

### 1. API Gateway
**Descrição**: Serve como o ponto central de entrada para todas as requisições de clientes (front-end ou aplicativos móveis). O API Gateway gerencia autenticação, autorização e roteamento, distribuindo as solicitações aos microserviços correspondentes. Este componente também garante a segurança da plataforma, simplificando o acesso aos serviços.

**Funções**:
- Roteamento de solicitações para microserviços específicos.
- Autenticação e autorização de usuários.
- Gestão de limite de taxa e monitoramento.

### 2. User Authentication and Profile Service
**Descrição**: Responsável pelo cadastro, autenticação e gerenciamento de perfis de usuários. Este serviço conecta-se a um banco de dados relacional (PostgreSQL) para armazenar dados de perfil, credenciais e outras informações pessoais.

**Funções**:
- Registro e login de usuários.
- Gestão de perfis (edição e visualização).
- Proteção de dados e validação de credenciais.

### 3. Skills and Exchange Service
**Descrição**: Gerencia listagens de habilidades, funcionalidades de busca e propostas de troca entre os usuários. Integra uma API de geolocalização para ajudar na busca por usuários próximos, e usa um banco de dados relacional para armazenar informações de habilidades e trocas.

**Funções**:
- Listagem e gerenciamento de habilidades.
- Busca e filtros por localização.
- Envio e recepção de propostas de troca.

### 4. Messaging and Notifications Service
**Descrição**: Suporta a troca de mensagens em tempo real e notificações entre usuários, utilizando WebSockets para comunicação instantânea. Armazena mensagens e históricos de conversas em um banco de dados NoSQL (MongoDB).

**Funções**:
- Sistema de mensagens em tempo real.
- Notificações de eventos e atualizações.
- Armazenamento de histórico de conversas.

### 5. Ratings and Reputation Service
**Descrição**: Gerencia avaliações e feedbacks após as trocas de habilidades, promovendo a confiança na plataforma. Este serviço armazena notas e comentários em um banco de dados relacional.

**Funções**:
- Recepção e armazenamento de avaliações.
- Cálculo de reputação de usuários.
- Exibição de feedback nos perfis.

### 6. Premium and Subscription Service
**Descrição**: Garante a gestão de funcionalidades premium, oferecendo recursos adicionais, como maior visibilidade nas buscas. As informações de assinaturas são mantidas em um banco de dados relacional.

**Funções**:
- Gestão de planos de assinatura e funcionalidades premium.
- Processamento de pagamentos (via serviços de terceiros).
- Monitoramento de status de assinatura.

### 7. Administration and Moderation Service
**Descrição**: Oferece controle administrativo da plataforma, incluindo a moderação de conteúdo e gerenciamento de usuários. É fundamental para garantir a segurança e a qualidade da plataforma.

**Funções**:
- Monitoramento de perfis e conteúdo.
- Aplicação de bloqueios temporários ou permanentes.
- Ferramentas de moderação para a equipe de administração.

## Ferramenta de Monitoramento e Containers
- **Prometheus e Grafana**: Utilizados para coleta de métricas e logs, ajudando na solução de problemas e monitoramento da performance dos microserviços.
- **Docker**: Facilita o gerenciamento de containers, garantindo que os microserviços sejam escaláveis e resilientes.

## Tecnologias Utilizadas
- **Linguagens e Frameworks**:
  - Backend: Spring Boot, Django.
  - Frontend: Vue.js.
- **Bancos de Dados**:
  - Relacional: PostgreSQL.
  - NoSQL: MongoDB.
- **Containers**: Docker.
- **Monitoramento e Logging**: Prometheus, Grafana.

---
