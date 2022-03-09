# Client web applications

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

Components are the atomic building block of Angular applications. Inside of component there is kind of two separate things that are happening inside of component conceptually. We have template and we have class. 

- Component are just ES6 classes. And when you define a property on a component class  or a method that becomes available to your template to bind or to execute

- Properties and methods of the component class are available to the template

- Providers (Services) are injected in the constructor

- The component lifecycle is exposed with hooks. Within a component you have a number of events that happen within the lifespan of a component.


## Templates

A template is a HTML with some Angular pieces in it that tells Angular how to render a component

Templates include data bindings as well as it allows us to embed other components as children into our parent componenta and directives

Angular leverages native DOM events and properties which dramatically reduces the need for a ton of built-in directives

Angular leverages shadow DOM to do some really interesting things with view encapsulation

We can define styles on the component level


## Metadata

Via metadata the template and the class they know about each other. This allows Angular to process the class, process the template and put this together into kind of a single coherent unit. 

Metadata allows Angular to process class

We can attach ,etadata with TypeScript using decorators

Decorators are just functions

Most common is the @Coponent() decorator

Takes a config option with the selector, templateUrl, styles, styleUrls, animations, etc

## Data Binding

Enables data to flow from the component to template and vice-versa 

Includes interpolation, property binding, event binding, and two way binding (Property binding and event binding combined)

The binding syntax has expanded but the resulat is a much smaller framework footprint



## Services

A service is generally just a class

Should only do one specific thing

Takes the burden od business logic out of components

It is considered best practice to alaways use @Injectable so that metadata is generated correctly

By using the provideIn: 'root' property, we are specifying that Angular shoul provide that service to the root: injector






















