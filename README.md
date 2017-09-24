# NgSocketServer
A guide to creating an Angular + Socket.io server app hosted on Heroku
[Heroku app](https://sleepy-dawn-81766.herokuapp.com/)

- `ng new ng-socket-server && cd ng-socket-server`
- `yarn install`
- add script in package.json
```
"heroku-postbuild": "ng build --target=production --environment=prod --aot=true"
```
- add engines in package.json
```
},
"engines": {
  "node": "6.9.0",
  "yarn": "1.0.2"
},
```
- download server.js `curl -o ./server.js https://raw.githubusercontent.com/milesstanfield/ng4-sockets/master/server.js`
- add server.js dependencies `yarn add express method-override compression socket.io`
- create procfile for heroku `touch Procfile && echo "web: node server.js" > Procfile`
- Add the cli and cli/compiler dependencies so they can be used in the npm build scripts. `yarn remove @angular/cli @angular/compiler-cli; yarn add @angular/cli@latest @angular/compiler-cli@latest`
- create heroku app `heroku create`
- push to heroku `git push heroku master`
- scale up to 1 free web dyno `heroku ps:scale web=1; heroku restart`
- visit your app `heroku open`
