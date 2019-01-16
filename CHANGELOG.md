#1.0.0

* Actualization of electron to version 4.0.1.
* Actualization of angular to version 7.2.0.
* Actualization of typescript to version 3.2.2.
* Minor actualization to use the last compatible version of various packages.
* Added es2018 lib on tsconfig.json and tsconfig-server.json.
* Added "module": "commonjs", "importHelpers": true, "noImplicitAny": true, "strictNullChecks": true, "noEmitOnError": true configurations on tsconfig.json and tsconfig-server.json.
* Added envoronment variable ELECTRON_ENV=dev on electron:serve script on package.json.
* Exchange the original MIT license for the AGPL 3.
* Moved the electron code to ./electron folder.
* Put the compile electron code on ./dist/electron-out-tsc.



