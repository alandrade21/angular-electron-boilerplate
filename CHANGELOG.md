## 1.0.2

* Electron version actualization to version 6.0.10.
* Angular version actualization o version 8.2.8.
* Typescript version actualization to version 3.5.3.
* Minor actualization to use the last compatible version of various packages.

## 1.0.1

* Electron version actualization to version 5.0.7.
* Angular version actualization o version 8.1.1.
* Typescript version actualization to version 3.4.5.
* Minor actualization to use the last compatible version of various packages.

## 1.0.0

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
