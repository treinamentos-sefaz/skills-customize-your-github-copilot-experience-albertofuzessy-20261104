# 📘 Assignment: Building REST APIs with FastAPI

## 🎯 Objective

Aprenda a criar uma API REST com FastAPI, definindo endpoints HTTP, validando dados e retornando respostas apropriadas. Ao final, você terá uma API para gerenciar tarefas e poderá testá-la pela documentação interativa do FastAPI.

## 📝 Tasks

### 🛠️ Configure a API e crie os primeiros endpoints

#### Descrição
Crie uma aplicação FastAPI e implemente endpoints simples para apresentar a API e informar se ela está disponível.

#### Requisitos
A aplicação deve:

- Instalar FastAPI e Uvicorn usando `python -m pip install fastapi uvicorn`
- Criar uma instância da aplicação FastAPI em `main.py`
- Implementar `GET /` com uma resposta JSON que identifique a API
- Implementar `GET /health` com uma resposta JSON indicando que a aplicação está ativa
- Iniciar localmente com `uvicorn main:app --reload` e exibir a documentação interativa em `/docs`

### 🛠️ Implemente leitura e criação de tarefas

#### Descrição
Modele uma tarefa e crie endpoints para listar, consultar e adicionar tarefas. Os dados podem ficar em uma lista ou dicionário em memória; não é necessário configurar um banco de dados.

#### Requisitos
A aplicação deve:

- Definir um modelo de dados para tarefas usando Pydantic, com título, descrição e estado de conclusão
- Atribuir um identificador único a cada tarefa criada
- Implementar `GET /tasks` para retornar todas as tarefas
- Implementar `GET /tasks/{task_id}` para retornar uma tarefa específica
- Implementar `POST /tasks` para criar uma tarefa e retornar o recurso criado com status HTTP `201`
- Retornar status HTTP `404` quando o identificador consultado não existir

### 🛠️ Atualize, remova e valide tarefas

#### Descrição
Complete as operações de gerenciamento de tarefas e verifique como a API responde a dados inválidos e recursos inexistentes.

#### Requisitos
A aplicação deve:

- Implementar `PUT /tasks/{task_id}` para atualizar uma tarefa existente
- Implementar `DELETE /tasks/{task_id}` para remover uma tarefa existente e retornar status HTTP `204`
- Retornar status HTTP `404` ao tentar atualizar ou remover uma tarefa inexistente
- Validar os dados recebidos com o modelo Pydantic e retornar os erros de validação do FastAPI
- Testar os endpoints em `/docs`, incluindo uma consulta a um identificador inexistente e o envio de dados inválidos
