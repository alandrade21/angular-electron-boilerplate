[![Angular Logo](https://www.vectorlogo.zone/logos/angular/angular-icon.svg)](https://angular.io/) [![Electron Logo](https://www.vectorlogo.zone/logos/electronjs/electronjs-icon.svg)](https://electronjs.org/)

[![License](https://img.shields.io/badge/License-AGPL--3-brightgreen.svg)](LICENSE.md)

# Introduction

This project was created based on <https://github.com/maximegris/angular-electron>. Some modifications were made to adapt this project to my taste. I will list this mods soon. For complete info about this boilerplate, please go to the original [project](https://github.com/maximegris/angular-electron).

This project bootstraps and packages your project with Angular and Electron (Typescript + SASS + Hot Reload) and SQLite (with TypeOrm) for creating Desktop applications.

Currently runs with:

- Angular v11.2.0
- Electron v11.2.0
- SQLite v^5.0.2
- TypeOrm v^0.2.32

With this sample, you can:

- Run your app in a local development environment with Electron & Hot reload
- Run your app in a production environment
- Package your app into an executable file for Linux, Windows & Mac

## Mods Made

The main modification made on the [original project](https://github.com/maximegris/angular-electron) is the location of the electron main process code. This code is now located inside an `electron` folder, created on the project root. All the necessary changes were made to support this modification. The compiled electron code was put in `./dist/electron-out-tsc`.

I also modified the build procedure according to <https://malcoded.com/posts/angular-desktop-electron/>. Now the [tsconfig.json](tsconfig.json) on the root controls the Angular build, and the [tsconfig-serve.json](tsconfig-serve.json) controls the electron code build. I was having a lot of bugs in the [original project](https://github.com/maximegris/angular-electron) way of build, and this isolation solved all the issues. All the build scripts were altered accordingly.

I also added SQLite and TypeORM on this boiler plate.

Another modification is the use of local versions of Angular, Electron ans Type Script only. In other words, there is no global version installed for this components. All the pertinent scripts changes were made to support this scenario.

Finally, I put a `.nvmrc` file into the project, to support the use of [nvm](https://github.com/nvm-sh/nvm) to allow various versions of node and npm installed simultaneously.

If you want to learn more about more about how to use multiple node, Angular, etc. version in your environment, I recommend the article [How to run multiple Node and Angular versions simultaneously](https://levelup.gitconnected.com/how-to-run-multiple-node-and-angular-versions-simultaneously-1f58e6d150de).

I'm using the AGPL 3 license here, instead of MIT, used by the [original project](https://github.com/maximegris/angular-electron).

For a complete list of changes, please see the file [CHANGELOG.md](CHANGELOG.md).

## Status

I'm still testing it, so, no warranties here! XD

## Getting Started (based on the [original project](https://github.com/maximegris/angular-electron))

Clone this repository locally

Install dependencies with npm:

``` bash
npm install
```

There is an issue with `yarn` and `node_modules` that are only used in electron on the backend when the application is built by the packager. Please use `npm` as dependencies manager.

If you want to generate Angular components with Angular-cli , you **MUST** use nvm. Please see the article [How to run multiple Node and Angular versions simultaneously](https://levelup.gitconnected.com/how-to-run-multiple-node-and-angular-versions-simultaneously-1f58e6d150de).

## To build for development (based on the [original project](https://github.com/maximegris/angular-electron))

- **in a terminal window** -> `npm start`

Voila! You can use your Angular + Electron app in a local development environment with hot reload !

The application code is managed by `./electron/main.ts`. In this sample, the app runs with a simple Angular App (http://localhost:4200) and an Electron window.
The Angular component contains an example of Electron and NodeJS native lib import.
You can disable "Developer Tools" by commenting `win.webContents.openDevTools();` in `./electron/main.ts`.

## Debuging

We have a launcher for debug the main proccess inside vscode. The launcher has the name `Debug Main Process` and can be found inside the vscode debug tab.

## Included Commands (based from the [original project](https://github.com/maximegris/angular-electron))

|Command|Description|
|--|--|
|`npm start`| Execute the app in dev environment loading Angular from `http://localhost:4200`. Changes on source are automatically reloaded |
|`npm run start:local` | Execute the app in dev environment loading Angular from build. Changes on source are NOT automatically reloaded |
|`npm run ng:serve:web`| Execute the app in the browser (dev environment) |
|`npm run build`| Build the app in dev environment. Your Angular built files are in the `/dist` folder and the electron built files are in the `/electron/dist` folder. |
|`npm run build:prod`| Build the app in prod environment. Your Angular built files are in the `/dist` folder and the electron built files are in the `/electron/dist` folder. |
|`npm run electron:linux`| Builds your application and creates an app consumable on linux system |
|`npm run electron:windows`| On a Windows OS, builds your application and creates an app consumable in windows 32/64 bit systems |
|`npm run electron:mac`|  On a MAC OS, builds your application and generates a `.app` file of your application that can be run on Mac |

**Your application is optimized. Only /dist folders and node dependencies are included in the executable.**

## You want to use a specific lib (like rxjs) in electron main thread ? (based on the [original project](https://github.com/maximegris/angular-electron))

You can do this! Just by importing your library in npm dependencies (not devDependencies) with `npm install --save`. It will be loaded by electron during build phase and added to the final package. Then use your library by importing it in `./electron/main.ts` file. Easy no ?

## Browser mode (copied from the [original project](https://github.com/maximegris/angular-electron))

Maybe you want to execute the application in the browser with hot reload ? You can do it with `npm run ng:serve:web`.
Note that you can't use Electron or NodeJS native libraries in this case. Please check `providers/electron.service.ts` to watch how conditional import of electron/Native libraries is done.
