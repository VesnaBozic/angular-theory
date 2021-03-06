# Client web applications with Angular

## Technologies : Angular, TypeScript, Node.js

### Installation

#### Node.js (Server side Language)

Download installer

 [**Installer**](https://nodejs.org/en/)
 
 #### Angular CLI (Command Line Interface)
 
  [**Documentation**](https://angular.io/docs)
 
 ```
 npm install -g @angular/cli
 ```
 
 ### Create Angular Project
 
 In folder where we want to create new angular application, open cmd
 
 ```
 ng new my-app
 ```
 
 ### Generating a component
 
 ```
 ng generate component new-component
 ```
 
 ### Generating a service 
 
 ```
 ng generate service my-new-service
 
 ```
 
 ### Generating a build
 
 ```
 ng build
 ```
 
 
 
 ### Run Angular App
 
 ```
 ng serve
 
```

### Running tests

```
ng test
ng e2e
```

### Linting

```
ng lint
```

## How to run app from command line 

```
npm start
```

# What is Angular?

Angular is a development platform, built on TypeScript. As a platform, Angular includes:

- A component-based framework for building scalable web applications

- A collection of well-integrated libraries that cover a wide variety of features, including routing, forms management, client-server communication, and more

- A suite of developer tools to help you develop, build, test, and update your code

***Typescript***  is a superset of JavaScript that offers excellent consistency. It is highly recommended, as it provides some syntactic sugar and makes the code base more comfortable to understand and maintain. Ultimately, TypeScript code compiles down to JavaScript that can run efficiently in any environment. 

***Single-Page Application*** are web applications that load once with new features just being mere additions to the user interface. It does not load new HTML pages to display the new page's content, instead generated dynamically. This is made possible through JavaScript's ability to manipulate the DOM elements on the existing page itself. A SPA approach is faster, thus providing a seamless user experience. 

# Angular big Picture

- Modules

- Routes

- Components

- Services

## Modules 

Modules export things that other modules can import

### @NgModules

Provides organization at framework level. This allows us to tell Angular how to configure itself so that it knows what exist and how it needs to fit together. Modules are really nothing more then a logical grouping or a division mechanism to divide and segment pieces of our application.

***declarations*** define view classes that are available to the module

***imports*** define a list of modules that the module needs

***providers*** define a list of services that module makes available

***exports*** define a list of modules the module makes available

***bootstrap*** defines the component that shoul be bootstraped


## Routes

Allows us to navigate from one module to the other. In it simplest form contains a ***path*** and ***component*** reference. Once that pattern has been or that part has been matched via pattern matching then it pulls in and says I'm going to load this component as a result of that.

Components are loaded into the ***router-outlet*** directive

We can navigate to routes using the ***routerLink*** directive

The router uses ***history.pushState*** which means we need to set a ***base-ref*** tag to our ***index.html*** file

Routing table is evalueted from top to bottom. Order does matter. 

## Components

***Components are the building blocks that compose an application.***

Components are the atomic building block of Angular applications. Inside of component there is kind of two separate things that are happening inside of component conceptually. 

Component includes HTML template, TypeScript class nad styles. 

- Component are just ES6 classes. And when you define a property on a component class  or a method that becomes available to your template to bind or to execute

- Properties and methods of the component class are available to the template

- Providers (Services) are injected in the constructor

- The component lifecycle is exposed with hooks. Within a component you have a number of events that happen within the lifespan of a component.

Here is a minimal Angular component. 

```
import { Component } from '@angular/core';

@Component({
  selector: 'hello-world',
  template: `
    <h2>Hello World</h2>
    <p>This is my first component!</p>
  `
})
export class HelloWorldComponent {
  // The code in this class drives the component's behavior.
}
```

To use this component, you write the following in a template:

```
<hello-world></hello-world>
```

When Angular renders this component, the resulting DOM looks like this:

```
<hello-world>
    <h2>Hello World</h2>
    <p>This is my first component!</p>
</hello-world>

```

## Templates

Angular Templates are written with HTML that contains Angular-specific elements and attributes. In combination with the model and controller's information, these templates are further rendered to provide a dynamic view to the user.

A template is a HTML with some Angular pieces in it that tells Angular how to render a component.

You define this template either inline or by file path.

Templates include data bindings as well as it allows us to embed other components as children into our parent componenta and directives

Angular leverages native DOM events and properties which dramatically reduces the need for a ton of built-in directives

Angular leverages shadow DOM to do some really interesting things with view encapsulation

We can define styles on the component level.

Angular extends HTML with additional syntax that lets you insert dynamic values from your component. Angular automatically updates the rendered DOM when your component???s state changes. One application of this feature is inserting dynamic text, as shown in the following example.

We use of double curly braces--they instruct Angular to interpolate the contents within them.

```
<p>{{ message }}</p>
```

The value for message comes from the component class:

```
import { Component } from '@angular/core';

@Component ({
  selector: 'hello-world-interpolation',
  templateUrl: './hello-world-interpolation.component.html'
})
export class HelloWorldInterpolationComponent {
    message = 'Hello, World!';
}
```

When the application loads the component and its template, the user sees the following:

```
<p>Hello, World!</p>
```

Angular also supports property bindings, to help you set values for properties and attributes of HTML elements and pass values to your application's presentation logic.

We use the square brackets--that syntax indicates that you're binding the property or attribute to a value in the component class.

```

<p
  [id]="sayHelloId"
  [style.color]="fontColor">
  You can set my color in the component!
</p>
```

Declare event listeners to listen for and respond to user actions such as keystrokes, mouse movements, clicks, and touches. You declare an event listener by specifying the event name in parentheses:

```
<button
  type="button"
  [disabled]="canClick"
  (click)="sayMessage()">
  Trigger alert message
</button>

```

The preceding example calls a method, which is defined in the component class:

```
sayMessage() {
  alert(this.message);
}
```
#### Directives 


Additional functionality we add through the use of directives. Use directives to perform a variety of tasks, such as dynamically modifying the DOM structure. And create your own custom directives to create great user experiences.

Directives are attributes that allow the user to write new HTML syntax specific to their applications. They execute whenever the Angular compiler finds them in the DOM. Angular supports three types of directives.  

- Component Directives
- Structural Directives
- Attribute Directives 

#### Dependency injection

Dependency injection lets you declare the dependencies of your TypeScript classes without taking care of their instantiation. Instead, Angular handles the instantiation for you. This design pattern lets you write more testable and flexible code. Even though understanding dependency injection is not critical to start using Angular, we strongly recommend it as a best practice and many aspects of Angular take advantage of it to some degree.

## Metadata

Via metadata the template and the class they know about each other. This allows Angular to process the class, process the template and put this together into kind of a single coherent unit. 

Metadata allows Angular to process class. The most popular directives in Angular are *ngIf and *ngFor. Use directives to perform a variety of tasks, such as dynamically modifying the DOM structure. And create your own custom directives to create great user experiences.

We can attach ,etadata with TypeScript using decorators

Decorators are just functions

Most common is the @Coponent() decorator

Takes a config option with the selector, templateUrl, styles, styleUrls, animations, etc

## Data Binding

Enables data to flow from the component to template and vice-versa.

Includes interpolation, property binding, event binding, and two way binding (Property binding and event binding combined)

The binding syntax has expanded but the resulat is a much smaller framework footprint

We use data binding in web pages that contain interactive components such as forms, calculators, tutorials, and games.

Angular uses the two-way binding. Any changes made to the user interface are reflected in the corresponding model state. Conversely, any changes in the model state are reflected in the UI state. This allows the framework to connect the DOM to the Model data via the controller. However, this approach affects performance since every change in the DOM has to be tracked. 

## Services

A service is generally just a class

Should only do one specific thing

Takes the burden od business logic out of components

It is considered best practice to alaways use @Injectable so that metadata is generated correctly

By using the provideIn: 'root' property, we are specifying that Angular shoul provide that service to the root: injector.

## Angular CLI

The Angular CLI is a command-line interface tool that you use to initialize, develop, scaffold, and maintain Angular applications directly from a command shell.

With Angular CLI we can generate aplication skeleton. 

A newly generated application contains the source files for a root module, with a root component and template. Each application has a src folder that contains the logic, data, and assets.

You can edit the generated files directly, or add to and modify them using CLI commands.

```ng build``` - 	Compiles an Angular app into an output directory.
```ng serve```	- Builds and serves your application, rebuilding on file changes.
```ng generate``` -	Generates or modifies files based on a schematic.
```ng test``` -	Runs unit tests on a given project.
```ng e2e``` -	Builds and serves an Angular application, then runs end-to-end tests.

## First-party libraries

Are architectural elements you'll use when building Angular applications.

Some of the libraries available to you include:

***Angular Router***	Advanced client-side navigation and routing based on Angular components. Supports lazy-loading, nested routes, custom path matching, and more.

***Angular Forms***	Uniform system for form participation and validation.

***Angular HttpClient***	Robust HTTP client that can power more advanced client-server communication.

***Angular Animations***	Rich system for driving animations based on application state.

***Angular PWA	Tools*** for building Progressive Web Applications (PWAs) including a service worker and Web app manifest.

***Angular Schematics***	Automated scaffolding, refactoring, and update tools that simplify development at large scale.


## How we build Angular applications

With components. Components define areas of responsibility in the UI that let you reuse sets of UI funcionality.

A component consist of three things :

- ```A component class``` that handles data and functionality.
- ```An HTML template``` that determines the UI.
- ```Component-specific styles``` that define the look and feel.

```<app-root>``` ???the first component to load and the container for the other components.


## Decorators 

Decorators are a design pattern or functions that define how Angular features work. They are used to make prior modifications to a class, service, or filter. Angular supports four types of decorators, they are:

- Class Decorators
- Property Decorators
- Method Decorators
- Parameter Decorators

## Anotations 

Annotations in Angular are used for creating an annotation array. They are the metadata set on the class that is used to reflect the Metadata library.

## Ahead-of-time compilation

The Ahead-of-time (AOT) compiler converts the Angular HTML and TypeScript code into JavaScript code during the build phase, i.e., before the browser downloads and runs the code.

Some of its advantages are as follows. 

- Faster rendering
- Fewer asynchronous requests
- Smaller Angular framework download size
- Quick detection of template errors
- Better security

## Pipes

Pipes are simple functions designed to accept an input value, process, and return as an output, a transformed value in a more technical understanding. Angular supports several built-in pipes. However, you can also create custom pipes that cater to your needs. 

Some key features include: 

- Pipes are defined using the pipe ???|??? symbol. 
- Pipes can be chained with other pipes.
- Pipes can be provided with arguments by using the colon (:) sign.


## Filters 

Filters are used to format an expression and present it to the user. They can be used in view templates, controllers, or services. Some inbuilt filters are as follows. 

***date*** - Format a date to a specified format.

***filter*** - Select a subset of items from an array.

***Json*** - Format an object to a JSON string.

***limitTo*** -  Limits an array/string, into a specified number of elements/characters.

***lowercase*** - Format a string to lowercase


















