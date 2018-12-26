# GraphQL Cheatsheet

##


## Schema

## Built-in scalar types

- `ID`: Entity identifier
- `Boolean`: Boolean
- `Float`: Floating-point number
- `Int`: Integral number
- `String`: String

## Type definitions

- `scalar`: Scalar type
- `type`: Object type
- `interface`: Interface type
- `union`: Union type
- `enum`: Enumeration type
- `input`: Input object type

## Type modifiers

- `String`: Nullable string
- `String!`: Non-null string
- `[String]`: List of nullable strings
- `[String]!`: Non-null list of nullable strings
- `[String!]!`: Non-null list of non-null strings


## Input arguments

### Basic input

```graphql
type Query {
    animals(limit: Int): [Animal]
}
```

### Input with default value

```graphql
type Query {
    animals(limit: Int = 10): [Animal]
}
```

### Input with multiple arguments (and default values)

```graphql
type Query {
    animals(limit: Int, sort: String = "asc"): [Animal]
}
```

```graphql
type Query {
    animals(limit: Int = 10, sort: String): [Animal]
}
```

```graphql
type Query {
    animals(limit: Int = 20, sort: String = "desc"): [Animal]
}
```

## Input types

```graphql
input ListAnimalsInput {
    limit: Int
    sort: String
    since_id: ID
}

type Query {
    animals(input: ListAnimalsInput): [Animal]!
}
```

