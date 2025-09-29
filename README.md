# PyLadies Indicações

## Objetivo do Projeto
O projeto **PyLadies Indicações** tem como objetivo criar um **aplicativo multiplataforma** para cadastro, consulta e recomendação de profissionais e empreendimentos de mulheres. A solução visa **fortalecer a visibilidade de profissionais mulheres**, facilitar conexões e promover networking, independentemente de fazerem parte de uma comunidade específica.

Para o lançamento inicial, utilizaremos a **comunidade PyLadies Fortaleza** como ponto de divulgação, devido ao grupo ativo no WhatsApp com mais de 600 mulheres que frequentemente buscam indicações profissionais.

---

## Problema Abordado e Justificativa

Mulheres profissionais ainda enfrentam dificuldades para serem encontradas e recomendadas em suas áreas de atuação.  
A busca por profissionais mulheres é um desafio comum, especialmente em comunidades de tecnologia, onde muitas vezes a rede de contatos é limitada.  

O **PyLadies Indicações** surge para resolver esse problema, oferecendo uma plataforma que centraliza cadastros, facilita buscas e promove networking.  
A comunidade **PyLadies Fortaleza** foi escolhida como ponto de partida para impulsionar o projeto, devido ao seu grupo ativo no WhatsApp com mais de 600 mulheres interessadas em troca de indicações e contatos profissionais. Além de oferecer uma camada de confiabialidade, pois embora exista o LinkedIn para buscar profissionais, muitas mulheres buscam recomendações validadas por pessoas próximas e que façam parte da sua comunidade.

---

## Descrição Funcional da Solução
A aplicação permitirá:  
- **Cadastro completo de profissionais** com nome, área de atuação, contatos, descrição, link de portfólio e demais informações;  
- **Busca e consulta** de profissionais por área e nome; 
- **Notificações por email** para quem cadastra e para quem é cadastrado, usando a API de envio de email do Google;  
- **Integração com WhatsApp** via API da Meta, permitindo consultas rápidas e envio de notificações dentro do grupo;  
- **Interface web responsiva** para desktop e dispositivos móveis, desenvolvida com React.js + Bootstrap.

---

## Visão Geral da Arquitetura
A arquitetura planejada é **multicamadas**, dividida entre frontend, backend, banco de dados e serviços de integração externa.

**Componentes principais:**  
- **Frontend Web:** React.js + Bootstrap  
- **Backend:** Spring Boot WebFlux (Java 21)  
- **Banco de Dados:** MongoDB  
- **Integrações externas:**  
  - API da Meta (WhatsApp Bot)  
  - API de envio de email do Google
  
```text
+----------------+        +----------------+        +----------------+
|  Frontend Web  | <----> |    Backend     | <----> |    MongoDB     |
+----------------+        +----------------+        +----------------+
                                  |
                                  +-----> Email API (Google)
                                  |
                                  +-----> WhatsApp API (Meta)
```

## Lista de Tecnologias Propostas
- **Backend:** Java 21, Spring Boot WebFlux
- **Frontend Web:** React.js + Bootstrap 
- **Banco de Dados:** MongoDB
- **Testes:** JUnit
- **Integração de Email:** API Google
- **Integração WhatsApp:** API da Meta (WhatsApp Cloud API)
- **Controle de versão:** Git + GitHub

---

## Cronograma de Desenvolvimento – 1 Mês

| Semana | Atividade |
|--------|-----------|
| 1      | Criação da arquitetura; início do backend (endpoints principais) |
| 2      | Desenvolvimento do backend completo, integração com MongoDB, testes unitários (JUnit) e documentação inicial das APIs |
| 3      | Desenvolvimento do frontend web (telas de cadastro, busca e consulta), integração com backend; início da integração com WhatsApp (Meta API) e envio de emails (Google API) |
| 4      | Finalização do frontend web, testes finais, ajustes de UX, validação de notificações, refinamento de documentação e entrega |

## Integrantes da Equipe e Seus Papéis

- **Mikaele dos Santos Aguiar** – Backend e implementação do MongoDB   
- **[Nome do integrante 2]** – Frontend e integração com backend  
- **[Integrante 3]** – Integrações externas (email e WhatsApp)  
- **[Integrante 4]** – Testes unitários (JUnit) e documentação técnica  
- **[Integrante 5]** – Modelagem de banco de dados e diagrama ER; Contato com a comunidade PyLadies
- **[Integrante 6]** – Prototipagem da interface e UX/UI
