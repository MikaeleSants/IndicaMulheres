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
- **Interface web responsiva** para desktop e dispositivos móveis, desenvolvida com React.js + Bootstrap.

---

## Visão Geral da Arquitetura
A arquitetura planejada é **multicamadas**, dividida entre frontend, backend, banco de dados e serviços de integração externa.

**Componentes principais:**  
- **Frontend Web:** React.js + Bootstrap  
- **Backend:** Spring Boot WebFlux (Java 21)  
- **Banco de Dados:** MongoDB  
- **Integrações externas:**   
  - API de envio de email do Google
  
```text
+----------------+        +----------------+        +----------------+
|  Frontend Web  | <----> |    Backend     | <----> |    MongoDB     |
+----------------+        +----------------+        +----------------+
                                  |
                                  +-----> Email API (Google)
                                 
```

## Lista de Tecnologias Propostas
- **Backend:** Java 21, Spring Boot WebFlux
- **Frontend Web:** React.js + Bootstrap 
- **Banco de Dados:** MongoDB
- **Testes:** JUnit
- **Integração de Email:** API Google
- **Controle de versão:** Git + GitHub

---
