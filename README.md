[![Angular Logo](https://www.vectorlogo.zone/logos/angular/angular-icon.svg)](https://angular.io/) [![Electron Logo](https://www.vectorlogo.zone/logos/electronjs/electronjs-icon.svg)](https://electronjs.org/)

[![License](https://img.shields.io/badge/License-AGPL--3-brightgreen.svg)](LICENSE.md)

[![Watch on GitHub][github-watch-badge]][github-watch]
[![Star on GitHub][github-star-badge]][github-star]
[![Tweet][twitter-badge]][twitter]

# Introduction

This project was created based on https://github.com/maximegris/angular-electron. Some modifications were made to adapt this project to my taste. I will list this mods soon. For complete info about this boilerplate, please go to the original [project](https://github.com/maximegris/angular-electron).

This project bootstraps and packages your project with Angular 7 and Electron (Typescript + SASS + Hot Reload) and SQLite (with TypeOrm) for creating Desktop applications.

Currently runs with:

- Angular v~7.2.0
- Electron v4.0.1
- Electron Builder v~20.36.2
- SQLite
- TypeOrm

With this sample, you can:

- Run your app in a local development environment with Electron & Hot reload
- Run your app in a production environment
- Package your app into an executable file for Linux, Windows & Mac

## Mods Made

The main modification made on the [original project](https://github.com/maximegris/angular-electron) is the location of the electron main proccess code. This code is now located inside an `electron` folder, created on the project root. All the necessary changes were made to support this modification. The compiled electron code was put in `./dist/electron-out-tsc` instead of the root of the project.

I also added SQLite and TypeORM on this boiler plate.

When running the app during development (usin npm strat - see the Included command section below), a node environment variable calles `ELECTRON_ENV` is created with the value `dev`, so if you want to write code that runs only in dev environment, you can test this variable. To see how this variable is created, see the `package.json` file, on the scripts section, and see the script electron:serve.

Finally, I'm using the AGPL 3 license here, instead of MIT, used by the [original project](https://github.com/maximegris/angular-electron).

For a complete list of chages, please see the file [CHANGELOG.md](CHANGELOG.md).

## Status

I'm still testing it, so, no warranties here! XD

## Getting Started (copied from the [original project](https://github.com/maximegris/angular-electron))

Clone this repository locally

Install dependencies with npm:

``` bash
npm install
```

There is an issue with `yarn` and `node_modules` that are only used in electron on the backend when the application is built by the packager. Please use `npm` as dependencies manager.


If you want to generate Angular components with Angular-cli , you **MUST** install `@angular/cli` in npm global context.
Please follow [Angular-cli documentation](https://github.com/angular/angular-cli) if you had installed a previous version of `angular-cli`.

On linux, do not forget to run the following command as `sudo`.

``` bash
npm install -g @angular/cli
```

## To build for development (based on the [original project](https://github.com/maximegris/angular-electron))

- **in a terminal window** -> npm start

Voila! You can use your Angular + Electron app in a local development environment with hot reload !

The application code is managed by `./electron/main.ts`. In this sample, the app runs with a simple Angular App (http://localhost:4200) and an Electron window.
The Angular component contains an example of Electron and NodeJS native lib import.
You can disable "Developer Tools" by commenting `win.webContents.openDevTools();` in `./electron/main.ts`.

## Included Commands (copied from the [original project](https://github.com/maximegris/angular-electron))

|Command|Description|
|--|--|
|`npm run ng:serve:web`| Execute the app in the browser |
|`npm run build`| Build the app. Your built files are in the /dist folder. |
|`npm run build:prod`| Build the app with Angular aot. Your built files are in the /dist folder. |
|`npm run electron:local`| Builds your application and start electron
|`npm run electron:linux`| Builds your application and creates an app consumable on linux system |
|`npm run electron:windows`| On a Windows OS, builds your application and creates an app consumable in windows 32/64 bit systems |
|`npm run electron:mac`|  On a MAC OS, builds your application and generates a `.app` file of your application that can be run on Mac |

**Your application is optimised. Only /dist folder and node dependencies are included in the executable.**

## You want to use a specific lib (like rxjs) in electron main thread ? (based on the [original project](https://github.com/maximegris/angular-electron))

You can do this! Just by importing your library in npm dependencies (not devDependencies) with `npm install --save`. It will be loaded by electron during build phase and added to the final package. Then use your library by importing it in `./electron/main.ts` file. Easy no ?

## Browser mode (copied from the [original project](https://github.com/maximegris/angular-electron))

Maybe you want to execute the application in the browser with hot reload ? You can do it with `npm run ng:serve:web`.
Note that you can't use Electron or NodeJS native libraries in this case. Please check `providers/electron.service.ts` to watch how conditional import of electron/Native libraries is done.

