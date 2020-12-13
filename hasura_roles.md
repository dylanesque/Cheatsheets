# User setup in Hasura

1) Deploy Hasura app from [Heroku](https://dashboard.heroku.com/new?button-url=https%3A%2F%2Fhasura.io%2F&template=https%3A%2F%2Fgithub.com%2Fhasura%2Fgraphql-engine-heroku)

2) Click on "View" button once the app finished building, and click on the "secure your endpoint" link, following the instructions there.

3) Create data tables. Make sure that user ids are of type text, and set that as the foreign key of the whatever tables are being linked to the users
   -Foreign keys are added for the benefit of Postgres; Object relationships are for GraphQL

4) Create an Auth0 application to go with this: Follow the instructions in the tutorial for [Create Auth0 App](https://hasura.io/learn/graphql/hasura/authentication/1-create-auth0-app/), Starting with the "Rules for Custom JWT Claim". DO NOT FORGET TO SET A NAMED TENANT.

5) Next, skip ahead to the "sync users with rules" page, and follow those instructions. Use the admin secret set up in Step 2 for the admin secret here, and the endpoint from your Hasura dashboard

6) Next, visit https://hasura.io/jwt-config/ to generate a JWT. Copy the key that is generated, and paste it as a value to "HASURA_GRAPHQL_JWT_SECRET" in Heroku.
   
7) Generate quickstart project 
   

