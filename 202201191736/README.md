# Create a React applcation without create-react-app
```create-react-app``` is a beast of a command; it allows developers to quickly
get up and running with React, without having to think about the technical
details. Because of its' approach however, it does come with a few flaws. It may
bloat your project by providing several out-of-the-box that your project does
not require. It also makes it difficult to add custom build configurations since
it hides what is installed under the hood. Finally, it also hides ***the
requirements*** of a React application from developers, making them dependent
on the tool.

## Setup
Go to directory where your projects live and create a new directory for your
project. You will also need some boiler-plate project structure to assist the
webpack tools in building your application. A bare-bones React app is structured
like so: 
```
.
│
├── package.json
│
├── package-lock.json
│
├── webpack.config.js
│
├── src
│   ├── index.html
│   │   
│   ├── index.js
│   │   
│   ├── components
│       ├── App.js
│
├── dist
│   ├── ... 
│
├── node_modules
│   ├── ... 
│

```
The following files/directories will be automatically generated during the
subsequent steps, so we do not need to manually create them:
* ```package.json```
* ```package-lock.json```
* ```webpack.config.js```
* ```node_modules/```
* ```dist/``` (this is the location of our production build)

Make sure to grab the ```barebones-react``` script from
[here](https://gitlab.com/michaelarn0ld/sh-scripts) if you don't already have
it. Now run these commands:
```bash
mkdir -p {YOUR_PROJECT_NAME}/src/components/ && cd {YOUR_PROJECT_NAME}

touch webpack.config.js src/index.{html,js} src/components/App.js

npm init -y &> /dev/null

barebones-react
```

Now, you must configure ```package.json``` so we can utilize the webpack
tools we just installed for development and production environments. Modify
the ```"scripts"``` from:

```
...
"scripts": {
    "test": "..."
}
...
```
to
```
...
"scripts": {
    "start": "webpack-dev-server --mode development --open --hot",
    "start": "webpack --mode production"
}
...
```

Add the following to ```webpack.congfig.js```:
```js
const path = requre('path');
const HTMLWebpackPlugin = require('html-webpack-plugin');

 module.exports = {                                                           
                                                                              
     entry: './src/index.js',                                                 
                                                                              
     output: {                                                                
         path: path.join(__dirname, './dist'),                                
         filename: 'bundle.js'                                                
     },                                                                       
                                                                              
     plugins: [                                                               
         new HTMLWebpackPlugin({                                              
             template: './src/index.html'                                     
         })                                                                   
     ],                                                                       
                                                                              
     module: {                                                                
         rules: [                                                             
             {                                                                
                 test: /.js$/,                                                
                 exclude: /node_modules/,                                     
                 use: {                                                       
                     loader: 'babel-loader',                                  
                     options: {                                               
                         presets: ['@babel/preset-env', '@babel/preset-react']
                     }                                                        
                 }                                                            
             }                                                                
         ]                                                                    
     }                                                                        
                                                                              
 }
```

Briefly, these configurations tell webpack that the root of the dependency graph
is at ```./src/index.js```, the build bundle will go to ```./dist/bundle.js```,
React will be injecting its code into file ```./src/index.html``` as the
template, and finally babel will transpile all javascript files except those with
```node_modules``` included in their path.

Time for some boilerplate in ```index.js```, ```index.html```, and ```App.js```:

### index.html
```html
<!DOCTYPE html>           
<html lang="en">          
<head>                    
    <meta charset="UTF-8">
    <title></title>       
</head>                   
<body>                    
   <div id="root"></div>  
</body>                   
</html>
```

### index.js
```js
import React from "react";
import ReactDOM from "react-dom";
import App from "./components/App";

ReactDOM.render(<App />, document.getElementById('root'));
```

### App.js
```js
import React from "react";

export default const App = () => {
    return (
    <div>
        <h1>Hello, React!</h1>
    </div>
    );
}
```

Finally, run ```npm start``` and then ```npm run build``` to make sure
everything works correctly!


## Related
[202110200109](../202110200109) - Clients, Servers, and the Web \
[202110200316](../202110200316) - Types in JavaScript \
[202110210320](../202110210320) - Semantic HTML Block Elements \
[202110210421](../202110210421) - Interesting Details of Inline HTML Elements \
[202110210445](../202110210445) - HTML Head Elements \
[202110210504](../202110210504) - HTML Media Elements \
[202110210536](../202110210536) - HTML Tables: Quick Tips \
[202110220323](../202110220323) - CSS Styling: Tables and Forms

## Tags
#webdev #react
