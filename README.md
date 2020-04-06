# Configuring Babel API

Firstly, into the package manager JavaScript - Yarn, we will open a session to create a JSON package that will configure and manage dependencies of the application.

The commando do create a JASON Package in yarn pm is:

    yarn init

After that, you will see in terminal, questions, and you can press enter for all, up until show the message of "Done!".

The correct way to do the steps above is, before codding, you create a folder to save the JSON package, where will be saved the package.json file.

Now, after the code you will see in the folder the package.json file, like that:

![jsoninfolder2](https://user-images.githubusercontent.com/62850277/78591788-5d6b0900-781a-11ea-8f3e-561b1eb04d7d.png)


You can see, the package.json file is in the "course-es6" folder, this happens because I wrote the code in a selected repository at prompt.

## Babel installing (dependency yarn)

To install Babel, I have to add a dependency babel to package.json with the following code:

    yarn add @babel/cli

if you open the "course-es6" folder/package.json you can see:

    "dependencies": {
        "@babel/cli": "^7.8.4",

the babel/cli isn't the only dependency what has to be added, and we have to add two more:

- @babel/preset-env
- @babel/core

   yarn add @babel/preset-env

and

    yarn add @babel/core

Then automatically, the dependencies are updated.

    "dependencies": {
        "@babel/cli": "^7.8.4",
        "@babel/core": "^7.9.0",
        "@babel/preset-env": "^7.9.0"
      },

The babel/preset-env will get for the code a feature to recognize what is the running ambient of application. For that, you must create in folder this file: ".babelrc".

In .babelrc:

    {
      //entende em que ambiente estou trabalhando, para isso serve o preset-env.
      "presets": ["@babel/preset-env"]
    }

Now, the application knows what is the ambient of the application, in this case, is the chrome browser. OK!!

With the dependencies of babel added, I must add a script in package.json for the babel convert the updated code ECMA(n) in a browser version ECMA(n) code.

Follow the code(in package.json):

    "scripts": {
        "dev": "babel ./main.js -o ./bundle.js -w"
      }

The above code does that:

Catch my code, in this case, my code file is main.js, and with the "-o", the babel, has create a new code file with name "bundle.js". This new file contains the converted code for my current ambient of application, the browser, and your ECMA script version. The next part of code is "-w", it will enable a right now actualization of code in bundle.js in accord of changes did in main.js code.

After defining the script, run the following code:

    yarn dev

"dev" is the name of the script that I was created.

In the folder, you can see, bundle.js was created, and this is the script what you must put in HTML body:

    <script src="bundle.js"></script>-

Now, finally, your code is running in whatever browser and your own ECMAScript version.