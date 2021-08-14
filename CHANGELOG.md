## 0.0.4

* Electron version actualization to version 11.2.0.
* Angular version actualization o version 11.2.0.
* Typescript version actualization to version 4.0.5.
* SQLite version actualized to version 5.0.2.
* TypeORM version actualized to version 0.2.32.
* Minor actualization to use the last compatible version of various packages.
* Introduction of nvm and local versions of Angular, Electron and Type Script (instead of global ones).

## 0.0.3

* Electron version actualization to version 6.0.12.
* Angular version actualization o version 8.2.10.
* Typescript version actualization to version 3.5.3.
* SQLite version actualized to version 4.1.0.
* TypeORM version actualized to version 0.2.19.
* Minor actualization to use the last compatible version of various packages.

## 0.0.2

* Angular version actualized to version 8.1.1.
* Electron version actualized to version 5.0.7.
* Typescript version actualization to version 3.4.5.
* SQLite version actualized to version 4.0.9.
* TypeORM version actualized to version 0.2.18.
* Minor actualization to use the last compatible version of various packages.
* The tsconfig-server.json solution was restored (removing the tsconfig.json from the ./electron folder), but the output folders were changed and the include parameters were altered.
* The scripts on package.json were restructured.

## 0.0.1

* Electron version actualization to version 4.0.1.
* Angular version actualization o version 7.2.0.
* Typescript version actualization to version 3.2.2.
* Minor actualization to use the last compatible version of various packages.
* Added SQLite and TypeOrm to the template.
* Added es2018 lib on tsconfig.json.
* Added "module": "commonjs", "importHelpers": true, "noImplicitAny": true, "strictNullChecks": true, "noEmitOnError": true configurations on tsconfig.json.
* Added environment variable ELECTRON_ENV=dev on electron:serve script on package.json.
* Exchange the original MIT license for the AGPL 3.
* Moved the electron code to ./electron folder.
* Added @types for electron, sqlite3.
* The build process was altered. The tsconfig-server.json was removed and a tsconfig.json was created inside the ./electron folder. The scripts in package.json were altered accordingly.
* Create a debug launch configuration for debug main process with vscode.
