# wp4-build-system
Using Webpack 4 for development
## Webpack installation
Before installing webpack first we need to install node and npm: see docs
The version that I am using for this demo is Node version 10.17.0 and NPM version 6.4.1
## Requirements
- Node & NPM
- Git (VCS)
Create a directory for your project and cd into it....
On MAC or Linux OS run the following command --
```
mkdir project_name && cd $_

```
If you are using oh-my-zsh you can do it in one step by simply running the command

```
take project_name

```
This will create a directory project_name and cd into it.
run the following command
```
npm init -y
```
the -y option tells the npm not to prompt you for questions, if you want answer the question please feel free to remove the -y option.

At the root of your directory create another folder called src.
By default webpack will look inside this directory for the index.js file to run.
Create a file called index.js in the src directory
Our project_name directory looks like this:
```

project_name
├── LICENSE
├── package.json
├── README.md
└── src
    └── index.js
```
To install webpack simply run the command
```
npm install --save-dev webpack
npm install ---save-dev webpack-cli
```
--
This will install webpack

### Webpack configuration
Create a file named webpack.config.js at the root of your directory and add the the following line of code.

```javascript
const webpack = require("webpack");
module.exports = {
  // output configuration options
  output: {
    filename: "bundle.js"
  }
};

```
Now when we run webpack command again we see that it runs with a configuration warning --

This is because our config mode has not been set.

To set the config mode option:

Add the following line to your script section of your package.json file

```json
"webpack": "webpack",
"dev": "npm run webpack -- --mode development",
"prod": "npm run webpack -- --mode production",

```
Update your webpack.config.js file to include mode option

```javascript
const webpack = require("webpack");
mode: "node"
module.exports = {
  // output configuration options
  output: {
    filename: "bundle.js"
  }
};
