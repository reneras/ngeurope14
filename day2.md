![ngeurope](https://www.dropbox.com/s/do6pb6bw7zp66mk/ng-europe-horizontal-on-black.png?dl=1)
#Day 2


## 1. Miško Hevery - Keynote
@mhevery

Misko welcomes everybody and is very pleased to be here
Stresses the fact that we're not creating a new language with AtScript

Goes on posing the question: "Can we make the Angular API a bit more friendlier ?"
Advocating a bit more explicit API in order to improve readability in general.
Discussing the API in 2.0 and apoligizes for any inconvinience and ask for your input to improve things

Continues on talking about optional types and metadata.
- Typecasting: What if we could apply more typecasting in Angular ? Something that exists in ES4.
  - Possible way to go: generate assertions from e.g. <cssSelectors> similar like AngularDart
  - Nominal, Structural type systems.
- Metadata to tell your intentions
- Introspection to check things on runtime, prevents programming errors

> Angular is raising what a browser is.
Abstraction should empower a developer by providing a more declarative way of programming

__Why not build the future today ?__
>Chances are that types, annotation and introspection will end up in ES7 anyway.

__AtScript__  
built on top of TypeScript to include types & annotation.
`AtScript.wraps( TypeScript.wraps( ES6.wraps( ES5 ) ) )`

Note: Angular 2.0 will be written in AtScript, but won't require you to write anything in AtScript. If you want, you can still work in JavaScript (ES5)

__Roadmap__
- right now .ats files, in which the angular source is being written in, gets generated to ( using ATS on top of Traceur )Dart
- An ES5 version
- IDE support is coming, as IDE developers are very interested and most of them already support TypeScript, making AtScript support a lot easier to add
- This will enable static typing


__More about AtScript__  
[AtScript preliminar specification](https://docs.google.com/document/d/11YUzC-1d0V1-Q3V0fQ7KSit97HnZoKVygDxpWzEYW0U/mobilebasic?pli=1)  
[Q&A about AtScript](https://docs.google.com/document/d/1cUTD8oVzfpwFqX5tMxHTifKO8uJm5VddwmB0aVQMxpI/mobilebasic?pli=1)


## 2. Igor Minar & Tobias Bosch - Angular 2.0 Core
@igorminar

#### Let's compare 1.3.x and (for now the incomplete version) 2.0.

Showing a, yet another, Todo App. (For Santa! Huuuuge list, two categories: nice & naughty)
- HTML templating quite the same
- New syntax for binding to properties of DOM objects. No longer binding to attributes. (Subtle difference, attribute is what is defined in HTML, property is what is available in the runtime DOM object, there is a one-time mapping from attribute to property on DOM initialization)
- Databinding
- Joke on adding a shopping cart....
- R.I.P. controller & DDO & $scope & angular.module & jqLite ( 2009-2014 )

Showing [Web Tracing Framework](http://google.github.io/tracing-framework/), a more detailed profiling in Chrome when it comes to angular, more detailed than the current flamecharts built in Chrome profiling.  
Will be built later on in Chrome flamecharts.

## 3. Zack Brown - Famous Angular
[slides](http://thomasstreet.com/ngeurope)

__Why hasn't the Web taken over the mobile world ?__  
According to Zack:
- Performance
- Ease of wrapping
- Rich interactivity

>CSS has it's boundaries. We hit the "declaritive ceiling".

But then again, JavaScript also poses some performance challenges.

Bold claim
>Rich interactions which users expect from todays mobile apps – are fundamentally better suited to imperative animations than to declarative animations.

__What's on the horizon ?__
- because it's built from he ground up it can approach a more native way close to existing 3D technologies like openGL
- Deep webGL integration
- Integration with 2.0 using AtScript

__Demo time__  
https://github.com/zackbrown/sheets

Bind to a css selector to a function for run-time/imperative transformation of css and animate element

More info on [Famous Angular](https://github.com/Famous/famous-angular)

## 4. Douglas Duteil - Yet another way to animate in Angular

Takes us back to Angular 1.1.5 were he met ngAnimate
But that was cumbersome

Discussing the spec of [W3C Web animations](http://www.w3.org/TR/web-animations/)

Then he discovered that this wasn't in Angular yet. __"Challenge accepted"__

Demo time (link)

## 5. Martin Gontovnikas - Restangular 2.0: The future and beyond
@mgonto [slides](mgonto.github.io/restangular20-ngeurope-talk)


![programmer](https://raw.githubusercontent.com/mgonto/restangular20-ngeurope-talk/gh-pages/img/programming.gif)  
Before Restangular we had a lot of boilerplate.

__Proviously on Restangular__
- Shows the ng rollercoaster and eventually encounter $resource, with it's limitations and overhead needed to implement a proper RESTful API ![britney meme](url)
- So he started building this thing on top of $resource and discussing the main concept of [Restangular](url)

__Restangular in the future__  
Let's walk through the refactoring needed to move towards 2.0.
- Decoupling the one large Restangular.js file into seperate modules
- Using model classes
- Hooks: he's not sure about it yet
- Custom configuration

More info on [Restangular 2.0](https://github.com/mgonto/restangular/tree/2.0-wip)


## 6. Erik Arvidsson & Vojta Jína - ES6 in Angular 2.0
@erikarvidsson & @Vojtajina

__Why ES6 ?__
- Easier coding

[compatibility list of ES6 features](http://kangax.github.io/compat-table/es6)

__Classes__
- Today - a lot of boilerplate
- ES6 - Easier and shorter syntax in order to ease and remove some overhead while developing with classes, while still based on prototypes.

__Modules__
- Today: AMD / Commonjs
- ES6: No sync load, static deps, static val, cyclic deps

__This scope__
- Today: fn.bind(this);
- ES6: Arrow fn , will look outside of the scope for declarations

Default params
- Today: param || default
- ES6: parameter list

Continues on [Traceur](https://github.com/google/traceur-compiler)
> Traceur is a JavaScript.next-to-JavaScript-of-today compiler that allows you to use features from the future __today__.

Module syntax :
    `import {myModule} from './mymodule.js';`



## 7. Matias Niemelä - Animations (sequencer, web animations)

@yearofmoo

Discusses the basics of ngAnimate  
Demos on how ngAnimate actually works

__So, what's new in 1.3 for ngAnimate ?__
- promise based anis, but we need $apply when changing data
- fixes to transitions + keyframes
- fixes to ngshow / nghide - no need to apply display
- 3rd party staggering
- ng-animate-children – will go in depth later on
- Classes - combined and resolved to one aimation
- Inline styling
- shows a demo on a map :boom:
- In the demo the directive handles the logic and ngAnimate is responsible for the animation

What else ?
- What about (group) sequences ? Too messy if done in CSS

Shows demo of possible solution: ngAnimateLayout (ng-animate-sequence)


## 8. Lukas Ruebbelke - Be a Real Time Cage Dragon with AngularJS and Firebase

@simpulton

> Why are we here ? We love to create things.

Mentions "Lean Startup" by Eric Ries.
> I love everything that speeds me up

Firebase overview
> Backend as a service with realtime capability and a world class hosting solution that you can deploy in a second (NOW BY GOOGLE)

Shows Viewnicorn demo [code here](bit.ly/viewnicorn-code)

__[AngularFire](http://angularfire.com/)__

> official binding of Firebase endpoint with Angular Model to 3-way data-binding in realtime

Shows 3 demos [code here](http://bit.ly/viewnicorn-code)

Free Firebase account http://bit.ly/lukas-friend  
promo code: nglukas1 for 1 month production for free


## 9. Carmen Popoviciu & Pascal Precht - “Don’t stop thinking about tomorrow” - AngularJS and Web
@CarmenPopoviciu & @PascalPrecht
slides: http://slidedeck.io/PascalPrecht/dont-stop-thinking-about-tomorrow

Giving an overview of [web components](http://webcomponents.org)

Pascal
> Back in 2008 when Backbone.js was cool, we got some of these stuff for the first time

- HTML Templates
- Shadow DOM
- Custom elements
- HTML Imports

__But how does Angular deal with custom elements ? Binding?__
- Today you can use [ngBindPolymer](https://github.com/eee-c/angular-bind-polymer)  
- You can pass data from Angular to Web Components and vice versa using Mutation Observers and event listeners
- Showing [code](http://slidedeck.io/PascalPrecht/dont-stop-thinking-about-tomorrow)

__Discussing binding to properties and events__  
Tomorrow with AngularJS 2.0 you will use `[property]=...` and `(method)=...` binding to easly communicate between angular and a webcomponent

## 10. Marcy Sutton - AngularJS Accessibility
@marcysutton [slides](http://marcysutton.github.io/angular-a11y)

> Everyone can perceive, understand, navigate, and interact with the Web, and they can contribute to the Web.

Accessibility in Angular Apps

__Write meaningful HTML__
- Consists of roles, states and properties
- Enable the keyboard, else you will the panda gets angry...  
![](http://marcysutton.github.io/angular-a11y/img/keyboard-panda-1.gif)
- Handle focus. If you want to remove the blue outline, don't forget to replace it with something meaningful. Make the panda happy!
- Alert the user. By easily adding attributes you can alert the user about state changes (Logged in, new search results, session expired etc )
- [How it's done in Material Design](http://marcysutton.github.io/angular-a11y/#/18)
- You can coverage your code with
  - Labels
  - ARIA Roles
  - Watched ARIA Properties
  - Interactions

Giveaway: Chrome tool to audit your page `chrome://accessibility/`

[More tools](http://marcysutton.github.io/angular-a11y/#/24)  
[More resources](http://marcysutton.github.io/angular-a11y/#/25)


## 11. Jeremy Elbourn - Software Patterns and Design with AngularJS
@jelborn
[Slides](https://docs.google.com/presentation/d/1eOL6ZaT-WqqC5q5D_uwE2EJxKmdWmfmXkkD4T47iYHk)

Regarding Angular 1.x

> Because next monday we'll have to get back at our day jobs using current versions of Angular

__Design patterns & Angular__
- __Traditional patterns && OO patterns__
  - Services = Injected Singletons
  - Cache for app level shared data
  - Facade for browser and 3rd party apps
  - Factory for instantiating other objects (based on shared init config)
- __Data binding, is basically an implementation of the traditional observer pattern__
  - Inheritance for services & controllers
  - Patterns for creating clean maintainable applications
  - Polymorhpism and Directives
- __Anti-patterns__
  - War and peace controllers. They're too long. Keep only the business logic in, and move the rest into services for example.
  - Too long/complicated link function
  - Using services to store "per page" state and clearing upon route change
  - Magical Prototype Chain Dependency


Focus less on __"is this this the angular way?"__  
Focus more on __"is this good software?"__


## 12. Dave Smith - The Power of $q
@djsmith42 [slides](http://slides.com/djsmith/the-power-of-angular-q/#/)

> Prevent Problems and upscale your apps with $q

__Advantages__
- Parallelizable `$q.all( callArray ).then();`
- Composable (easy chain promise)
- Dynamic
- Great for handling errors and corner cases
`promise.then( function happyPath() {...}, function handleError(){ ... });`
- $q is aware of the digest loop of Angular  
if you resolve a promise the callback is called only after the digest loop is finished)

__Promises are Everywhere__
- Even jQuery has them ;-)
- Q
- Bluebird
- Native promises coming soon

## 13. Matias Woloski & Martin Gontovnikas - Making your Angular app a maximum security prison
@woloski @mgonto @auth0

[Auth0](https://auth0.com/)
> Out of the box security in Angular

__Handle identity management__  
- on almost all possible [development platforms](https://docs.auth0.com/quickstart/) (choose your app type)
- together with many [identity providers](https://docs.auth0.com/identityproviders) (socialmedia or generic backend services)

__Demo time__  
The [code](https://github.com/auth0/angularjs-jwt-authentication-tutorial) is a step-by-step tutorial seperated by branch

## 14. Ari Lerner - Building games with AngularJS
@auser [slides](http://ari.ngrok.com)  
Code at https://github.com/fullstackio/ng-game

Why build a game with Angular ?
- Games are often more than a canvas
- Webapps are great at powering these

Showing interesting use of:
- [Browserify](http://browserify.org/) to package and load module with CommonJS syntax (like nodejs require ...)
- $injector to dynamically / imperative load services without declaring explicit dependency
- hook of $destroy event to correctly free object (cleanup game manager)
- ioLoader module to wrap and handle socket.io for runtime comunication with backend (keep gamers in sync)

## 15. Brian Ford - Tooling
@briantford [slides](https://docs.google.com/presentation/d/16RJPOvWMePMTkvDrugOakV9uyGFRMd3PZ3g5UofhfIY/edit#slide=id.p)

> Sometimes you have no clue as a developer why nothing or a certain thing happened

Try picking out a typo `ng-clock` in several lines of code!

>Can we do better ? Should we do more static validation or even runtime validation ?

> Yes we should.

__Solution: [ngHint](https://github.com/angular/angular-hint)__  
Runtime hinting for Angular. Suggests and hints on improvements in your code.
- typo’s `Found ng-clock. did you mean ng-click?`
- unused modules
- deprecated API’s
- naming conventions
- great improvement for CI

### Further news

__New Batarang__
- More simplified
- ngHint integration

__Roadmap, personal wishes__
- Performance hints
- Hints for when upgrading for example from 1.2 to 1.3
