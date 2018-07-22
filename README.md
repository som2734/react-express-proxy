# A Study of React using Express as a Server

## Agenda

1. Create React App
1. Server Setup
1. Ejecting Creat React App
1. Component setup
1. Hookup REST API through Redux Thunk

## Maybe if we have time

- How do I break up components?
- Webpack 4 upgrade (zero configuration)
- Routing (w/ React Router)
- REST API - Redux Thunk
- REST API - Redux Saga
- GraphQL setup
- Redux Form
- Styled Components
- Babel (transpiler)
- Redux - State Manager
- [React Concepts] Context API
- [React Concepts] Fragments
- Form elements - controlled vs uncontrolled

UNIX cmds and other bash/zsh thingys and other apps and shit
- cat / more
- oh_my_zsh
- Visual Studio Code
- [Book] Resilient Web Design by Jeremy Keith https://resilientwebdesign.com/
- Atomic Design by Brad Frost http://atomicdesign.bradfrost.com/
- React starter kit based on Atomic Design https://github.com/diegohaz/arc
- yarn commands
- Docker and Kubernetes (k8)
- Heroku https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up
- CSS in JS
- React Unit Testing
- Renovate https://renovatebot.com/
- Compatibility Table: https://kangax.github.io/compat-table/es6/
- Prettier (code formatter)
- [Design pattern] Unidirectional data flow
- [Messaging] Pub/Sub https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
- [React Concept] Unidirectional data flow

## Knowledge Dump

_What is a lock file?_

A lock file basically shoves all of the depedencies map into an autogenerated file a tool can reference to install packages more optimally. Don't modify this. It's autogenerated.

_Server Setup_

- Install dependencies
  - Express
  - Nodemon
  - Body Parser (for JSON on server)
  - Path
- Setup npm scripts  
  - dev scripts
    - npm-run-all
  - Prod script
- Setup Docker
  - Install docker on local machine: https://docs.docker.com/install/

_Why do we use `Webpack Dev Server` and `Express` for development?_

We need express to do any hookups with APIs. In production, we use express to serve the application. Webpack dev server is only for local development. It detects diffs in our project and re-builds it, which Express can't do. We also have set-up react-hot-loader to re-render only the components that have changed. 

_What is Docker?_

Uh....

```bash
docker images # Lists docker images
# REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
# <none>              <none>              fbe5e7e6f00e        30 seconds ago      804MB
docker create fbe5e7e6f00e # Creates docker image
# 91a83a81ce6944d730892f1e4e740242c96c265246e185f3182627cd5bda9b9b
docker start 91a83a81ce6944d730892f1e4e740242c96c265246e185f3182627cd5bda9b9b # starts the container
```

_Why boilerplates?_

Configuring React apps are hard, confusing, misleading, and all around hair tearingly bad. Create React App came about because a small team at Facebook saw a lot of developers were having trouble setting up their project end-to-end, which means lower developer happiness and usage. To mitigate some of this stress, the team set out to write one boilerplate to rule them all. Hence their philosophy.

> One Dependency: There is just one build dependency. It uses Webpack, Babel, ESLint, and other amazing projects, but provides a cohesive curated experience on top of them.

> No Configuration Required: You don't need to configure anything. Reasonably good configuration of both development and production builds is handled for you so you can focus on writing code.

> No Lock-In: You can “eject” to a custom setup at any time. Run a single command, and all the configuration and build dependencies will be moved directly into your project, so you can pick up right where you left off.

_Why use webpack?_

You can totally not use webpack! Webpack is more for bundling if you're using special javascript files, css preprocessor, languages that transpile to javascript, (ES6) babel transformations, and more things. There are alternatives to webpack, of course. To name a few, `browserify`, `gulp`, `grunt`, I think there's some other stupid names ones like `broccoli` and `brunch`. 

_What's a design system / manual?_

A design manual is an outline or blueprint for designing all assets. Everything from letterheads, email signatures, to signage. In web design, this is the breakdown of all web elements on the page. 

We can use a methodology like BEM, SMACSS, and other methodologies to organize reusable components of a website. That means breaking elements down to its most fundamental and describing its variations. In many of my recent projects, I've used atomic design to organize with an inherent hierarchy: atoms, molecules, organisms, templates, and pages. With React and other front-end libraries and frameworks, you can use [storybook](https://storybook.js.org/) to organize how each design element is used.

_How does React Architecture compared to other front-end libraries/frameworks?_

- Retrieving values from form elements
- Persistent Data Locally
- Persistent Data to a server
- Building Components
  - Pure Components Pattern
  - Managing component props and state
  - Where to keep certain logic
  - Data Flow between components

_How do I introduce authentication?_

Authentication requires routing. There are numerous ways of implementing security, and each has its drawbacks. For example, you can use OAuth to sign your users in with an OAuth provider. Then you have to think of session storage, tokens, cookies, or some way of persisting user information in a secure way from the front-end to talk back to the server with.

In previous React apps, I've used cookies, a JWT, a hash key, and other methods to store this with a login call. There's also another call if a token is available to assume the user is authenticated and start calling APIs. When a 401 status code comes back, we automatically log the user out.

A system to call APIs must already be in place before authentication can be done.
