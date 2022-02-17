# About

Hi, this is a MERN boilerplate I'd compiled over time to quickly spin up a full stack app with auth, todos, a mongo DB, all that. I used to be a big fan of webpack managing the all-encompassed app (shared type), but have since preferred keeping the front-end and back-end separated and swappable. Perhaps I'll change this boiler to something more in that line at some point :)

### Technicalities

* Axios is configured to automatically attach Auth JWT headers to API requests. Can be bypassed/modified by using `axios` normally or in your desired configuration
  * JWT tokens are stored in cookies (rather than localStorage)
* Redux is organized in the [Ducks Modular Redux](https://github.com/erikras/ducks-modular-redux) paradigm
* React containers are organized in the Ember-like fashion proposed by [alexmngn](https://medium.com/@alexmngn) in his [article](https://medium.com/@alexmngn/how-to-better-organize-your-react-applications-2fd3ea1920f1). A summary as follows:
  * Containers are placed as the `index.js` elements in their respective folders inside `scenes`. Each container can then have its own utilities, services, components and nested scenes, allowing grouping based on feature rather than by root page/element
  * General components (buttons, form elements) are placed in the general `client/components` directory
* Absolute imports are used - head to `webpack.config.dev.js` and look at `resolve.alias`. This allows you to import files from your project with paths like `@/Components/FileName` rather than `../../../../Components/FileName`. Configure as you like.
* Forms use [redux-form](https://github.com/https://redux-form.com)
* Note that in this simple Todo example, anyone can create or update todos as long as they are logged in

## First-time Setup

* Install [yarn](https://yarnpkg.com/en/docs/install)
* Copy the `.env.example` to your `.env`, making changes as needed
* Install Webpack globally `yarn global add webpack`
* Install typescript globally `yarn global add typescript`
* Install mongo globally `yarn global add mongo`. In one terminal, run `sudo mongod` to spin up a database. Note the example env is configured to connect to a database on localhost, but you can configure it as you like
* Inside the main directory of the project, run `yarn` to install dependencies

Go ahead and run
```bash
$ yarn run dev
```

To start devving!

## Development

* `yarn run dev` - to start local development server with nodemon and hot reloading.
<!-- * `yarn test` - to run unit tests. -->
* `yarn lint` - to run linter.
* `yarn build` - to build production files
* `yarn run prod` - to start the server in production mode
* `yarn bs` - to build production files and start server in production mode (combination of above two steps).
