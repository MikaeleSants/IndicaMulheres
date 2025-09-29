# Especificação das APIs – PyLadies Indicações

## 1. Base URL

```
http://localhost:8080/profissionais
```

## 2. Endpoints

### 2.1 Listar todos os profissionais

* **Rota:** `/profissionais`
* **Método:** GET
* **Descrição:** Retorna todos os profissionais cadastrados.
* **Parâmetros:** Nenhum
* **Resposta (200 OK):**

### 2.2 Buscar profissional por nome

* **Rota:** `/profissionais/nome/{nome}`
* **Método:** GET
* **Descrição:** Retorna profissionais cujo nome contém o termo pesquisado.
* **Parâmetros:** `nome` (string, path)
* **Resposta (200 OK):** mesma estrutura do endpoint `/profissionais`

### 2.3 Buscar profissional por área

* **Rota:** `/profissionais/area/{area}`
* **Método:** GET
* **Descrição:** Retorna profissionais filtrados por área de atuação.
* **Parâmetros:** `area` (string, path)
* **Resposta (200 OK):** mesma estrutura do endpoint `/profissionais`

### 2.4 Cadastrar novo profissional

* **Rota:** `/profissionais`
* **Método:** POST
* **Descrição:** Cria um novo registro de profissional.
* **Corpo da requisição (JSON):**

```json
{
  "nome": "Ana Souza",
  "area_de_atuacao": "QA",
  "descricao": "Testadora de software",
  "email": "ana@email.com",
  "contato": "85988888888",
  "link_portfolio": "http://portfolio.com/ana",
  "link_redes_sociais": "http://linkedin.com/in/ana",
  "campos_personalizados": {
    "certificacao": "ISTQB",
    "experiencia": "3 anos"
  },
  "registrador_id": "usuario123"
}
```

* **Resposta (201 Created):**

```json
{
  "id": "456",
  "message": "Profissional cadastrado com sucesso"
}
```

### 2.5 Editar profissional

* **Rota:** `/profissionais/{id}`
* **Método:** PUT
* **Descrição:** Atualiza dados de um profissional existente.
* **Parâmetros:** `id` (string, path)
* **Corpo da requisição:** mesmo formato do POST
* **Resposta (200 OK):**

```json
{
  "id": "456",
  "message": "Profissional atualizado com sucesso"
}
```

### 2.6 Deletar profissional

* **Rota:** `/profissionais/{id}`
* **Método:** DELETE
* **Descrição:** Remove um profissional do banco de dados.
* **Parâmetros:** `id` (string, path)
* **Resposta (200 OK):**

```json
{
  "message": "Profissional deletado com sucesso"
}
```

### 2.7 Listar áreas registradas

* **Rota:** `/profissionais/areas`
* **Método:** GET
* **Descrição:** Retorna todas as áreas de atuação presentes nos cadastros.
* **Resposta (200 OK):**

```json
[
  "Desenvolvimento",
  "QA",
  "Dados",
  "UX/UI"
]
```
