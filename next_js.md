# API Routes

- Next.js has API routes, that work similar to pages

To create API routes:

1) Create an `api` folder in the `pages` directory.
2) Add files as needed in this folder, which will create a path based on file names
3) Create a `handler` function, which will accept a `req` and `res`

# Apollo Client in Next.js

-Wrapping the app in a HOC is the best way to go for Next & Apollo

-Add a `lib` directory with an `apollo.js` file.

-Populate the file like so, installing dependencies as needed:

```javascript
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

- Import withApollo into the index js, and wrap the component

- Don't forget to nstall the `isomorphic-unfetch` package

# Data Fetching

- getInitialProps is a React lifecycle method that doesn't exist in main React

## How Pre-rendering works

1) Request is sent to route
2) Pre-rendered page is returned
3) Page is hydrated with React code once loaded
4) Page/Application is interactive

## Static Generation

- In which a page is pre-generated during build time: This happens by default with pages that only consist of basic HTML, etc.

- Static props are explicitly fetched like so:

```javascript
export async function getStaticProps(context) {
  const res = await fetch(`https://.../data`)
  const data = await res.json()

  if (!data) {
    return {
      notFound: true,
    }
  }

  return {
    props: {}, // will be passed to the page component as props
  }
}
```

- With pre-generated dynamic content, we also need the `getStaticPaths` function:

```javascript
export async function getStaticPaths() {
  return {
    paths: [
      { params: { ... } } // See the "paths" section below
    ],
    fallback: true or false // See the "fallback" section below
  };
}
```

- Incremental Static Generation is when Next will re-generate the page at certain intervals: https://blog.logrocket.com/incremental-static-regeneration-with-next-js/

# Head Component

- Next.js will merge multiple Head Components

# Images

# Routing

- Next routing and Links work a lot like Gatsby, but with the system of Links being more verbose

- We can handle nested routes by nesting folders in the pages directory; every instance of of an `index.js/tsx`
file indicates the root of that part of the path

- Parameterized routes can be created with brackets: `[id].jsx`

- Catch-all routes apply to everything that fits X template: Good for when you need similar layouts for dynamic information. Think of them like a reusable component, but on a page level. See https://nextjs.org/docs/routing/dynamic-routes

- The router can be accessed with the `useRouter` hook, which gives access to the router object. This is a vital technique for both parameterized and catch-all routes.

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



