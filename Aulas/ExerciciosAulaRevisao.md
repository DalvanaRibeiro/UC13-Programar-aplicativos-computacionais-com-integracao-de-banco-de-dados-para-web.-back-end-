# 📝 Exercícios – Express.js (Rotas, HTTP, Req/Res, Status Codes e Middleware)

---

## 🟢 Exercício 1 – API de Tarefas

### Enunciado

Desenvolva uma API de **tarefas** utilizando **Node.js + Express + TypeScript**.

### Requisitos

1. Criar um **middleware global de log** que exiba no terminal o método HTTP e a URL de cada requisição.

2. Implementar a rota **GET `/tarefas`**:
   - Deve retornar todas as tarefas.
   - Deve aceitar a **query opcional** `concluida=true/false` para filtrar as tarefas.
   - Deve retornar o status **200 (OK)**.

3. Implementar a rota **GET `/tarefas/:id`**:
   - Deve buscar uma tarefa pelo **id** recebido via **params**.
   - Se a tarefa existir, retornar **200 (OK)**.
   - Se não existir, retornar **404 (Not Found)**.

4. Implementar a rota **POST `/tarefas`**:
   - Deve receber os dados via **body**.
   - O campo `titulo` é obrigatório.
   - A tarefa deve ser criada com `concluida=false` por padrão.
   - Se o campo `titulo` não for informado, retornar **400 (Bad Request)**.
   - Se a tarefa for criada com sucesso, retornar **201 (Created)**.

5. Criar um **middleware de validação** que verifique se o campo `titulo` foi informado:
   - Esse middleware deve ser aplicado **somente** na rota POST.

---

## 🟡 Exercício 2 – API de Produtos

### Enunciado

Desenvolva uma API de **produtos** utilizando **Node.js + Express + TypeScript**.

### Estrutura do Produto

- `id`
- `nome`
- `preco`
- `emEstoque`

### Requisitos

1. Criar um **middleware global de log**.

2. Implementar a rota **GET `/produtos`**:
   - Deve retornar todos os produtos.
   - Deve aceitar a **query opcional** `emEstoque=true/false` para filtrar os produtos.
   - Retornar **200 (OK)**.

3. Implementar a rota **GET `/produtos/:id`**:
   - Deve buscar um produto pelo **id** (params).
   - Retornar **200 (OK)** se existir.
   - Retornar **404 (Not Found)** se não existir.

4. Implementar a rota **POST `/produtos`**:
   - Deve receber `nome` e `preco` via **body**.
   - O campo `emEstoque` deve ser `true` por padrão.
   - Se `nome` ou `preco` não forem informados, retornar **400 (Bad Request)**.
   - Se criado com sucesso, retornar **201 (Created)**.

5. Criar um **middleware de validação** aplicado apenas na rota POST para verificar os dados obrigatórios.

---

## 🔴 Exercício 3 – API de Chamados (Helpdesk)

### Enunciado

Desenvolva uma API de **chamados de suporte (Helpdesk)** utilizando **Node.js + Express + TypeScript**.

### Estrutura do Chamado

- `id`
- `titulo`
- `prioridade` (baixa | media | alta)
- `status` (aberto | fechado)

### Requisitos

1. Criar um **middleware global de log**.

2. Implementar a rota **GET `/chamados`**:
   - Deve retornar todos os chamados.
   - Deve aceitar as **queries opcionais**:
     - `status=aberto/fechado`
     - `prioridade=baixa/media/alta`
   - Retornar **200 (OK)**.

3. Implementar a rota **GET `/chamados/:id`**:
   - Deve buscar um chamado pelo **id**.
   - Retornar **200 (OK)** se existir.
   - Retornar **404 (Not Found)** se não existir.

4. Implementar a rota **POST `/chamados`**:
   - Deve receber `titulo` e `prioridade` via **body**.
   - O campo `status` deve ser `"aberto"` por padrão.
   - Se a `prioridade` não for válida, retornar **400 (Bad Request)**.
   - Se criado com sucesso, retornar **201 (Created)**.

5. Criar um **middleware de validação** aplicado somente na rota POST para:
   - Validar se `titulo` foi informado.
   - Validar se `prioridade` possui um valor permitido.

---

## 📌 Conceitos avaliados

- Rotas REST
- Métodos HTTP
- `req.params`, `req.query`, `req.body`
- `res.status()` e `res.json()`
- Status Codes HTTP
- Middleware e `next()`
- Organização e boas práticas em APIs Express
