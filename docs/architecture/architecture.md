## Arquitetura do Sistema – PyLadies Indicações

```text
            +----------------------+
            |   Frontend Web       |
            |----------------------|
            | React.js + Bootstrap |
            | (Single Page App)    |
            | - Componentes:       |
            |   - Cadastro         |
            |   - Busca            |
            |   - Consulta         |
            +----------+-----------+
                        |
                        v
            +----------------------+
            |       Backend        |
            |----------------------|
            | Spring Boot WebFlux  |
            | Java 21              |
            | - Handlers           |
            | - Repository         |
            | - Serviços internos  |
            +----------+-----------+
                        |
                        v
            +----------------------+
            |      MongoDB         |
            |----------------------|
            | Coleção Profissionais|
            +----------------------+
```

Integrações externas:
--------------------
- API de envio de email do Google (EmailService)
- API da Meta – WhatsApp Cloud API (WhatsAppService)

## 1. Descrição da Arquitetura

A arquitetura do sistema é **multicamadas**, organizada para separar responsabilidades entre frontend, backend, banco de dados e integrações externas.  
O frontend é uma **Single Page Application (SPA)**, responsiva para dispositivos móveis, enquanto o backend é desenvolvido em **Spring Boot WebFlux (Java 21)**, garantindo escalabilidade e reatividade.  
O MongoDB é utilizado como banco de dados NoSQL para armazenar profissionais, registradores e histórico de notificações.  

---

## 2. Padrões Arquiteturais Utilizados

- **MVC (Model-View-Controller)**: separação entre camada de apresentação, lógica de negócio e persistência  
- **Repository Pattern**: abstração do acesso ao banco de dados  
- **Service Layer**: encapsulamento de integrações externas (email e WhatsApp)  
- **Single Page Application (SPA)**: frontend responsivo e dinâmico  

## 2. Componentes do Sistema

1. **Frontend Web (SPA)**  
   - React.js + Bootstrap  
   - Componentes internos para cadastro, busca e consulta de profissionais  
   - Responsivo para desktop e mobile  

2. **Backend (Spring Boot WebFlux)**  
   - Handlers: implementam lógica de negócio  
   - Repository: comunicação com o MongoDB  
   - Services internos: lógica de envio de notificações  

3. **Banco de Dados (MongoDB)**  
   - Coleção Profissionais    

4. **Integrações Externas**  
   - **EmailService**: API Google para envio de emails  
   - **WhatsAppService**: API Meta (WhatsApp Cloud API) para notificações  