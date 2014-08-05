# Default Tasks

### Overview

The asset pipeline bundled in Sails is a set of Grunt tasks designed to make you more consistent and productive. The entire workflow is completely customizable, but it comes ready with out of the box default. Sails makes it easy to [configure new tasks](/#/documentation/concepts/Assets/TaskAutomation.html?q=task-configuration) to fit your needs.

Here are a few things that the default Grunt configuration in Sails does:  
- Automatic LESS compilation
- Automatic JST compilation
- Automatic Coffescript compilation
- Optional automatic asset injection, minification, and concatenation
- Creation of a web ready public directory
- File watching and syncing
- Optimization of assets in production

### Default Grunt Task Behavior.

Below are the Grunt tasks that are included by default in your Sails project as well as a description of their behaviour.

##### clean

> This grunt task is configured to clean out the contents of the `.tmp/public/` directory.

> [usage docs](https://github.com/gruntjs/grunt-contrib-clean)

##### coffee

> Compiles CoffeeScript files from `assest/js/` and places them in the `.tmp/public/js/` directory.

> [usage docs](https://github.com/gruntjs/grunt-contrib-coffee)

##### concat

> Concatenates Javascript and CSS files, and saves the concatenated files in the `.tmp/public/concat/` directory.

> [usage docs](https://github.com/gruntjs/grunt-contrib-concat)

##### copy

> **dev task config**
> Copies all directories and files, except CoffeScript and LESS files, from the assets folder into the `.tmp/public/` directory.

> **build task config**
> Copies all directories and files from the .tmp/public directory into a new www directory.

> [usage docs](https://github.com/gruntjs/grunt-contrib-copy)

##### cssmin

> Minifies css files and places them in th `.tmp/public/min/` directory.

> [usage docs](https://github.com/gruntjs/grunt-contrib-cssmin)

##### jst

> Precompiles Underscore templates to a `.jst` file. (in other words, converts HTML templates into Javascript functions). This can speed up template rendering on the client, and reduce bandwidth usage.

> [usage docs](https://github.com/gruntjs/grunt-contrib-jst)

##### less

> Compiles LESS files. Only the `assets/styles/importer.less` file is compiled. This allows you to control the ordering yourself, i.e. import your dependencies, mixins, variables, resets, etc. before other stylesheets.

> [usage docs](https://github.com/gruntjs/grunt-contrib-less)

##### sails-linker

> Automatically injects tags for Javascript and CSS files into your views, in addition to any Underscore templates you created. A much more detailed description of this task can be found [here](https://github.com/balderdashy/sails-generate-frontend/blob/master/docs/overview.md#a-litte-bit-more-about-sails-linking). This task injects the tags between `<!--SCRIPTS--><!--SCRIPTS END-->` and `<!--STYLES--><!--STYLES END-->` comments. These are included in the default **views/layout.ejs** file in a new Sails project. If you don't want to use the linker for your project, you can simply remove those tags.

> [usage docs](https://github.com/Zolmeister/grunt-sails-linker)

##### sync

> A grunt task to keep directories in sync. It is very similar to grunt-contrib-copy but tries to copy only those files that have actually changed. It specifically synchronizes files from the `assets/` directory to `.tmp/public/`, overwriting anything that's already there.

> [usage docs](https://github.com/tomusdrw/grunt-sync)

##### uglify

> Minifies client-side Javascript assets.

> [usage docs](https://github.com/gruntjs/grunt-contrib-uglify)

##### watch

> Runs predefined tasks whenever a watched file is added, changed or removed. Automatically watches for changes on files in the `assets/` directory, and re-runs the appropriate tasks (like LESS and JST compilation). This allows you to see changes to your assets without having to restart the Sails server.

> [usage docs](https://github.com/gruntjs/grunt-contrib-watch)

<docmeta name="uniqueID" value="DefaultTasks764297">
<docmeta name="displayName" value="Default Tasks">

