```markdown
# Aplicativo de Lista de Tarefas

## Visão Geral
Este é um aplicativo de Lista de Tarefas construído com Java e Spring Boot. 
Ele permite que os usuários criem, leiam, atualizem e excluam tarefas. 
O aplicativo usa uma API RESTful para gerenciar contas de usuários e tarefas.

## Funcionalidades
- Registro e autenticação de usuários
- Gerenciamento de tarefas (operações CRUD)
- Hashing de senhas com BCrypt
- Dockerizado para fácil implantação

## Tecnologias Utilizadas
- Java
- Spring Boot
- Maven
- Docker
- BCrypt para hashing de senhas

## Pré-requisitos
- Java 17
- Maven
- Docker

## Começando

### Clonar o Repositório
```sh
git clone https://github.com/linconvinicius/todolist.git
cd todolist
```

### Construir o Projeto
```
mvn clean install
```

### Executando o Aplicativo

#### Usando Maven
```sh
mvn spring-boot:run
```

#### Usando Docker
1. Construir a imagem Docker:
    ```sh
    docker build -t todolist-app .
    ```
2. Executar o container Docker:
    ```sh
    docker run -p 8080:8080 todolist-app
    ```

### Endpoints da API

#### Endpoints de Usuário
- `POST /users/` - Criar um novo usuário
    - Corpo da Requisição:
        ```json
        {
            "username": "string",
            "password": "string"
        }
        ```
    - Resposta:
        - `201 Created` se o usuário for criado com sucesso
        - `400 Bad Request` se o usuário já existir

#### Endpoints de Tarefa
- `GET /tasks/` - Obter todas as tarefas
- `POST /tasks/` - Criar uma nova tarefa
- `PUT /tasks/{id}` - Atualizar uma tarefa
- `DELETE /tasks/{id}` - Excluir uma tarefa

### Estrutura do Projeto
```
todolist
├── src
│   ├── main
│   │   ├── java
│   │   │   └── br
│   │   │       └── com
│   │   │           └── todolist
│   │   │               ├── todolist
│   │   │               │   ├── user
│   │   │               │   │   ├── UserController.java
│   │   │               │   │   ├── UserModel.java
│   │   │               │   │   └── UserRepository.java
│   │   │               │   └── task
│   │   │               │       ├── TaskController.java
│   │   │               │       ├── TaskModel.java
│   │   │               │       └── TaskRepository.java
│   │   └── resources
│   │       └── application.properties
├── Dockerfile
└── pom.xml
```

### Configuração
O aplicativo pode ser configurado usando o arquivo `application.properties` localizado no diretório `src/main/resources`.

### Dependências
O projeto utiliza as seguintes dependências:
- Spring Boot 
- Spring Data JPA
- H2 Database
- BCrypt
- Maven
