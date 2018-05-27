
# Description 
Use NPM in my Javascript project

# Author 
Naor Bar

# Date 
May, 2018

#### This is based on this blog:
https://medium.com/jeremy-keeshin/hello-world-for-javascript-with-npm-modules-in-the-browser-6020f82d1072

## Step 1:
Use "npm init" command will create my initial package.json file in this folder
 
## Step 2: 
Install two modules:

    npm install --save arithmetic
    npm install --save repeat-string

This will update package.json and add folder "node_modules" with the new modules

## Step 3:
Create a index.js with some js code based on the packages I've installed... 
e.g.
    
    var repeat = require("repeat-string");
    console.log(repeat("hey", 100));
    document.write(repeat("hey", 10));

## Step 4: 
Run the index.js:

    C:\NAOR\my-simple-npm-project>node index.js
    heyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyheyhey

## Step 5: 
Create a sample index.html which uses *index.js* and try to open with a browser:

    <h1>Simple Web Page</h1>
    <script src="index.js"></script>

As you can see it doesn't work! I need to browserify the nodejs code first!!!!
Console error:

    index.js:1 Uncaught ReferenceError: require is not defined

## Step 6: 
Use browserify to convert my nodejs code with the relevant modules into client side code
need to install browserify first:
    
    npm install -g browserify

and now run:

    browserify index.js -o bundle.js

The output is bundle.js file

## Step 7: 
Edit the index.html to now use the *bundle.js* and try to open with a browser:

    <h1>Simple Web Page</h1>
    <script src="bundle.js"></script>

Now it works!!! 
