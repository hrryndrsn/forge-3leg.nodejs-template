# forge-3leg.nodejs-template

[![Node.js](https://img.shields.io/badge/Node.js-4.4.3-blue.svg)](https://nodejs.org/)
[![npm](https://img.shields.io/badge/npm-2.15.1-blue.svg)](https://www.npmjs.com/)
![Platforms](https://img.shields.io/badge/platform-windows%20%7C%20osx%20%7C%20linux-lightgray.svg)
[![License](http://img.shields.io/:license-mit-blue.svg)](http://opensource.org/licenses/MIT)

*Forge API*:
[![oAuth2](https://img.shields.io/badge/oAuth2-v1-green.svg)](http://developer-autodesk.github.io/)
[![Data-Management](https://img.shields.io/badge/Data%20Management-v1-green.svg)](http://developer-autodesk.github.io/)
[![OSS](https://img.shields.io/badge/OSS-v2-green.svg)](http://developer-autodesk.github.io/)
[![Model-Derivative](https://img.shields.io/badge/Model%20Derivative-v2-green.svg)](http://developer-autodesk.github.io/)
[![Viewer](https://img.shields.io/badge/Forge%20Viewer-v2.10-green.svg)](http://developer-autodesk.github.io/)

# Description

This template (or boiler plate) implements a basic infrastrucutre for [Autodesk Forge 3 Legged OAuth](https://developer.autodesk.com/en/docs/oauth/v2/tutorials/get-3-legged-token/) with NodeJS. 

# Setup

For using this sample, you need an Autodesk developer credentials. Visit the [Forge Developer Portal](https://developer.autodesk.com), sign up for an account, then [create an app](https://developer.autodesk.com/myapps/create). For this new app, use <b>http://localhost:3000/callback/autodesk</b> as Callback URL. Finally take note of the <b>Client ID</b> and <b>Client Secret</b>.

Install [NodeJS](https://nodejs.org) if you don't have yet.

Clone this project or download it. It's recommended to install GitHub desktop](https://desktop.github.com/). To clone it via command line, use the following (MacOSX/Linux, use the Terminal, on Windows use the Git Sheel):

    git clone https://github.com/augustogoncalves/forge-3leg.nodejs-template
    cd forge-3leg.nodejs-template
    
To run it, install the required packages, set the enviroment variables with your client ID & secret and finally start it. Via command line, use the following:

Mac OSX/Linux (Terminal)

    npm install
    export FORGE_CLIENT_ID=<<YOUR CLIENT ID FROM DEVELOPER PORTAL>>
    export FORGE_CLIENT_SECRET=<<YOUR CLIENT SECRET>>
    npm start

Windows (use <b>Node.js command line</b> from Start menu)

    npm install
    set FORGE_CLIENT_ID=<<YOUR CLIENT ID FROM DEVELOPER PORTAL>>
    set FORGE_CLIENT_SECRET=<<YOUR CLIENT SECRET>>
    npm start

Open the browser: [http://localhost:3000](http://localhost:3000).

## What's next?

Your application endpoint should be implemented at [/routes/app.js](/routes/app.js). Use the [Token](/routes/app.js) module to read the Public and Internal tokens. Only send Public token to the front-end, use the Internal token to perform server-side operations with Autodesk APIs.

Below is a small section of the app.js file. Replace the <br>get</b> and <b>your_end_point</b> with your own.

    // token handling in session
    var token = require('./token');

    router.get('/your_end_point', function (req, res) {
      var tokenSession = new token(req.session);

      // ToDo: implement your application here

    });

## Packages used

All Autodesk Forge NPM packages are included by default, see complete list of what's available at [NPM website](https://www.npmjs.com/browse/keyword/autodesk). Some other non-Autodesk packaged are used, including [express](https://www.npmjs.com/package/express) and its session/cookie middlewares ([express-session](https://www.npmjs.com/package/express-session) and [cookie-parser](https://www.npmjs.com/package/cookie-parser)) for user session handling. The front-end uses [bootsrap](https://www.npmjs.com/package/bootstrap) and [jquery](https://www.npmjs.com/package/jquery).

# Tips & tricks

For local development/testing, consider use <b>nodemon</b> package, which auto restart your node application after any modification on your code. To install it, use:

    sudo npm install -g nodemon

To use it, instead of <b>npm start</b>, use the following:

    nodemon server.js --ignore www/

Trick: the <b>--ignore</b> parameter indicates that the app should not restart if files under <b>www</b> folder are modified.

## Troubleshooting

After installing Github desktop for Windows, on the Git Shell, if you see a *error setting certificate verify locations* error, use the following:

    git config --global http.sslverify "false"

# License

This sample is licensed under the terms of the [MIT License](http://opensource.org/licenses/MIT).
Please see the [LICENSE](LICENSE) file for full details.

## Written by

Augusto Goncalves (Forge Partner Development)<br />
http://forge.autodesk.com<br />
