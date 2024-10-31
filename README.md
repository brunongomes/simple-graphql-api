# Projeto Simples em GraphQL

Este projeto demonstra como criar uma API simples utilizando GraphQL com Apollo Server. Ele contém duas implementações: uma básica e outra utilizando TypeGraphQL para uma estrutura de código mais organizada e tipada.

## Estrutura do Projeto

- `simple-server.ts`: Implementação simples com Apollo Server e GraphQL.
- `src/`: Contém a implementação com TypeGraphQL.
- `package.json`: Script de inicialização.

## Requisitos

- Node.js (recomendado versão 20 ou superior)
- TypeScript
- Apollo Server
- TypeGraphQL (para a segunda implementação)

## Scripts

No arquivo `package.json`, você encontrará os seguintes scripts:

```json
"scripts": {
    "dev:simple": "ts-node-dev --respawn --transpile-only simple-server.ts",
    "dev": "ts-node-dev --respawn --transpile-only src/server.ts"
}
```

- `dev:simple`: Inicia o servidor simples.
- `dev`: Inicia o servidor utilizando TypeGraphQL.

## Implementação Simples (simple-server.ts)

A implementação simples utiliza Apollo Server e fornece uma API com as seguintes operações:

### Schema

```graphql
type User {
    id: ID!
    name: String!
}

type Query {
    users: [User!]!
}

type Mutation {
    createUser(name: String!): User!
}
```

### Resolvers

- **Query**: `users` retorna todos os usuários.
- **Mutation**: `createUser` cria um novo usuário e o adiciona à lista.

### Executando o Servidor

Instalar os pacotes
```bash
npm install
```

Para iniciar o servidor simples, execute:

```bash
npm run dev:simple
```

O servidor estará disponível em `http://localhost:4001`.

## Implementação com TypeGraphQL

Na segunda implementação, utilizamos o TypeGraphQL para criar um esquema mais organizado, utilizando decoradores para definir tipos e resolvers.

### Estrutura de Arquivos

- `dtos/`: Contém os modelos e inputs.
- `resolvers/`: Contém os resolvers para a API, no caso, agendamentos.

### Executando o Servidor com TypeGraphQL

Para iniciar o servidor com TypeGraphQL, execute:

```bash
npm run dev
```

## Referências

- [Apollo Server](https://www.apollographql.com/docs/apollo-server/)
- [TypeGraphQL](https://typegraphql.com/)