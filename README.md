# Gleam Presentation

This is the code for the presentation given abou Gleam @ Gangverk 2024

## Project structure

Project is structured in the following way

```
├── priv
│   └── static
│       ├── dist
│       └── sources
├── src
│   ├── app
│   │   ├── components
│   │   ├── pages
│   │   ├── web
│   │   ├── models.gleam
│   │   ├── pages.gleam
│   │   ├── router.gleam
│   │   ├── service.gleam
│   │   └── web.gleam
│   └── app.gleam
├── Dockerfile
├── gleam.toml
├── manifest.toml
├── package.json
├── pnpm-lock.yaml
├── README.md
└── tailwind.config.js
```

### priv

Contains the private files to be served by the server. Most files here are autogenerated but you can add custom scripts and assets if required to the `dist` folder.

### src

Contains all the Gleam source code for the project, with `app.gleam` being our entrypoint. It's further structured as follows:

#### app

Files at the root work as the main entrypoints for each module. The filenames should be pretty self explanatory

#### components

Files in the `components` module are intended to be pure functions that return html code, they are using [nakai](https://github.com/nakaixo/nakai) as the templating engine.

#### pages

Code in the `pages` module defines the views to be rendered in the browser using a mix of nakai elements and componets as defined in the `components` folder.

#### web

The `web` module takes care of handling request and determining which views to render according to those requests. It's essentially an extension of the router code.


## Development

Requirements: This project needs node installed to work as it depends on tailwindcss.

```sh
pnpm install # Install the dependencies
pnpm run dev   # Run the project
gleam test  # Run the tests
```

**Looking for a more robust Gleam solution?** 
Check out the [Gleam Monorepo Template](https://github.com/sandsower/gleam-monorepo-template)! It's setup to use Wisp for the backend and Lustre for the frontend 

## Deployment

The project comes with a standard Dockerfile that can be used for deployment purposes

# TODO

- Remove node dependencies
- Expand on deployment section

Initial structure inspired by the work done for [jsorm](https://github.com/aosasona/jsorm), check it out for your JSON explorer needs!
