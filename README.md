
# Catálogo de Livros

Este projeto foi desenvolvido com o objetivo de colocar em prática meus conhecimentos em **Java, Spring Boot, desenvolvimento de APIs REST e operações CRUD**.

A aplicação consiste em uma API para gerenciamento de um catálogo de livros, permitindo cadastrar, listar, consultar, atualizar e excluir registros.

Durante o desenvolvimento, trabalhei com conceitos de programação orientada a objetos, persistência de dados e organização de uma aplicação backend utilizando o ecossistema Spring.

## Sobre o projeto

O sistema permite gerenciar livros por meio de requisições HTTP, utilizando o Spring Boot para processar as operações e o banco de dados H2 para armazenar as informações durante a execução.

Cada livro possui os seguintes atributos:

- ID
- Título
- Autor
- Ano de publicação

## Funcionalidades

- Cadastrar novos livros
- Listar os livros cadastrados
- Consultar um livro pelo identificador
- Atualizar as informações de um livro
- Excluir livros do catálogo
- Validar os dados recebidos nas operações de cadastro e atualização

## Tecnologias utilizadas

- **Java 21:** linguagem de programação
- **Spring Boot:** estrutura principal da aplicação
- **Spring Web MVC:** desenvolvimento das rotas REST
- **Spring Data JPA:** acesso e persistência dos dados
- **H2 Database:** banco de dados em memória
- **Maven:** gerenciamento de dependências e execução do projeto

## Estrutura do projeto

```text
catalogo-livros/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/
│       │       └── lanakarine/
│       │           └── catalogolivros/
│       │               ├── CatalogoLivrosApplication.java
│       │               ├── Livro.java
│       │               ├── LivroController.java
│       │               └── LivroRepository.java
│       └── resources/
│           └── application.properties
├── pom.xml
└── README.md
```

### Principais arquivos

- `CatalogoLivrosApplication.java`: inicialização da aplicação Spring Boot.
- `Livro.java`: representação da entidade Livro.
- `LivroController.java`: implementação das rotas e operações da API.
- `LivroRepository.java`: acesso aos dados utilizando Spring Data JPA.
- `application.properties`: configuração da aplicação e do banco H2.
- `pom.xml`: dependências e configurações do Maven.

## Operações CRUD

A API disponibiliza as seguintes rotas:

| Método | Rota | Funcionalidade |
|--------|------|----------------|
| POST | `/livros` | Cadastrar um livro |
| GET | `/livros` | Listar os livros cadastrados |
| GET | `/livros/{id}` | Consultar um livro pelo ID |
| PUT | `/livros/{id}` | Atualizar as informações de um livro |
| DELETE | `/livros/{id}` | Excluir um livro |

### Exemplo de cadastro

Para cadastrar um livro, envie uma requisição `POST` para:

```http
POST http://localhost:8080/livros
Content-Type: application/json
```

Com o seguinte corpo JSON:

```json
{
  "titulo": "Dom Casmurro",
  "autor": "Machado de Assis",
  "anoPublicacao": 1899
}
```

A API foi estruturada para armazenar o registro e retornar as informações do livro cadastrado, incluindo seu identificador.

### Consulta de livros

Para consultar todos os livros:

```http
GET http://localhost:8080/livros
```

Para consultar um livro específico:

```http
GET http://localhost:8080/livros/1
```

### Atualização de livros

Para atualizar um registro:

```http
PUT http://localhost:8080/livros/1
Content-Type: application/json
```

Exemplo de dados:

```json
{
  "titulo": "O Cortiço",
  "autor": "Aluísio Azevedo",
  "anoPublicacao": 1890
}
```

### Exclusão de livros

Para excluir um registro:

```http
DELETE http://localhost:8080/livros/1
```

## Como executar

### 1. Requisitos

Para executar o projeto localmente, é necessário ter instalado:

- Java 21
- Maven

### 2. Obter o projeto

Clone o repositório:

```bash
git clone https://github.com/lkarine03/catalogo-livros.git
```

Acesse a pasta:

```bash
cd catalogo-livros
```

Também é possível baixar os arquivos diretamente pelo GitHub.

### 3. Executar a aplicação

No terminal, execute:

```bash
mvn spring-boot:run
```

Com a aplicação iniciada, a API deverá ficar disponível em:

http://localhost:8080/livros

As requisições podem ser realizadas por ferramentas como Postman ou Insomnia.

## Banco de dados

O projeto utiliza o **H2 Database**, configurado para funcionar em memória.

Essa configuração permite utilizar um banco de dados sem precisar instalar e configurar um servidor MySQL ou PostgreSQL.

Os registros ficam disponíveis durante a execução da aplicação e são perdidos quando ela é encerrada.

## Aprendizados

A construção deste projeto foi voltada à prática dos seguintes conceitos:

- Programação orientada a objetos com Java
- Desenvolvimento de APIs REST com Spring Boot
- Implementação de operações CRUD
- Utilização de entidades com JPA
- Persistência de dados com Spring Data JPA
- Integração entre aplicação e banco de dados
- Manipulação de requisições e respostas HTTP
- Organização básica de uma aplicação backend

## Observações

Este é um projeto simples de estudos, desenvolvido para consolidar conhecimentos em Java e Spring Boot.

A aplicação foi estruturada para execução local e suas funcionalidades ainda precisam ser testadas nesse ambiente.
