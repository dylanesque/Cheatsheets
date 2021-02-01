# Apollo Client

1) Install graphql and @apollo/client

2) Create an instance of Apollo Client for the application. You'll need `Apollo Client` and `InMemoryCache` for this.

```javascript
const client = new ApolloClient({
 uri: 'http://localhost:4000',
 cache: new InMemoryCache(),
});
```
- The `uri` is the location of our GraphQL server
- the `cache` is the InMemory Cache, which does a lot of caching behind the scenes


3) We wrap the App component (or take an alternate strategy, as in the case of Next.js) in an `ApolloProvider`, 
   and pass the Apollo Client instance as a prop to that.

# Apollo Server