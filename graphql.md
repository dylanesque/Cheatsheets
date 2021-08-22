# Basics

- GraphQL is a query langaugenfor your API that offers a more flexible way to get data as opposed to REST APIs.

# Jargon

- *Nodes* represent objects and *Edges* represent the relationships between those objects.

- *Scalar* types are primitives, *Object* types are complex.

- A *Field* is an attribute of an object type.

- An *Alias* can be used to rename the results of a field query to something more unique:

```js
  jediHero: hero(episode: JEDI) {
    name
  }
}
```

- *Fragments* are essentially variables that we can reuse when we need to user certain fields over and over again in queries.

- *Directives* are logic that can alter what gets returned by a query based on the value of certain key variables.

- *Resolvers* are functions that take several arguments for queries or mutations. Discussed in depth here: https://graphql.org/learn/execution/#root-fields-resolvers

# SDL

- The Schema Definition Language is how we describe objects in GraphQL

- We can use single or triple quotes to make inline or block-level comments.



# Disadvantages

- GraphQL does nothing to curb the complexity of requests from the front-end

- Harder to implement rate-limiting

- Caching is more complicated

# ORMs

- Prisma: Best for mapping existing datasources, getting up and running fast

- Hasura: Shines at subscriptions/realtime use-cases