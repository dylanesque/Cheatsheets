# Basics

- GraphQL is a query langaugenfor your API that offers a more flexible way to get data as opposed to REST APIs.

# Jargon

- *Nodes* represent objects and *Edges* represent the relationships between those objects.

- *Scalar* types are primitives, *Object* types are complex.

- A *Field* is an attribute of an object type.

- *Resolvers* are functions that take several arguments for queries or mutations. Discussed in depth here: https://graphql.org/learn/execution/#root-fields-resolvers

# SDL

- The Schema Definition Language is how we describe objects in GraphQL

- We can use single or triple quotes to make inline or block-level comments.



# Disadvantages

- GraphQL does nothing to curb the complexity of requests from the front-end

- Harder to implement rate-limiting

- Caching is more complicated