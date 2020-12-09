# Setting up a React project with create-react-app

- Use styled components
- Use Prettier to keep code consistent
- Remove unnecessary files after running Create React App as soon as
  possible
- It's important to have well defined file structures and folder structures
  sooner rather than later in a project, i.e.
  - `layouts` folder for major view outlines for common components rendered on
    every view or multiple views have shared components
  - Use a `components` folder for lower level stuff
  - A `views` folder for higher level stuff
  - `__tests__` for tests
  - `App.js` and `index.js` remain at root level of the folder
- `React.StrictMode` gives you a layer of
  (assurance)[https://reactjs.org/docs/strict-mode.html], but it does introduce complications when developing locally
- Add files to `.gitignore`
- Make skeleton components by adding empty files where you think you might need
  them
- Having a high level idea of your views reinforces the structure of your files
  and folders

# Building Your React App's Architecture

- Use semantic html where possible -- not every component has to be wrapped in
  a div
- Fill out logic of skeleton files by wiring together components

# Making Skeleton Components In Your React App

- Use Material UI for forms as it's easy to implement and powerful

# Adding Routing in React with react-router-dom

- Add routes in the `App` component using React Router Dom
- Store routes in `Routes.js` file
- `Switch` component allows routes to be rendered exclusively
- Typically, the `exact` attribute is used in `Route` components
- Include slashes in slugs, eg. `<Route exact path="/items" component{Items} />
- Organize import statements in alphabetical order for quick skimming
- Replace all `<a href>` components with components from React Router Dom, eg.
  `<Link to>`
- Higher level styled components should be named so you can keep track of where
  you are in the application -- lower level styled components can be anonymous
- Styled components are typically declared as `const` and occasionally
  declared as `function`

# Adding Styles And Hooks To Components

- Use mock data to aid development
- Instead of Redux, use `createContext`
- Context captures data and can be shared across multiple components, especially
  for global values used across the app, to avoid deep prop drilling
- `useState` is how to handle form updates, actions on the page, and other
  dynamic interactions that happens in an SPA
- Any components wrapped inside a provider has access to context functions

# Working With Third-Party APIs and Data Handling

- `fakerapi.it` is a free API that serves mock data although you can't POST to
  it
- `useEffect` pulls data when the component loads, and adding an empty array as
  an argument, the call only happens once to avoid an infinite loop, eg.
  `useEffect(handler, []);`
- Define dependencies of component function below the function in the same file

# Finishing Up APIs And A Bit About Packages

- Styled components can target child components
- Talk through your thinking process when debugging; it also helps to refresh
  the browser
- Use trial-and-error to figure out which libraries to use
  - Make sure libraries are relatively small
  - Libraries used should have good documentation
  - Libraries should have a community that will maintain it
    - When's the last pull request?
    - When's the last time a user asked a question about the library on Stack
      Overflow?
    - As a last resort, look at number of stars on the repo in GitHub

# Performance Optimization and Accessibility In React

- Code split so components are lazy loaded instead of loading all components up
  front, slowing down load time
- Use React's `Suspense` to load placeholder elements
- `React.lazy` allows you to render a dynamic import as a regular component to
  dynamically load all components
- Much of the code splitting can be done in the router, which is where
  components are loaded from
- Split larger components as it might not make a huge difference to code split
  smaller components
- Use profiler tab in dev tools to record how long each component takes to load
- Use Lighthouse tool to generate a report for your app
- Everyone deserves the same level of access

# Writing Tests For React Components

- There are many ways to write tests
- Read test reports to understand what to fix
- Testing can be tricky because certain packages aren't up-to-date with what's
  happening in the testing library, which means things are out of sync

# Writing A Test For Fetching Data From an API

- Use mock requests and mock data to see if components render the way we
  expect
- Use skeleton test to try out broad ideas to get some direction early in a
  project or feature

# Links

- https://create-react-app.dev/docs/measuring-performance/
- https://material-table.com/#/docs/all-props
- https://reactjs.org/docs/higher-order-components.html
- https://ui.dev/why-react-hooks/
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals
- https://reactrouter.com/web/api/Hooks
- https://styled-components.com/
- https://blog.alanmontgomery.co.uk/using-react-context-api-with-nextjs
- https://reflectoring.io/github-fork-and-pull/
- https://public-apis.io/
- https://prettier.io/
- https://medium.com/product-x-culture/difference-between-508-ada-aoda-and-wcag-2-0-206ee44fce97
- https://styled-components.com/docs/tooling#better-debugging
- https://stackoverflow.com/questions/56547215/react-testing-library-why-is-tobeinthedocument-not-a-function
