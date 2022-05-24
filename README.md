# Glyphx Monorepo

## 1. Install dependencies

A few dependencies need to be available in your development system. Please verify they are present or install them.

- Node v12+
- Yarn v1.22.5+
- Docker v19+

Open a terminal and run the following commands:

```bash
node -v
yarn -v
docker --version
```

This should produce the following output:

If you need to install or update any of the dependencies, please see the following guides:

- [Downloading and installing Node.js and npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- [Yarn Installation](https://yarnpkg.com/getting-started/install)
- [Install Docker for Windows](https://docs.docker.com/docker-for-windows/install/) / [Install Docker for Mac](https://docs.docker.com/docker-for-mac/install/)

## 2. Extract and install

Extract the contents of the zip file into a folder of your choice.

Run `yarn` in your project directory to install and download all dependencies.

The installation process should take around 3-10 minutes depending on the dependencies that need to be downloaded.


You can confirm everything was installed correctly by running `yarn -v`. This should show a yarn version of `3.0.0+`.


## 3. Build modules

Make sure that the project compiles correctly by running `yarn build` your project directory:

Note that this command also ensures that all TypeScript project references are configured correctly.

## 4. Configure VSCode

In order to setup VSCode, open the project in VSCode.

VSCode may prompt you to ask if you trust the authors of the workspace. Respond with Yes.

You may also be asked if you want to install recommended extensions for this workspace. We recommend to do so since the template will be optimised to work with the suggested extensions.

If you want to install the necessary extensions manually, here are links to the extensions required:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [ZipFS](https://marketplace.visualstudio.com/items?itemName=arcanis.vscode-zipfs) (optional)

## 5. Initialise TypeScript

Locate a `.ts` or `.tsx` file in the workspace and open it. When asked whether to use the workspace TypeScript version, click _Allow_.

In the status bar on the bottom right-hand corner of the VSCode editor you should now see _TypeScript_.


## 7. Develop

Each module you have selected comes with its own instructions about how to get started with development. However, there are some handy commands in the project root that can be useful for development:

- `yarn build`: Will build all modules in the project.
- `yarn compile`: Will compile all TypeScript code.
- `yarn fix-project-references`: Will ensure all [TypeScript project references](https://www.typescriptlang.org/docs/handbook/project-references.html) between the packages in the project are correct. Always run this after adding a new package or changing the dependencies between packages in the project.
- `yarn test-watch`: Will run tests when modules have changed.
- `yarn format-check` and `yarn format`: Will check or fix source code formatting using Prettier
- `yarn lint` and `yarn lint-fix`: Will check or auto-fix linting issues using ESLint.

Note that you can run all of these commands in the context of individual modules as well. If you only modify code within one module, this is sufficient. However, if you develop multiple modules at the same time, it is important to run these commands at the project root.

## Notes

### Max ListenersExceededWarning on `compile-watch` command

When running the `compile-watch` command in the root, you may get the following warning:

    (node:97874) MaxListenersExceededWarning: Possible EventEmitter memory leak detected. 11 SIGINT listeners added to [process]. Use emitter.setMaxListeners() to increase limit

This is nothing to worry about. It is caused by the command spawning a lot of sub-processes, since an individual `nodemon` process is started for every package that is watched (see also [this question](https://stackoverflow.com/questions/9768444/possible-eventemitter-memory-leak-detected) on Stackoverflow).
