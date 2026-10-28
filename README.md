# Biblioteca Digital

Sistema de linha de comando para gerenciar uma biblioteca: cadastro de usuários e livros, empréstimos, devoluções e cálculo de multas por atraso.

Projeto de estudo focado em fundamentos de Java: orientação a objetos, JDBC puro, separação em camadas, testes automatizados e concorrência.

## Tecnologias

- Java 21 (LTS)
- SQLite, como banco embutido em um arquivo
- sqlite-jdbc, driver JDBC para SQLite
- Maven, para build e gerenciamento de dependências
- JUnit 5, para testes (a partir da etapa de testes)

## Requisitos

- JDK 21 ou superior
- Maven 3.9 ou superior

Para verificar as versões instaladas:

```bash
java -version
mvn -version
```

## Como compilar

Na raiz do projeto, rode:

```bash
mvn -q compile
```

Se a compilação terminar sem mensagens, o projeto está correto.

## Banco de dados

O banco é um arquivo SQLite. Não é preciso instalar servidor nem criar usuário.

O caminho do arquivo fica em `src/main/resources/connection.properties`. Na primeira execução, o arquivo é criado automaticamente, junto com as tabelas.

O arquivo do banco não é versionado: ele está listado no `.gitignore`, porque contém dados de uso.

## Estrutura do projeto

```
biblioteca-digital/
├── docs/                         documentação extra
├── src/
│   ├── main/
│   │   ├── java/com/biblioteca/
│   │   │   ├── config/           conexão com o banco
│   │   │   ├── dao/              acesso a dados com JDBC
│   │   │   ├── model/            entidades do domínio
│   │   │   ├── service/          regras de negócio
│   │   │   ├── threads/          tarefas em paralelo
│   │   │   └── ui/               menu de linha de comando
│   │   └── resources/
│   │       └── connection.properties
│   └── test/
│       └── java/com/biblioteca/  testes automatizados
├── pom.xml
└── README.md
```

## Fluxo de desenvolvimento

O projeto segue o Git Flow. Cada etapa de desenvolvimento fica em uma branch própria, criada a partir da `develop` e integrada de volta a ela. A `main` recebe apenas versões estáveis.

## Status

Em desenvolvimento. A etapa atual é a de estrutura base.