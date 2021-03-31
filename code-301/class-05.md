# Heroku Deployment

![Heroku Deployment](https://camo.githubusercontent.com/915d1dcb60aa6acf9279f8492422c7d2763a3f9896c011069e1af211f9b22420/68747470733a2f2f7370696e2e61746f6d69636f626a6563742e636f6d2f77702d636f6e74656e742f75706c6f6164732f32303138303530383039313734312f6865726f6b752d6e6f64652d312e706e67)

## Set up

![heroku setup](https://camo.githubusercontent.com/f4496430cb7abb1fad1017d8ccde6d78a5750c0031bf3e366f76f9cee6cd6734/68747470733a2f2f777777302e6173736574732e6865726f6b752e636f6d2f6173736574732f706c6174666f726d2f6469616772616d2d313436386230313366373364363535643932613832373434303936393438376436346332653436393339386364303137383331303162663739643138616238612e706e67)

The Heroku CLI requires Git, the popular version control system. If you don’t already have Git installed, complete the following before proceeding:

Download and run the installer for your platform:

### macOS

using terminal

`$ brew install heroku/brew/heroku`

When installation completes, you can use the `heroku` command from your terminal.

Use the `heroku` login command to log in to the Heroku CLI:

```terminal
$ heroku login
heroku: Press any key to open up the browser to login or q to exit
 ›   Warning: If browser does not open, visit
 ›   https://cli-auth.heroku.com/auth/browser/***
heroku: Waiting for login...
Logging in... done
Logged in as waleed-afifi@windowslive.com
```

## Check you environment versions

```terminal
$ node --version
v12.16.3

$ npm --version
6.14.4

$ git --version
git version 2.17.0
```

## Prepare the app

![Prepare the app](https://camo.githubusercontent.com/a415e791768d4dd7ef79642d8fb57a4d99b643837698526e7e062d2c783b67e1/68747470733a2f2f696d672d612e7564656d7963646e2e636f6d2f636f757273652f373530783432322f323434373633305f376130655f322e6a7067)

To clone a local version of the sample application that you can then deploy to Heroku, execute the following commands in your local command shell or terminal:

```terminal
$git clone https://github.com/heroku/node-js-getting-started.git
$cd node-js-getting-started
```

You now have a functioning Git repository that contains a simple application as well as a `package.json` file, which is used by Node’s dependency manager.

## Deploy the app

In this step you will deploy the app to Heroku.

Create an app on Heroku, which prepares Heroku to receive your source code.

```terminal
$ heroku create
Creating sharp-rain-871... done, stack is heroku-18
http://sharp-rain-871.herokuapp.com/ | https://git.heroku.com/sharp-rain-871.git
Git remote heroku added
```

Now deploy your code:

```terminal
$ git push heroku master
Counting objects: 488, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (367/367), done.
Writing objects: 100% (488/488), 231.85 KiB | 115.92 MiB/s, done.
Total 488 (delta 86), reused 488 (delta 86)
remote: Compressing source files... done.
remote: Building source:
remote:
remote: -----> Node.js app detected
remote:
remote: -----> Creating runtime environment
remote:
remote:        NPM_CONFIG_LOGLEVEL=error
remote:        NODE_VERBOSE=false
remote:        NODE_ENV=production
remote:        NODE_MODULES_CACHE=true
remote:
remote: -----> Installing binaries
remote:        engines.node (package.json):  12.x
remote:        engines.npm (package.json):   unspecified (use default)
remote:
remote:        Resolving node version 12.x...
remote:        Downloading and installing node 12.16.3...
remote:        Using default npm version: 6.14.4
       ....
remote: -----> Build succeeded!
remote: -----> Discovering process types
remote:        Procfile declares types -> web
remote:
remote: -----> Compressing...
remote:        Done: 19M
remote: -----> Launching...
remote:        Released v3
remote:        http://sharp-rain-871.herokuapp.com deployed to Heroku
remote:
remote: Verifying deploy... done.
To https://git.heroku.com/nameless-savannah-4829.git
 * [new branch]      master -> master
```

`$ heroku ps:scale web=1`

`$ heroku open`
