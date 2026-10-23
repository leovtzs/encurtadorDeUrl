# 🔗 Encurtador de URL

Aplicação web para encurtamento e gerenciamento de URLs, desenvolvida com Java e Spring Boot. O projeto conta com uma API REST para cadastrar, consultar, listar e excluir URLs, além de uma interface web simples e intuitiva.

## 🚀 Tecnologias utilizadas

- **Java 25**: linguagem de programação.
- **Spring Boot**: estrutura principal da aplicação.
- **Spring Web MVC**: criação dos endpoints REST.
- **Spring Data JPA**: persistência e gerenciamento dos dados.
- **H2 Database**: banco de dados relacional em memória.
- **HTML5 e CSS3**: estrutura e estilização da interface.
- **JavaScript**: comunicação entre o front-end e a API.
- **Maven**: gerenciamento de dependências e build do projeto.
- **Lombok**: suporte ao processamento de anotações.

## ✨ Funcionalidades

- Encurtamento de URLs a partir de um endereço original.
- Geração de um código curto para cada URL.
- Cadastro de URLs no banco de dados.
- Listagem de todas as URLs cadastradas.
- Consulta de uma URL pelo seu identificador.
- Exclusão de URLs cadastradas.
- Interface web para inserir URLs e visualizar os resultados.

## 🛠️ Arquitetura do projeto

O projeto utiliza uma organização em camadas, separando as responsabilidades da aplicação.

```text
src/
├── main/
│   ├── java/
│   │   └── encurtadorDeUrl/
│   │       ├── EncurtadorDeUrlApplication.java
│   │       ├── controller/
│   │       │   └── UrlController.java
│   │       ├── model/
│   │       │   └── Url.java
│   │       ├── repository/
│   │       │   └── UrlRepository.java
│   │       └── service/
│   │           └── UrlService.java
│   └── resources/
│       ├── application.properties
│       └── static/
│           └── index.html
└── test/
    └── java/
        └── encurtadorDeUrl/
            └── EncurtadorDeUrlApplicationTests.java
```

### Responsabilidade de cada camada

- **Controller:** recebe as requisições HTTP e disponibiliza os endpoints da API.
- **Service:** concentra a lógica de negócio e o processamento das URLs.
- **Repository:** realiza as operações de persistência no banco de dados.
- **Model:** representa a entidade `Url`, com identificador, endereço original e código curto.
- **Static:** contém a interface web da aplicação.

## ⚙️ Como executar o projeto

### Pré-requisitos

- Java JDK 25.
- Git.
- Maven instalado ou utilização do Maven Wrapper incluído no projeto.


### 2. Entre na pasta do projeto

```bash
cd encurtadorDeUrl
```

O nome da pasta pode variar conforme o diretório criado pelo Git.

### 3. Execute a aplicação

No Linux ou macOS:

```bash
./mvnw spring-boot:run
```

No Windows:

```powershell
.\mvnw.cmd spring-boot:run
```

Alternativamente, com o Maven instalado:

```bash
mvn spring-boot:run
```

### 4. Acesse a aplicação

Com o servidor em execução, abra:

- **Interface web:** http://localhost:8080
- **API REST:** http://localhost:8080/urls
- **Console do H2:** http://localhost:8080/h2-console

O console do H2 permite consultar os dados durante a execução. Como o banco está configurado em memória, os dados são perdidos quando a aplicação é encerrada.

## 📡 Endpoints da API

A API utiliza a rota base `/urls`.

| Método HTTP | Endpoint | Descrição |
|---|---|---|
| `POST` | `/urls/criar` | Cadastra e encurta uma URL |
| `GET` | `/urls` | Lista todas as URLs cadastradas |
| `GET` | `/urls/{id}` | Consulta uma URL pelo ID |
| `DELETE` | `/urls/{id}` | Exclui uma URL pelo ID |

### Exemplo de requisição

Para cadastrar uma URL, envie uma requisição `POST` para:

```text
http://localhost:8080/urls/criar
```

Cabeçalho:

```http
Content-Type: text/plain
```

Corpo da requisição:

```text
https://www.exemplo.com.br/pagina
```

A resposta retorna os dados da URL cadastrada, incluindo o identificador, o endereço original e o código curto gerado.

## 🗄️ Banco de dados

O projeto utiliza o H2 Database em memória, integrado ao Spring Data JPA.

Configurações atuais:

- URL JDBC: `jdbc:h2:mem:testdb`
- Usuário: `sa`
- Senha: vazia
- Console web: `/h2-console`

Essas configurações são voltadas ao desenvolvimento local e podem ser adaptadas para um banco de dados persistente em futuras versões.

## 🎯 Objetivos do projeto

Este projeto tem como objetivo praticar conceitos de desenvolvimento back-end, incluindo:

- Desenvolvimento de APIs REST com Java.
- Organização de aplicações em camadas.
- Operações CRUD.
- Persistência de dados com JPA.
- Integração entre front-end e back-end.
- Configuração e execução de aplicações com Maven e Spring Boot.

## 🔮 Possíveis melhorias futuras

- Implementar códigos curtos únicos e aleatórios.
- Criar redirecionamento automático para a URL original.
- Adicionar validação de URLs.
- Implementar tratamento de exceções e respostas HTTP apropriadas.
- Migrar para um banco de dados persistente.
- Adicionar testes automatizados para os endpoints.
- Permitir copiar o link curto diretamente pela interface.

## 👨‍💻 Autor

**Leonardo Vitor de Jesus Santos Lacerda**

Desenvolvedor com foco em Java e desenvolvimento back-end.

- GitHub: [@leovtzs](https://github.com/leovtzs)

---

Desenvolvido com Java, Spring Boot e vontade de aprender cada vez mais. 🚀
