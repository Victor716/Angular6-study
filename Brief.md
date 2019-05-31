# Angular6
## Some common commands
### ng-new -- create a new application

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

### ng-lint 
```
ng lint
```
Check the project source
code for common errors and
formatting issues

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


### class
```
export class AppComponent {
 model = new Model();
 getName() {
 return this.model.user;
 }
}
```

### ng-module
```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
@NgModule({
 declarations: [AppComponent],
 imports: [BrowserModule],
 providers: [],
 bootstrap: [AppComponent]
})
export class AppModule { }
```
### bootstrap file main.ts 
```
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app/app.module';
import { environment } from './environments/environment';
if (environment.production) {
 enableProdMode();
}
platformBrowserDynamic().bootstrapModule(AppModule)
.catch(err => console.log(err));
```
This file is only for browser-based platform.

Calling the platformBrowserDynamic().bootstrapModule method is for browser-based applications,
which is what I focus on in this book. If you are working on different platforms, such as the Ionic mobile
development framework, then you will have to use a different bootstrap method specific to the platform you are
working with. The developers of each platform that supports Angular provide details of their platform-specific
bootstrap method.

### Round-trip

The browser requests an initial
HTML document from the server. User interactions—such as clicking a link or submitting a form—led the
browser to request and receive a completely new HTML document. In this kind of application, the browser
is essentially a rending engine for HTML content, and all of the application logic and data resides on the
server. The browser makes a series of stateless HTTP requests that the server handles by generating HTML
documents dynamically.

### Comparing Angular to React and Vue.js

The main difference between these frameworks is the developer experience. Angular requires you
to use TypeScript to be effective, for example. If you are used to using a language like C# or Java, then
TypeScript will be familiar and avoids dealing with some of the oddities of the JavaScript language. Vue.js
and React don’t require TypeScript but lean toward mixing HTML, JavaScript, and CSS content together in a
single file, which not everyone enjoys.

### ANGULAR VS. ANGULARJS

The original AngularJS was popular but awkward to use and required developers to deal with some
arcane and oddly implemented features that made web application development more complex than it
needed to be. Angular, starting with Angular 2 and continuing to the Angular 6 release described in this
book, is a complete rewrite that is easier to learn, is easier to work with, and is much more consistent. It
is still a complex framework, as the size of this book shows, but creating web applications with Angular
is a more pleasant experience than with AngularJS.
