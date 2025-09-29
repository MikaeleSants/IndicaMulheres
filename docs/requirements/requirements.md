
# Documento de Requisitos

## 1. Requisitos Funcionais (RF)

### Cadastro de Profissionais

Permitir cadastrar profissionais e empreendimentos de mulheres com os seguintes campos:

- **Nome completo**
- **Área de atuação**
- **Contatos:** telefone, email, redes sociais
- **Descrição/resumo**
- **Link de portfólio ou site**
- **Outras informações relevantes**

**Registro do usuário que está cadastrando:**
- Armazenar o identificador de quem realizou o cadastro no banco de dados.
- Esta informação não deve ser exibida na interface; é apenas para controle interno e auditoria.

### Notificações

- Enviar email de confirmação para quem cadastrou e para quem foi cadastrado (API Google).
- Enviar notificações via WhatsApp através da API da Meta (bot) para cadastros e consultas realizadas.

### Interface Web Responsiva

- Disponibilizar layout responsivo que funcione bem em desktop e dispositivos móveis.
- Desenvolvido com **React.js** + **Bootstrap**.

### Administração Básica

- Permitir remoção de cadastros duplicados ou incorretos.

---

## 2. Requisitos Não-Funcionais (RNF)

### Performance

- Resposta rápida para buscas e cadastros.

### Escalabilidade

- Capacidade de incluir mais profissionais e integrar outras comunidades futuramente.

### Usabilidade

- Interface simples, clara e consistente.
- Compatível com diferentes navegadores e tamanhos de tela (desktop e mobile).

### Confiabilidade e Disponibilidade

- Sistema deve registrar logs de erros e permitir monitoramento de operações.
- Garantir que notificações (email e WhatsApp) sejam enviadas corretamente.

### Tecnologias

- **Backend:** Java 21 + Spring Boot WebFlux
- **Frontend:** React.js + Bootstrap
- **Banco de dados:** MongoDB
- **Testes:** JUnit
- **Integração:** API Google (email) e API da Meta (WhatsApp)
---

## 3. Regras de Negócio

1. Cada profissional deve ter **um único registro** por email.  
2. O registrador deve informar **nome e email** no cadastro, mas essa informação **não será exibida publicamente**.  
3. Campos personalizados podem ser adicionados por cada profissional, de acordo com necessidade.  
4. Notificações (email) só são enviadas **após o cadastro do profissional** e deve conter uma mensagem explicando do sistema.
5. Áreas de atuação devem ser consistentes e padronizadas; novos nomes são adicionados automaticamente ao listar áreas. 

## 4. Histórias de Usuário / Casos de Uso

- **HU01 – Cadastro de profissional**  
  Como registrador, quero cadastrar um profissional informando seus dados, para que ele fique disponível para consultas na plataforma.

- **HU02 – Consulta de profissionais**  
  Como usuário da plataforma, quero buscar profissionais por nome ou área, para encontrar indicações relevantes.

- **HU03 – Edição de profissional**  
  Como registrador, quero atualizar os dados de um profissional, para manter as informações corretas.

- **HU04 – Exclusão de profissional**  
  Como registrador, quero remover um profissional, caso o cadastro seja inválido ou desatualizado.

- **HU05 – Notificações**  
  Como registrador, quero que o profissional e eu recebamos notificações ao cadastrar um registro, para garantir que todos estão informados.

---

## 5. Perfis de Usuários

1. **Registrador**  
   - Responsável por cadastrar, editar e deletar profissionais.  
   - Preenche seu **nome e email** no cadastro.  

2. **Usuário da plataforma**  
   - Pode buscar profissionais por nome ou área de atuação.  
   - Não precisa se cadastrar.  