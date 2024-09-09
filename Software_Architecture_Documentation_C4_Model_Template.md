# Documentação da Arquitetura de Software

## Visão Geral
Este documento descreve a arquitetura de software do sistema DiverTyr utilizando o C4 Model. A arquitetura é apresentada em quatro níveis: Contexto, Container, Componente e Código.

---
_**Instruções de Uso:**_

- _**Contexto**: Adicione uma visão geral de como o sistema interage com os usuários e sistemas externos._
- _**Containers**: Detalhe as principais partes do sistema, como a aplicação web, banco de dados, etc._
- _**Componentes**: Descreva a estrutura interna dos containers, detalhando os módulos e serviços principais._
- _**Código (Opcional)**: Use este nível para detalhar classes ou módulos críticos se necessário._
- _**Decisões Arquiteturais**: Documente as decisões tomadas e suas justificativas._
---

## 1. Diagrama de Contexto

### 1.1. Descrição do Diagrama de Contexto
O diagrama de contexto fornece uma visão geral de alto nível do sistema e suas interações com os atores externos.

- **Sistema:** DiverTyr
- **Atores Externos:** 
Usuário: Pessoas que acessam o sistema para planejar suas viagens.
API Externa de IA: Fornece sugestões de atividades, destinos e restaurantes.
Banco de Dados de Usuários e Itinerários: Armazena as informações de login e itinerários salvos.

### 1.2. Diagrama
![Diagrama de Contexto](![Captura de tela 2024-09-09 162346](https://github.com/user-attachments/assets/5af43f23-d6e6-4843-9df6-3e70ba07a59d)
)

### 1.3. Descrição dos Componentes
- **Atores Externos:** 
Usuário: Interage com o sistema para criar e salvar itinerários de viagem.
API Externa de IA: Um serviço externo que utiliza IA para gerar sugestões personalizadas de destinos e atividades.
Banco de Dados: Responsável por armazenar dados dos usuários, itinerários e preferências salvas.

- **Sistema:** 
Um aplicativo que ajuda os usuários a planejar suas viagens com recomendações de IA, fornecendo itinerários completos e permitindo o armazenamento de sugestões.

---

## 2. Diagrama de Container

### 2.1. Descrição do Diagrama de Container
O diagrama de container mostra os principais containers de software que compõem o sistema e como eles interagem entre si.

- **Containers Incluídos:** 
Aplicação Web (Frontend)
API de Backend (Node.js)
Banco de Dados (MongoDB)
API Externa de IA

### 2.2. Diagrama
![Diagrama de Container](path/para/diagrama-container.png)

### 2.3. Descrição dos Containers
- **Aplicação Web (Frontend):** Descrição do container, sua responsabilidade e tecnologias utilizadas.
  - **Tecnologias:** React, HTML, CSS.
  - **Responsabilidade:** Interface com o usuário, permitindo login, chat com IA e salvamento de itinerários.
  - **Interações:** Comunica-se com a API de backend para enviar e receber dados.

- **API de Backend (Node.js):** Descrição do container, sua responsabilidade e tecnologias utilizadas.
 - **Tecnologias:** Node.js, Express.
  - **Responsabilidade:** Recebe requisições do frontend, se comunica com a API externa de IA para sugestões e salva/recupera dados do banco de dados.
  -  **Interações:** Recebe requisições do frontend, se comunica com a API externa de IA para sugestões e salva/recupera dados do banco de dados.
---

## 3. Diagrama de Componente

### 3.1. Descrição do Diagrama de Componente
O diagrama de componente detalha a arquitetura interna de cada container, mostrando os componentes que o compõem e suas interações.

- **Container Focado:** Backend

### 3.2. Diagrama
![Diagrama de Componente](path/para/diagrama-componente.png)

### 3.3. Descrição dos Componentes
- **Componente de Autenticação:** Descrição do componente, sua responsabilidade e interações.
  - **Responsabilidade:** Gerencia login e controle de acesso dos usuários.
  - **Interações:** Se comunica com o banco de dados para validar as credenciais do usuário.
  - **Tecnologias:** JSON Web Token (JWT) para autenticação.
---


## 5. Decisões Arquiteturais

### 5.1. Decisões Importantes
Documente aqui as decisões arquiteturais importantes que foram tomadas durante o desenvolvimento do projeto, incluindo justificativas e impactos.

- **Decisão:** Utilizar MongoDB como banco de dados..
  - **Descrição:**  Armazenar informações dos usuários e itinerários de forma flexível.
  - **Justificativa:** MongoDB é ideal para dados não estruturados e oferece escalabilidade.
  - **Impacto:**  Facilita futuras expansões, mas exige conhecimento de bancos de dados NoSQL.

---

## 6. Considerações Finais

### 6.1. Padrões e Práticas
Liste os padrões arquiteturais e práticas recomendadas que foram seguidos durante o desenvolvimento da arquitetura.

- **Padrões:** Arquitetura RESTful, autenticação JWT.
- **Práticas:** Testes automatizados, Integração Contínua, Documentação de API.

### 6.2. Próximos Passos
Melhorar a interface do usuário com feedbacks em tempo real.
Explorar APIs de IA adicionais para aumentar a precisão das sugestões.

---

**Autores:** Ayrton Farias e João Nolasco  
**Data:** 06/09
