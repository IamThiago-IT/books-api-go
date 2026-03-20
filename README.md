<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original-wordmark.svg" width="120" alt="Go Logo"/>
</p>

<h1 align="center">📚 Books API</h1>

<p align="center">
  <strong>API RESTful para gerenciamento de livros construída em Go</strong>
</p>

<p align="center">
  <a href="#-sobre">Sobre</a> •
  <a href="#-tecnologias">Tecnologias</a> •
  <a href="#-funcionalidades">Funcionalidades</a> •
  <a href="#-instalação">Instalação</a> •
  <a href="#-endpoints">Endpoints</a> •
  <a href="#-exemplos">Exemplos</a> •
  <a href="#-estrutura">Estrutura</a> •
  <a href="#-contribuição">Contribuição</a> •
  <a href="#-licença">Licença</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Go-1.21+-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go Version"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License"/>
  <img src="https://img.shields.io/badge/Status-Em%20Desenvolvimento-yellow?style=for-the-badge" alt="Status"/>
</p>

---

## 📖 Sobre

Uma API REST completa e elegante para gerenciamento de uma biblioteca pessoal de livros. Este projeto demonstra conceitos fundamentais de desenvolvimento backend em Go, incluindo roteamento com Gorilla Mux, manipulação de JSON e operações CRUD.

### 🎯 Motivação

Criar uma solução prática para organizar e gerenciar uma coleção de livros, permitindo cadastro, consulta, atualização e remoção de registros de forma simples e eficiente.

---

## 🚀 Tecnologias

| Tecnologia | Descrição |
|:----------:|-----------|
| ![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white) | Linguagem de programação principal |
| ![Gorilla Mux](https://img.shields.io/badge/Gorilla%20Mux-00ADD8?style=flat-square&logo=go&logoColor=white) | Router HTTP de alto desempenho |
| ![JSON](https://img.shields.io/badge/JSON-000000?style=flat-square&logo=json&logoColor=white) | Formato de serialização de dados |

---

## ✨ Funcionalidades

- ✅ **Criar** - Cadastrar novos livros na biblioteca
- ✅ **Listar** - Visualizar um livro específico ou todos os livros
- ✅ **Atualizar** - Editar informações de livros existentes
- ✅ **Deletar** - Remover livros da biblioteca

### 📋 Modelo de Dados

```json
{
  "id": 1,
  "titulo": "Nome do Livro",
  "categoria": "Categoria",
  "autor": "Nome do Autor",
  "sinopse": "Descrição do livro"
}
```

---

## 🔧 Instalação

### Pré-requisitos

- [Go](https://golang.org/dl/) 1.21 ou superior
- [Git](https://git-scm.com/)

### Passo a passo

```bash
# Clone o repositório
git clone https://github.com/IamThiago-IT/Go.git

# Acesse o diretório do projeto
cd Go

# Instale as dependências
go mod tidy

# Execute a aplicação
go run main.go
```

> 🎉 A API estará disponível em `http://localhost:8000`

---

## 📡 Endpoints

| Método | Endpoint | Descrição |
|:------:|----------|-----------|
| `POST` | `/livros` | Cadastra um novo livro |
| `GET` | `/livros` | Lista todos os livros |
| `GET` | `/livros/{id}` | Retorna um livro específico |
| `PUT` | `/livros/{id}` | Atualiza um livro existente |
| `DELETE` | `/livros/{id}` | Remove um livro |

---

## 💡 Exemplos

### 📗 Cadastrar um livro

```bash
curl -X POST http://localhost:8000/livros \
  -H "Content-Type: application/json" \
  -d '{
    "titulo": "O Senhor dos Anéis",
    "categoria": "Fantasia",
    "autor": "J.R.R. Tolkien",
    "sinopse": "Uma aventura épica na Terra Média."
  }'
```

**Resposta:**
```json
{
  "id": 1,
  "titulo": "O Senhor dos Anéis",
  "categoria": "Fantasia",
  "autor": "J.R.R. Tolkien",
  "sinopse": "Uma aventura épica na Terra Média."
}
```

### 📘 Listar todos os livros

```bash
curl -X GET http://localhost:8000/livros
```

### 📙 Buscar um livro específico

```bash
curl -X GET http://localhost:8000/livros/1
```

### 📕 Atualizar um livro

```bash
curl -X PUT http://localhost:8000/livros/1 \
  -H "Content-Type: application/json" \
  -d '{
    "titulo": "O Hobbit",
    "categoria": "Fantasia",
    "autor": "J.R.R. Tolkien",
    "sinopse": "A aventura de Bilbo Bolseiro."
  }'
```

### 🗑️ Deletar um livro

```bash
curl -X DELETE http://localhost:8000/livros/1
```

---

## 📁 Estrutura

```
📦 books-api-go
 ┣ 📂 cmd
 ┃ ┗ 📂 api
 ┃   ┗ 📜 main.go                 # Ponto de entrada da aplicação
 ┣ 📂 internal
 ┃ ┣ 📂 handler
 ┃ ┃ ┣ 📜 health_handler.go       # Handler para health check
 ┃ ┃ ┗ 📜 livro_handler.go        # Handlers HTTP para livros
 ┃ ┣ 📂 middleware
 ┃ ┃ ┣ 📜 cors.go                 # Middleware CORS
 ┃ ┃ ┗ 📜 logging.go              # Middleware de logging
 ┃ ┣ 📂 model
 ┃ ┃ ┗ 📜 livro.go                # Modelo de dados do livro
 ┃ ┣ 📂 repository
 ┃ ┃ ┗ 📜 livro_repository.go     # Camada de acesso a dados
 ┃ ┣ 📂 router
 ┃ ┃ ┗ 📜 router.go               # Configuração das rotas
 ┃ ┗ 📂 service
 ┃   ┗ 📜 livro_service.go        # Regras de negócio
 ┣ 📂 pkg
 ┃ ┗ 📂 response
 ┃   ┗ 📜 response.go             # Utilitários para respostas HTTP
 ┣ 📜 Dockerfile                  # Configuração Docker
 ┣ 📜 docker-compose.yml          # Configuração Docker Compose
 ┣ 📜 go.mod                      # Dependências do projeto
 ┣ 📜 LICENSE                     # Licença MIT
 ┗ 📜 README.md                   # Documentação
```

---

## 🤝 Contribuição

Contribuições são sempre bem-vindas! Para contribuir:

1. Faça um **Fork** do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'feat: Adiciona MinhaFeature'`)
4. Faça Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um **Pull Request**

---

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

<p align="center">
  Feito com 💙 por <a href="https://github.com/IamThiago-IT">Thiago</a>
</p>
