## Diagrama ER – PyLadies Indicações (Banco de Dados)

## 1. Modelo de Dados

O sistema utiliza **MongoDB**, um banco NoSQL, com uma única coleção para **Profissionais**
O modelo centraliza os dados do profissional, mantendo informações sobre quem realizou o cadastro (registrador) e possibilitando campos personalizados.

---

## 2. Descrição da Entidade

### Profissional
- Representa um profissional cadastrado na plataforma.  
- Campos principais: nome, área de atuação, contatos, links, campos personalizados e informações do registrador.  

---

## 3. Diagrama ER Simplificado

```text
+----------------------+
|    Profissional      |
+----------------------+
| id (PK)              |
| nome                 |
| area      |
| descricao            |
| email                |
| contato              |
| linkedIn             |
| link_redes_sociais   |
| campos_personalizados|
| registrador_nome     |
| registrador_email    |
| data_de_criação      |
+----------------------+
```
---

## 3. Dicionário de Dados

| Campo                   | Tipo     | Descrição                                                    |
|-------------------------|----------|--------------------------------------------------------------|
| `id`                    | String   | Identificador único do profissional                          |
| `nome`                  | String   | Nome completo do profissional                                |
| `area`                  | String   | Área de atuação (Desenvolvimento, QA, Dados, etc.)           |
| `descricao`             | String   | Breve descrição sobre o profissional                         |
| `email`                 | String   | Email de contato                                             |
| `contato`               | String   | Telefone ou WhatsApp                                         |
| `linkedIn  `            | String   | URL do linkedIn                                                      |
| `link_redes_sociais`    | String   | URL de perfis sociais (LinkedIn, GitHub, etc.)               |
| `campos_personalizados` | Object   | Campos extras definidos pelo registrador                     |
| `registrador_nome`      | String   | Nome de quem cadastrou o profissional (apenas para rastreio) |
| `registrador_email`     | String   | Email de quem cadastrou o profissional (apenas para rastreio) |
