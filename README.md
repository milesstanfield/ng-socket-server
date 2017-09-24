# NgSocketServer

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.4.3.

- `ng new ng-socket-server && cd ng-socket-server`
- `yarn install`
- add script in package.json `"heroku-postbuild": "ng build --target=production --environment=prod --aot=true"`
- add engines in package.json
```
},
"engines": {
  "node": "6.9.0",
  "yarn": "1.0.2"
},
```
- download server.js `curl -o ./server.js https://raw.githubusercontent.com/milesstanfield/ng4-sockets/master/server.js`
- add dependencies `yarn add express method-override compression --dev`
- create procfile for heroku `touch Procfile && echo "web: node server.js" > Procfile`
- Add the cli and cli/compiler dependencies so they can be used in the npm build scripts. `yarn remove @angular/cli @angular/compiler-cli; yarn add @angular/cli@latest @angular/compiler-cli@latest`
