-Next routing and Links work a lot like Gatsby, but with the system of Links being more verbose

# Apollo Client in Next.js

-Wrapping the app in a HOC is the best way to go for Next & Apollo

-Add a `lib` directory with an `apollo.js` file.

-Populate the file like so, installing dependencies as needed:

```
import ApolloClient from "apollo-boost";
import { ApolloProvider } from "@apollo/react-hooks";
import fetch from 'isomorphic-unfetch';

export function withApollo(PageComponent) {
  const WithApollo = props => {
    const client = new ApolloClient({
      uri: "http://localhost:3000/api/graphql",
      fetch
    });

    return (
      <ApolloProvider client={client}>
        <PageComponent {...props} />
      </ApolloProvider>
    );
  };
  return WithApollo;
}
```

-Import withApollo into the index js, and wrap the component

-Install the isomorphic unfetch package

-getInitialProps is a React lifecycle method that doesn't exist in main React;



