# Apollo Client

- Apollo Client is a GraphQL data-fetching layer for the front-end that also includes caching and state management.

## Caching

Per the Apollo Docs:

> "Whenever Apollo Client fetches query results from your server, it automatically caches those results locally. This makes subsequent executions of the same query extremely fast."

## Installation

1. Install `graphql` and `@apollo/client`

2. Create an instance of Apollo Client for the application. You'll need `Apollo Client` and `InMemoryCache` for this.

```javascript
const client = new ApolloClient({
  uri: "http://localhost:4000",
  cache: new InMemoryCache(),
});
```

- The `uri` is the location of our GraphQL server
- the `cache` is the InMemory Cache, which does a lot of caching behind the scenes

3. We wrap the App component (or take an alternate strategy, as in the case of Next.js) in an `ApolloProvider`,
   and pass the Apollo Client instance as a prop to that.

# Apollo Server

- From the Apollo website:

> "Apollo Server is an open-source, spec-compliant GraphQL server that's compatible with any GraphQL client, including Apollo Client. It's the best way to build a production-ready, self-documenting GraphQL API that can use data from any source."

- The Apollo Studio Explorer acts as the GraphiQL IDE for your Apollo Server project.

## Schema Creation

1. Create a file (something like `schema.js`)

## DataSource

// TODO: **Resolvers in Apollo are a shaky concept for me, especially what precisely goes in the parent**

- `DataSource` is an abstract class with several implementations specific to certain data/source types like REST, Mongo, SQL, etc.

- resolver functions in Apollo have a params signature very close to that of native GraphQL resolver:

1. `parent` is the returned value of the resolver for that particular field's parent.
2. `args` are all arguments provided for that field.
3. `context` is necessary context for the query, such as authentication state, or a db connection.
4. `info` is optional metadata.

# Apollo Federation

- Apollo Federation is a way to split your endpoint into multiple microservice-style resources.

CREATE TABLE unesco
 (name TEXT, description TEXT, justification TEXT, year INTEGER,
    longitude FLOAT, latitude FLOAT, area_hectares FLOAT,
    category_id INTEGER, state_id INTEGER,
    region_id INTEGER, iso_id INTEGER);