# Uniware

### Basic setup

##### Setting up frontend tools:
- install [brew](https://brew.sh/)
- brew install node
- npm install -g grunt
- npm install -g grunt-cli
- npm install -g bower

##### Setting up uniware
Go to project root then,
- npm install
- bower install
- brew install fontforge ttfautohint
- grunt devfiles

For starting localhost server:
- run `grunt start-cdn-server` from root directory

### How dependencies and libraries are installed and where they are kept?

- For installing dependencies we use npm (node package manager) and bower. 
- We use npm for dependencies that are used generally for the build process. For uniware those dependencies are mostly grunt plugins.
- Npm saves all the dependencies in the node_modules directory.
- As for libraries that are used on the working web application, for those libraries we use bower to install them. 
- Bower saves all the libraries in src/external directory. (This can be changed in .bowerrc file)


### What is grunt? What all things does it do?

Grunt is the task manager that we use in the project for various tasks. These are the following tasks:

- JS files: uglification, 
- General: clean, copy, concatenation
- CSS and images: css minification, sprite, sass to css, webfont
- Localhost server: cdn server, buildcdn server
- HTML2JSON

All the tasks are written in the Gruntfile.js file in the root directory.

Various grunt tasks can be grouped into a single task. The list of these tasks can be found near the end of the file using: `grunt.registerTask(‘groupedTaskName’, ‘task1’, ‘task2’)`

##### Tasks used for development:

`grunt devfiles`: This tasks is used for first time after a fresh pull. This runs the following tasks:  `html2json`, `svg2js`, `clean:css`, `sprite`, `sass`, `concat:css`

`grunt start-cdn-server`: This task starts a localhost server whose purpose is to server all the js files, css files, (not html files because all html files are compiled into template.js), svg files, font files etc. It also starts up a grunt watch task, that watches for any changes in js files, html files or scss files and re runs the suitable grunt tasks and refreshes the webpage.

`grunt webfont`: This is used when a new svg icon is added.

### Dev environment and production environment

To switch to dev environment

- go to /ui/dev, and check the debug box to true.
- in the input box `remoteJsServer`, enter: `http://localhost:5000` then click save and refresh. (Make sure it's http not https)

Working in dev environment which is having debug = true, allows files to be unbundled and are served from localhost rather than the actual cdn where the files go after build.

### What is choona.js? What does it do?

Choona.js is the framework used for our application that allows one to divide the whole application into modules that can be loaded inside an html element. This modules are completely independent of each other.

General structure of a module:
```javascript
define({
  "fileName": "testMod",
  "layer": "Module Layer",
  "dependency": ["jq", "_t"]
}).content(function(jq, _t) {
  "use strict";
  return {
    domEvents: {

    },
    sandboxEvents: {
    
    },
    start: function() {
      // start writing here
    },
    someMethod: function(){
    
    },
    end: function() {
      this.$$.off(); //detach all event listeners
    }
  };
});

```
### Step by step of how the application loads
- First of all `index.html` gets loaded where information such as cdn url, auth url are there.
- From index.html the first js file that loads is `initialPayload.js`.
- This contains the library `headjs` which is used for loading the js files and css files (adding them to script tag) and the logic for deciding the list of js files and css files that are to be loaded.
- After that the list of js files read from resource.json is loaded sequantially.

### How to add a new module corresponding to a new URL?

- Entry in resource.json
- Entry in iFrameRouter.js & URLService.js
- Any module can be opened using the url: `/module?m=moduleName`

### How to hit a new API endpoint and retrieve it's data and use it? Where is the list maintained?

- jQuery GET and POST is used.
- List of API endpoints maintained in DataLayer.js

### How SCSS and CSS files are organized?

### Global event system: publishing and subscribing event

### How HTML files are compiled into template.js 

### 2 way data binding: Rivetsjs

### AddEditModel

### SpreadSheet

### Datatable

### SubTabRouterModule
