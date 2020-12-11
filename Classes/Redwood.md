# What is JAMStack and Prisma

- JAMStack uses microservices
- Prisma is an ORM for SQL, allowing us to use object-notation to write queries

# Starting With RedwoodJS

- The dummy data and dummy pages from installing Redwood makes it easy to add
  more pages
- Prisma schema defines how obejct-relational mapping works
- Under `api` directory:
  - `seeds.js` will hold dummy data for app
  - `src` folder has `functions` subfolder for GraphQL
  - `graphql` subfolder holds graphql schema
  - `lib` subfolder instatiates prisma database client
  - `services` subfolder holds business logic such as GraphQL queries and
    mutations
- `web` folder holds front-end code
  - `src` folder has subfolders too
    - `components` holds components
    - `layouts` holds layouts
    - `pages` holds anything you want in the url as the router is build off
      folder structure, like Next.js
    - `index.js` bootstraps code and gets Redwood running
    - `routes.js` is the meat and potatoes, like the router in React Router
- `redwood.toml` is usually fine as is

# Making Pages With RedwoodJS

- Run code regularly while coding
- Storybook is a way to debug a component

# Routing In RedwoodJS

- Follow the folder structure to get routing

# Migrating From React To Redwood

- Migrating logic from previous Create React App to Redwood starts with copying
  components logic
- `yarn rw g page activities` for example will create routing, tests, and
  storybook
- Be sure to update import statements to reflect new folder structure
- Remove Apollo and GraphQL code from components as they will live elsewhere

# Updating React Components To Work In Redwood

- Migrate layouts from previous Create React App to Redwood
- Be sure to update import statements to reflect new folder structure
- Remove Apollo and GraphQL code from components as they will live elsewhere

# Setting Up Postgres In Redwood

- Prisma sits in front of SQL to simplify queries
- Include port in environment variable when connecting to postgres
- `yarn rw db save "create models"` will migrate data

# Using Scaffolding In Redwood

- `yarn rw g scaffold store` will generate example code, which you can use to
  build out your own code, but first you'll need a GraphQL schema
- Troubleshooting tip: delete `_migrations` table and migrate data using `rw`

# Working With Cells In Redwood

- Cells store GraphQL logic
- Files ending with `cell` tell Redwood that these are cells
- Default exports goes against Redwood conventions
- Manual refreshes are necessary between many back-end changes
- Postgres uses single quotes not double quotes

# Creating New Cells And Queries In Redwood

- Redwood is sensitive to naming conventions, eg. single vs plural

# Links

- https://jamstack.org/
