# Hi!
--
# Agenda
* A bit of background
* The experiment
* The result
* Other stuff (as time permits)
--
### To all the frameworks I've loved before...
* Backbone
* Angular
* React (kinda)
--
### Good ideas from web frameworks
* Reusable components
* Actions up, data down
  * AKA Dumb Components
  * AKA One way binding
  * AKA ...
--
## But do we really need another (incompatible) one?
--
## Things that used to be good ideas
* jQuery
* Coffeescript
* Proprietary component models
--
## State of webcomponents
* Custom Elements v1
* Shadow DOM v1
* HTML templates
* Custom events
* webcomponentjs polyfill
--
## Custom elements v1
* ES6 classes that extend `HTMLElement`
* `customElements.define('my-tag', MyTagElement)`
--
### Custom element lifecyle methods
  * constructor
  * `attributeChanged`
  * `connectedCallback`
--
## Shadow DOM v1
* `element.attachShadow({mode: 'open'})`
* Total encapsulated DOM within a DOM
* CSS from outer page doesn't apply
* CSS in Shadow DOM doesn't bleed out
--
## Custom events
* Not really part of Webcomponents
* Just what the name implies
* "payload" goes in `detail`
--
## The experiment
* Build app using only browser provided API
  * Bonus points for no build tool
* Use "off the shelf" web components
* Figure out how to wire things together in a sensible way
--
### github.com/superchris/aviation-webcomponents
--
## Testing with [mocha-puppeteer](https://github.com/charlieduong94/mocha-puppeteer)
--
## Other stuff
* [Webcomponents.org](http://webcomponents.org)
* [Polymer](https://www.polymer-project.org/)
  * [lit-html](https://github.com/Polymer/lit-html)
* [SkateJS](http://skatejs.netlify.com/)
* [Others](https://www.webcomponents.org/introduction#libraries-for-building-web-components)
--
## But FooJS has a library that can convert its components to web components kinda sorta!
--
