# Angular6
## Some common commands
### ng-new

```
ng new my-app
```
### ng-serve -- start development tool

```
ng serve --port 3000 --open
```
The Angular development tools include a feature that automatically updates the browser when there is
a change in the project. As soon as you save the index.html file, the server will detect the change and update
the application, reflecting the new content.


## Some keywords
### export
The export keyword relates to JavaScript modules. When using modules, each TypeScript or JavaScript
file is considered to be a self-contained unit of functionality, and the export keyword is used to identify
data or types that you want to use elsewhere in the application. JavaScript modules are used to manage the
dependencies that arise between files in a project and avoid having to manually manage a complex set of
script elements in the HTML file. See Chapter 7 for details of how modules work.

### import
```
import { Component } from "@angular/core";
import { Model } from "./model";
```

The first import statement is used in the Listing to load the @angular/core module, which contains
the key Angular functionality, including support for components. When working with modules, the import
statement specifies the types that are imported between curly braces. In this case, the import statement is
used to load the Component type from the module. The @angular/core module contains many classes that
have been packaged together so that the browser can load them all in a single JavaScript file.
The second import statement is used to load the Model class from a file in the project. The target for this
kind of import starts with ./, which indicates that the module is defined relative to the current file.
Notice that neither import statement includes a file extension. This is because the relationship between
the target of an import statement and the file that is loaded by the browser is managed by a module loader,
which I configure in the “Putting the Application Together” section.

### decorator
```
@Component({
selector: "todo-app",
templateUrl: "app.component.html"
})
```

function: 
1. provides metadata about a class
2. tells Angular that this is a component
3. provides configuration information through its properties like selector and templateUrl
 3.1 The selector property specifies a CSS selector that matches the HTML element to which the component will be applied
 3.2 The templateUrl property is to specify the component’s template location
