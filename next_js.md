# API Routes

- Next.js has API routes, that work similar to pages

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

# Routing

- Next routing and Links work a lot like Gatsby, but with the system of Links being more verbose

- We can handle nested routes by nesting folders in the pages directory; every instance of of an `index.js/tsx`
file indicates the root of that part of the path

- Parameterized routes can be created with brackets: `[id].jsx`

- The router can be accessed with the `useRouter` hook, which gives access to the router object

- Catch-all routes apply to everything that fits X template: Good for when you need similar layouts for dynamic information. Think of them like a reusable component, but on a page level. See https://nextjs.org/docs/routing/dynamic-routes

- The Link component is intended ONLY for client-side routing.

- Best practice is to wrap <a> tags in a Link tag:
 ```javascript
<Link href="/about">
  <a>About Us</a>
</Link>
```

- Use the router API for programmatic routing

# Styling



# Theming

- Scott Moss's recommendation is to use [Theme UI](https://hendrixer.github.io/nextjs-course/themeui)



