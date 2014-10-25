![ngeurope](https://www.dropbox.com/s/do6pb6bw7zp66mk/ng-europe-horizontal-on-black.png?dl=1)
#Day 1


## 1. Brad Green & Igor Minar

- 1600+ angular apps internally at Google and growing
- Google Fiber https://fiber.google.com
- Google Trends https://trends.google.com
- 234+ meetups worldwide

### Angular 1.3

- A lot of [speed improvements](https://github.com/angular/angular.js/blob/v1.3.0/CHANGELOG.md)
- You can now use ngAria

### Angular 2.0
*What's going to be in 2.0 ?*

__Mobile__
- Will be shipped with Material Design
- Improved router
- Animation + touch
- Close to native quality

__Performance__
- GC pressure
- Optimized DOM
- Analysis tools

__Scale__
- Improvements to scale your apps and allow you to scale development teams. Focus on 'enterprisey' collaboration features.
- IDE support
- ES6 + types + meta ( optional types system )
- Documentation tools. Demo will follow.

Final note: Brad and Igor encourage the community to reach out to other community members, contribute and keep the party going.

## 2. Jeff Cross & Brian Ford
Angular 1.3 in depth [release notes](https://github.com/angular/angular.js/blob/v1.3.0/CHANGELOG.md )

__1.3.0 release__
- 400+ contributors.
- 1600+ commits

###What's in it ?###
A lot of runtime speed improvements. In total it took 8 months to release.

__Performance__
- Mentioning ng-benchpress. For performing repetitive benchmarks on Angular, also available for your apps.
- Digest cycle is 44% faster than 1.2.x by average
- DOM manipulation is up by 44%
- 73% less garbage (kb)
- Production mode performance monitoring can be turned on and off. Default was on in previous versions, increases speed even more.
- $httpProvider.useApplySync(true) - Allows http provider to group async responses that come in shortly after each other and trigger just 1 digest cycle
- One time binding - use :: in your templates to bind once for static values (reduces size of the watchlist by excluding items which only 'change' at app-startup)

__Forms__
- ngModel.$validators is a seperate step after $formatters.
- ngModel.$asyncValidators. (allows you to check for things that need something like a database/http call)

__Forms: ng-model-options__
- debounce like in underscore.js  (gives an input a time to settle after user input before triggering binding updates)
- blur ( update model onblur )
- getter / setter ( instead of watching you can now bind directly to a getter/setter function in your Ctrl, similar til jQuery)
- ngMessages provides directive to integrate validation messages into a smaller structure. Replaces endless ng-show="..." on many many divs with different messages. Will only show one message at a time in the order they are written.

__Developer ergonomics. To help developers develop faster__

- Composable SVG - was hard to before to do.
- allOrNothing - doesn't evaluate bindings on ng-src or other http URL template when a variable in the template has no value (prevents ng-src"images/{{user.id}}/avatar.png" to evaluate to images//avatar.png
- $watchGroup - to group a group of watches together and bind to 1 function
- strictDI - like ng-annotate but more powerful
- ngAria for easier implementation of accessibility

more info : http://goo.gl/AOfdPB


## 3. Andrew Joslin - Ionic Framework

Ionic in 100 words or less:
>A container that displays a website and fools the user in thinking it's a native app. And it supports/hangs on Angular.

__Demo__

(Freaking fast live coding)
See live stream https://www.youtube.com/watch?v=QEs91Yh-cao

- Showing the ionic cli tool.
- Creating an app and downloading dependencies and setting up livereload with iOS emulator.
- Live reloading makes for an instant development experience on an actual device emulator. It actually launches a server you can also access with your browser for debugging.
- Provides directives for 'native' components like loading icons which actually feel native, but also a few 'ionic' custom ones which are <quote>always the best</quote>

## 4. Victor Berchet & Rado Kirov - AngularDart under the hood
https://angulardart.org/

> Angular.dart is a remake of Angular in Dart and is used as a proving ground for new features in Angular2.0

Things making it into Angular 2.0
- @-annotations
- Views and ViewPorts
- Zones (in callback handling) (main functionality is that there is no need to call apply() to get inside the Angular scope)
aha


Showing a demo Todo app built with Dart


## 5. Vojta Jína - Can We Learn from Architects?

Vojta:
> Sometimes when I enter the office in the morning, I will find the Angular dashboard all red, things broken and stuff.

Usually we don’t know why it’s broken. What if we could improve the predictability ?
Shows a couple of landmarks around the world and states

> Designing buildings and software do have a lot in common.

Designing buildings involves a lot of math to ensure the quality and durability. So does software need more math to ensure those things?

*( Shows generic object orientated code to demonstrate the order of javascript lines are essential for it work properly. )*

When you have several apps which depend on each other, sometimes we tend to communicate too explicitly between those apps. That poses a lot of problems regarding maintainability for example.

*Basic message: use more functional/formal approach to programming. Pure functions (without side-effects) and immutable objects allow for easier reasoning about them and optimizing calls etc)*


## 6. Julien Bouquillon - Using AngularJS and Phonegap to build hybrid mobile applications

- Dicusses [Cordova](http://cordova.apache.org/) architecture, the OpenSource part of Phonegap.
- The web platform is the only one that can adress the multiples devices/OS with a single codebase
- Mentions http://ngcordova.com/, will demonstrate that using the [Contacts API](http://ngcordova.com/docs/#Contacts).
- Showing how to load certain angular modules only when on Desktop or Mobile for example using a simple condition (!window.cordova)
- Example code of mocking cordova calls for desktop browsers or unit test

Slides : http://revolunet.github.io/ngeurope-angular-cordova

Demo : http://revolunet.github.io/angular-ngcordova-demo

[Demo time]

LUNCH ^_^

## 7. Thomas Burleson & Max Lynch - Material Design

- Discussing the people and the philosophies behind Angular, Material Design and Polymer.

> The Angular Material library's goal is to free us developers from the complexity of things like touch events, ink, aria etc
> Simply include the directive and use them, don't worry about the underlying code

Walking through the documentation and sources at https://material.angularjs.org/

A lot of emphasis on invested time from Google to assure the components perform well on mobile

- The Grid in Angular Material
  - takes care of the challenges you encounter with flexbox
  - allows for changes based on Device capabilities (screen size, rotations, etc)
- Theming is almost released, theming allows you to change all the colors in a very simple manner (change single property)
- Beta 1 will include all missing components and is targeted for release before end of Q4

## 8. Pete Bacon Darwin - Dgeni - Documentation generation on steroids


This is why we think Pete is a cool guy ^_^
![Bacon](http://assets.amuniversal.com/b44e2a60d2d60131678b005056a9545d)

> We developers love docs, but hate stale, not regulary updated, docs

Mentions ngdoc, but finds it got too complicated and too large
Thus came Dgeni ( Jenny ), with good design principles like seperation of concerns, dependency injection, tested codebase.

Projects using Dgeni:
- Angular
- Protractor
- Ionic
- Angular Material

Dgeni understands the Angular concepts. If you construct a factory, it knows the name of the factory is the name used.

Pete talks about a dgeni package called [angularjs](https://github.com/petebacondarwin/dgeni-angular) he has been working the last few months, which processes your code and finds and categorizes your controllers, services, etc without defining @module: name, @directive: unicorn.

##### Request
It would be great if you could join and create styling/templates for Dgjeni.
Go to https://github.com/angular/dgeni, clone it, make it beautiful and create a pull request. He might just add your theme/styling to the project.


## 9. Julie Ralph & Chirayu Krishnappa - Protractor and the Testability API

> Protractor is the End-To-End testing tool from the Angular team. It's built as a nodeJS package.

1.0 version of Protractor released in July. API is now stable and ready for use.
https://github.com/angular/protractor
http://angular.github.io/protractor/#/
Examples can be found in Protractor's own test suite (see github)

__Main concepts of Protractor__
- Basically a layer on top of WebDriver API.
- Jasmine syntax is primary syntax for writing tests. They try to stay as close to unittests as possible
- Protractor exposes several globals to drive/check/assert the resulting HTML/DOM
element(by.model('name')).clear().sendKeys('abc');
- All calls on element are async, but are executed in a Command queue or control flow
- They're all promises behind the scene

__Best practices__
- Limit logic in tests
- Re-used elements can be created as Page Objects. Defines your code for locating elements and testing them is centralized for central components.
- debug with browser.pause() - Will stop your tests at that point so you can interact with the browser and see what is happening

__Angular testability__
- App has test_e2e folder by default, containing the Protractor tests
- Angular has a testability API allowing for the inspection of bindings, or turning off animations ( which speeds up your tests! )
whenStable(callback) allows you to wait for Angular to have completely handled all async actions / digests. No need to use timeouts


__Debugging in production__

Feels bad right ?
But let's be honest.. Does it slow down your app ? Sloppiness ? Insecure ?

Julie states:
> "the impact is minimal". Workload gets deferred and in terms of security: your frontend code is there anyway.

__Coming up next in Protractor__
- Debugging improvements
- Latency profiling
- Webdriver Proxy - SyncDriver
- More advanced tutorials and best practices


## 10. Rob Eisenberg - The new Router for AngularJS

Got to work on the new router of Angular after talking to Brad Green.
The new router was initially built for Angular 2.0, but is going to be ported to Angular 1.3 as well.
Agenda for today: Features & Design.

__New features__
- Conventions
- Navigation Model
- Document Title updates
- Dynamic Loading
- Allows for controllers to be loaded as soon as the route is accessed (lazy loading of controllers)
- Child Apps ( great for large, feature rich applications and particulary large organizations )
- Splits all routing into a single App Router and sub routers, called Child Routers.
- State management & component reuse
- Parellel Controllers (map a single route to multiple controllers)
- Screen Activation
- Lifecycle provides hooks for controllers to receive an event when navigating to & from a router state (usefull for displaying messages if you have unsaved data)
- Everything is promises based
- Navigation Commands. write your own custom logic on top of angular-router.

__Design__
- Navigation pipeline. Can be customized to your likings. Add or remove the processing steps.
- Customization. Plug into the history, viewport, configs, etc.


## 11. Pawel Kozlowski - ui-bootstrap

Talking about the philosophy behind ui-bootstrap.
> Mainly: Lightweigt directives, flexible, customizable & tested.

Demonstrates with jquery-ui, that having parts of your template within your 1700+ lines of Javascript poses big challenges in terms of theming

__Advocates for__
- The usage of templateUrl in directives and keeping all markup and css outside of your directives
- Writing small directives
- thinking about the right abstraction level. Sometimes a directive is not the right abstraction


## 12. Matthieu Lux - Angular from scratch

> Let's build a lightweight copy of Angular during this presentation.

First line in an empty document: `'use strict';`
Code can be found here: https://github.com/Swiip/angular-from-scratch

## 13. Oliver Dore - Responsive Takes Flight: Building The First Responsive Airline Website

Oliver is a developer at [Work & Co](http://work.co/), and lead the front-end architecture of a responsive redesign for [virginamerica.com](http://www.virginamerica.com/).

---

Slideshare deck of session: [ngEurope 2014 | Responsive Takes Flight](http://www.slideshare.net/workandco/vx-ng-europe)

---

Demonstrated old site, UX issues and two codebases (for desktop and mobile). Explained that Virgin America is a unique airline that deserves a unique presence on the Web.

**Main goals of the project**

* Increase conversion
* Create a responsive, consistent experience across all devices
* Create a site that better represents Virgin's brand

> The prototype was the single source of truth, the bible - it wasn't meeting notes, sketches or PSDS. The prototype was the shared vision of what the product should be.

**Approach to Responsive Design**

Often, a discussion around "Mobile First" or "Desktop First"? Not on this project. 

> Aims of consistent UI and interaction patterns lead us to adopting an **Everything First** approach.

**UI Architecture**

* [BEM](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/) (Block, Element, Modifier) for class conventions, to promote re-usability
* [SMACSS](https://smacss.com/) (Scalable and Modular Architecture for CSS) for structuring [SASS](http://sass-lang.com/) partials

**Responsive Components**

* The ability to render different markup from a single source of data
* Other examples include main navigation, fare selector and travel summary bar
* windowService to centralize window and app global UI events
* Performance bottlenecks when firing watchers on scroll and resize events and how digest cycle was circumvented

**Forms**

* Series of directives to make building forms easier
* Aggregation of validation into formHandler
* Use of models to define schemas, mappings and (de)serialization methods to reduce coupling between API and UI

**Responsive Images**

* Grunticon for SVG icons and background images
* Responsive image directive to define breakpoint-specific sizes
* Modernizr to determine variable pixel densities and convert size attributes
* Built in conjunction with [Akamai image resize service](http://www.slideshare.net/AkamaiTechnologies/akamai-whitepaper-frontendoptimization)

**Mo $watch(), Mo Problems**

* Views with hundreds of bindings - used Pasquale Vazzana's [bindonce directive](https://github.com/Pasvaz/bindonce) to reduce number of watchers
* Memory issues, investigating with Chrome DevTools memory profiler, reducing memory usage, spikes and detached DOM nodes
* Accessibility issues - planning for improvements, including incorporating ngAria module as part of upgrade to Angular 1.3.