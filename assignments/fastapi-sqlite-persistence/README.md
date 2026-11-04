# 📘 Assignment: FastAPI and SQLite Persistence

## 🎯 Objective

Amplie uma API REST criada com FastAPI para armazenar dados de forma persistente usando SQLite. Você praticará a criação de tabelas e operações SQL parametrizadas para que os dados continuem disponíveis após reiniciar a aplicação.

## 📝 Tasks

### 🛠️ Configure o banco de dados SQLite

#### Descrição
Prepare um banco de dados SQLite para armazenar as tarefas da API. Use o módulo `sqlite3` da biblioteca padrão do Python, sem instalar uma biblioteca adicional de banco de dados.

#### Requisitos
A aplicação deve:

- Criar ou abrir um arquivo de banco de dados chamado `tasks.db`
- Criar a tabela `tasks` automaticamente quando a aplicação iniciar, caso ela ainda não exista
- Definir colunas para identificador, título, descrição e estado de conclusão
- Usar um identificador inteiro com incremento automático como chave primária
- Abrir e fechar conexões com o banco de dados sem deixá-las em uso após cada operação

### 🛠️ Salve e consulte tarefas no banco

#### Descrição
Substitua o armazenamento temporário em memória da API por operações SQLite para criar, listar e consultar tarefas.

#### Requisitos
A aplicação deve:

- Implementar `POST /tasks` para inserir uma tarefa no SQLite e retornar a tarefa criada com seu identificador
- Implementar `GET /tasks` para retornar as tarefas armazenadas
- Implementar `GET /tasks/{task_id}` para consultar uma tarefa pelo identificador
- Usar consultas SQL parametrizadas para todos os valores recebidos pela API
- Retornar status HTTP `404` quando a tarefa solicitada não existir

### 🛠️ Atualize, remova e verifique a persistência

#### Descrição
Complete as operações de gerenciamento de tarefas no banco e confirme que os dados permanecem salvos depois que a aplicação é reiniciada.

#### Requisitos
A aplicação deve:

- Implementar `PUT /tasks/{task_id}` para atualizar uma tarefa existente no SQLite
- Implementar `DELETE /tasks/{task_id}` para remover uma tarefa existente do SQLite
- Retornar status HTTP `404` ao tentar atualizar ou remover uma tarefa inexistente
- Usar consultas SQL parametrizadas também nas operações de atualização e remoção
- Verificar em `/docs` que uma tarefa criada continua disponível após reiniciar a aplicação
