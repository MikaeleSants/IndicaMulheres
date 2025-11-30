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
                                 
```

## Lista de Tecnologias Propostas
- **Backend:** Java 21, Spring Boot WebFlux
- **Frontend Web:** Java Script, CSS e HTML
- **Banco de Dados:** MongoDB
- **Testes:** JUnit (A etapa de testes foi incluida no build do deploy)
- **Integração de Email:** API Google
- **Controle de versão:** Git + GitHub
- **Plataforma de deploy:** Azure (back) e GitHub Pages (front)
- 
---

## Instruções para Teste

Para testar a aplicação, você pode utilizar:

### 🔹 **Frontend Web**
Acesse diretamente a versão publicada do site:

**[https://mikaelesants.github.io/IndicaMulheres/](https://mikaelesants.github.io/IndicaMulheres/)**  


### 🔹 **Backend API**
Utilize a collection do Postman disponível no repositório para testar os endpoints da API:

- **Collection Postman:** `https://.postman.co/workspace/My-Workspace~c62593ae-c8fc-4908-804c-540958815e2d/collection/40060547-ac291e7f-de69-4f6b-b524-54e39a2891a5?action=share&creator=40060547`
- **URL base da API:**  
  `https://indicacoespyladies-czh6d3gbfxhgabb3.canadacentral-01.azurewebsites.net`

Principais endpoints disponíveis:
- `GET /profissionais` – Lista todos os profissionais
- `GET /profissionais/nome/{nome}` – Busca por nome
- `GET /profissionais/area/{area}` – Busca por área
- `POST /profissionais` – Cadastro de profissional

Você pode importar a collection no Postman e realizar testes diretamente com os endpoints em produção.

---

## Justificativa de Mudanças

Durante o desenvolvimento e deploy, algumas mudanças foram necessárias para garantir o funcionamento da aplicação:

- O arquivo `script.js` foi movido para dentro da pasta `public`, pois o GitHub Pages só publica arquivos que estão dentro da pasta configurada no workflow. Essa mudança resolveu o erro 404 e garantiu que o frontend funcionasse corretamente.
- A interface frontend foi reestruturada para utilizar **HTML + CSS + JavaScript puro**, em vez de React.js, para facilitar a **manutenção futura** e permitir integração direta com o site oficial da PyLadies Fortaleza, que já utiliza essa stack.
- A funcionalidade de integração com a **API do WhatsApp da Meta** foi removida após conversa com a representante da comunidade, pois não há um número oficial da PyLadies Fortaleza para esse tipo de comunicação. A funcionalidade de envio de email foi mantida como canal principal de notificação.

---

## Cronograma de Desenvolvimento – 1 Mês

| Semana | Atividade                                                                                                                                                                  |
|--------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1      | Criação da arquitetura; início do backend (endpoints principais)                                                                                                           |
| 2      | Desenvolvimento do backend completo, integração com MongoDB, testes unitários (JUnit) e documentação inicial das APIs                                                      |
| 3      | Desenvolvimento do frontend web (telas de cadastro, busca e consulta), integração com backend; início da integração com WhatsApp (Meta API) e envio de emails (Google API) |
| 4      | Finalização do frontend web, testes finais, ajustes de UX, validação de notificações, refinamento de documentação e entrega                                                |

---

## Validação com Público-Alvo

O projeto **PyLadies Indicações** foi apresentado a uma representante da comunidade **PyLadies Fortaleza**.  
O feedback recebido destacou que o sistema está **bem estruturado e útil** para a comunidade. Foi solicitado **remover a integração com WhatsApp**, já que não existe um número oficial da comunidade para esse fim, e as demais funcionalidades foram consideradas adequadas.

A representante também demonstrou interesse em **adicionar o projeto ao site oficial da comunidade** quando a plataforma estiver pronta e enviou uma **sugestão de ajustes no frontend** para alinhar com o design que já está sendo construído para o site da PyLadies Fortaleza.

---

## Integrantes da Equipe e Seus Papéis

- **Mikaele dos Santos Aguiar** – Backend e implementação do MongoDB   
- **[]** – Frontend e integração com backend  
- **[]** – Integrações externas (email e WhatsApp)  
- **[]** – Testes unitários (JUnit) e documentação técnica  
- **[]** – Modelagem de banco de dados e diagrama ER; Contato com a comunidade PyLadies
- **[]** – Prototipagem da interface e UX/UI
