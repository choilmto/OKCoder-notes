# Intro to GraphQL, Part 0

- Property types on the data defines the schema, but so do interactions. How do
  you get data? How do you create new data? How do you send data?

# Intro to GraphQL, Part 1

- REST api's are limited to whatever you can put in a URL, and the data
  returned is pre-defined
- In GraphQL, there is one api and the client can decide what data it needs,
  and the endpoint doesn't over- or under-provide data. The client will have to
  do more work though.
- GraphQL has one endpoint, which combines data from databases and api's
- GraphQL errors are informative

# Intro to GraphQL, Part 2

- Keep queries simple by avoiding optional ID fields so they're well defined
- You can redistribute how much work the front-end does with the data from
  GraphQL to the back-end
- Avoid using anonymous types as defined types make debugging easier
- Use types! Please, use types (both GraphQL primitives and literal types you
  define)!
- To experience the full benefits of iGraphQL, have your type definitions like
  so:

```
input ItemInput {
    id: ID
    name: String
    .
    .
    .
}

mutation {
    createItem(input: ItemInput): Item
}
```

# Intro to GraphQL, Part 3

- Use GraphQL's subscriptions to inform components of updates to properties

# Setting Up A Node Server For GraphQL

- Have a directory for GraphQL code, eg. `inventory-graphql`
- Name your project in `package.json` so that it's distinct from any of the
  dependency packages you use, as that will cause problems
- When writing a new server, expose a simple endpoint to test it
- Prepend an underscore to intentionally unused parameters in function
  definitions to remove messages informing you of unused parameters

# Setting Up A GraphQL Schema

- GraphQL can nest types, sometimes deeply
- Copy-pasting code removes opportunities for misspelling words

# Adding GraphQL Queries And The GraphiQL Tool

- Have a file `resolvers.js` to hold your resolvers
- Import `makeExecutableSchema` to simplify and expedite the process of making
  a schema
- History tab in GraphiQL is useful for debugging and tracing

# Working With Mutations In GraphQL

- Having type definitions will resolve many issues when working with deeply
  nested data in api's or general performance issues
- Try out mutations on temporary database to try out queries

# Connecting GraphQL To A Mongo Database

- Try not to use the mongo string when setting things up
- Use a `dbConnectors.js` file to hold connectors
- Using promises when working with mongoose may be more readable over
  async/await

# Updating GraphQL Mutations To Work With A Mongo Database

- Getting rid of unused code as you go can provide some psychological relief
- Look at documentation explorer in GraphiQL to see mutations and queries

# Adding Update Mutations To GraphQL

- Use an underscore as a placeholder for unused parameters when defining
  callbacks

# Adding Delete Mutation To GraphQL

- You can group queries by functionality or by type
- Reuse entries in the history of GraphiQL to test code
- Verify that changes to the database have happened as you'd expect by
  examining the data using MongoDB Compass

# Setting Up Apollo GraphQL In React

- Apollo is the most popular GraphQL client
- We're using Apollo's in-memory cache
- There is a convention that GraphQL queries are written in all-caps
- The `schema.js` file can act as documentation showing what queries you can
  make, which is useful especially in the case where you have little access to
  the back-end.

# Querying GraphQL With Apollo In React

- Use GraphiQL to hard-code examples of mutations you want to see, and replace
  values with variables when coding up the mutation in the front-end

# Updating Data In GraphQL With Apollo In React

- Don't forget to include the id when querying in GraphQL

# Deleting Data In GraphQL With Apollo In React

- A naming convention is to use matching names for GraphQL queries in the the
  front-end and back-end, but if you're going to give friendlier names to
  queries in the front-end, every one has to be on the same page
- Most apps have different forms for different components
- Always set a fallback render, especially since GraphQL has nice built-in
  state handling
-

# Links

- https://honest.engineering/posts/why-use-graphql-good-and-bad-reasons
- https://github.com/nvm-sh/nvm
- https://stackoverflow.com/questions/22891211/what-is-the-difference-between-save-and-save-dev#:~:text=By%20default%2C%20NPM%20simply%20installs,to%20the%20package's%20development%20dependencies
- https://graphql.org/graphql-js/mutations-and-input-types/
- https://github.com/ardatan/graphql-tools
- https://docs.mongodb.com/compass/master/install
- https://zellwk.com/blog/install-mongodb/
- https://www.howtographql.com/advanced/4-security/
- https://yarnpkg.com/package/download
- https://flaviocopes.com/npm-packages-local-global/#:~:text=local%20packages%20are%20installed%20in,%2Dg
