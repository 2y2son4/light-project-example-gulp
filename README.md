# light-project-example-gulp

Example of build setup for a gulp-based 'light project': a Magnolia project built with light modules.

## Features

* Gets a collection of light modules from npm.
* Processes the webresources from all modules via a gulpfile. The default process is to concatonate the js and css files into build.js and build.css.


## Usage

* Clone this repository and rename it to your project name - and change the name in `package.json`.
* Add desired light modules to `dependencies` in `package.json`.
* Tune `gulpfile.js` as desired.
* Run `npm install` at project root.
* Run `npm run build` at project root.
* Processed light modules, and a new light module containing `build.js` and `build.css` are in `dist` directory which can be used as the magnolia resources directory.

## Explanation

Main gulp task grabs the dependencies and puts them in `src` directory.

Then it copies files from specific directories
It will also concatenate the **pre-compiled** CSS / JS into one
bigger file.

This way every dependency can use their own pre-processor, let it be
TypeScript, Sass, Coffeescript, Less, Stylus etc. and we don't have
to fix the gulp script as soon as we add another dependency or
something changes in the existing dependencies.

Dependencies (the Light Modules) for the build are defined in the
`dependencies` section of the `package.json`.
