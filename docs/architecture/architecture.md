## Arquitetura do Sistema – PyLadies Indicações

```text
            +----------------------+
            |   Frontend Web       |
            |----------------------|
            | HTML + CSS + JS      |
            | (Site Estático)      |
            | - Página Unica:      |
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

---

## 1. Descrição da Arquitetura

A arquitetura do sistema é **multicamadas**, organizada para separar responsabilidades entre frontend, backend, banco de dados e integrações externas.  
O frontend é um **site estático** construído com **HTML, CSS e JavaScript**, responsável pela interface de cadastro, busca e consulta de profissionais.  
O backend é desenvolvido em **Spring Boot WebFlux (Java 21)**, garantindo escalabilidade e reatividade.  
O MongoDB é utilizado como banco de dados NoSQL para armazenar informações de profissionais e registradores.

---

## 2. Padrões Arquiteturais Utilizados

- **MVC (Model-View-Controller)**: separação entre camada de apresentação, lógica de negócio e persistência
- **Repository Pattern**: abstração do acesso ao banco de dados
- **Service Layer**: encapsulamento de integrações externas (envio de email)
- **Arquitetura Estática no Frontend**: páginas HTML/CSS/JS servidas diretamente, sem framework SPA

---

## 3. Componentes do Sistema

1. **Frontend Web (Site Estático)**
    - HTML, CSS e JavaScript puro
    - Páginas para cadastro, busca e consulta de profissionais
    - Responsivo para desktop e mobile

2. **Backend (Spring Boot WebFlux)**
    - Handlers: implementam lógica de negócio e endpoints reativos
    - Repository: comunicação com o MongoDB
    - Services internos: lógica de envio de notificações por email

3. **Banco de Dados (MongoDB)**
    - Coleção `Profissionais` para armazenar dados de cadastro

4. **Integrações Externas**
    - **EmailService**: integração com API do Google para envio de emails

---