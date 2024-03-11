# GraphQL

- Projeto de estudo de GraphQL do curso FullCycle

## Comandos necessários:

- Instalar as dependências:
```bash
go mod tidy
```

- Rodar o projeto:
```bash
go run cmd/server/server.go
```

- Acessar o playground:
```
http://localhost:8080/
```

## GQLGen
- Para gerar os arquivos necessários para o GraphQL, execute o comando:

```bash
go run github.com/99designs/gqlgen init
```

- Para gerar os arquivos necessários para o GraphQL, execute o comando:

```bash
go run github.com/99designs/gqlgen generate
```

- Referência: [GQLGen](https://gqlgen.com/)

## Queries:
- Categories:
```graphql
mutation createCategory {
  createCategory(input:{
    name: "Tecnologia",
    description:"Cursos tecnologia"
  }) {
    id, name, description
  }
}

query queryCategories {
  categories{
    id
    name
    description
  }
}

query queryCategoriesWithCourses{
  categories{
    id,
    name,
    courses{
      id,
    	name
    }
  }
}
```

- Courses:
```graphql
mutation createCourse{
  createCourse(input: {
    name: "FullCycle",
    description:"the best!!",
    categoryId: "0979cd9a-ff59-40c0-94c9-aa0efa7fa68c"
  }) {
    id, name, description
  }
}

query queryCourses {
  courses{
    id
    name
    description
  }
}

query queryCoursesWithCategory{
  courses{
    id
    name
    description
    category{
      id
      name
    }
  }
}

```