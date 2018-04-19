# Hi!
--
# Agenda
* A brief history
* A preferred future
* How we get there
--
### To all the frameworks I've loved before...
* Backbone
* Angular
* React
--
### Good ideas from web frameworks
* Reusable components
* Actions up, data down
  * AKA Dumb Components
  * AKA One way data flow
  * AKA ...
--
## But do we really need another (incompatible) one?
--
## Things that used to be good ideas
* jQuery
* Coffeescript
* Proprietary component models
--
## Web development utopia
* Cross-{browser,framework,etc} reusable components
* Truly semantic HTML
* Manageable data flow
* Testability
* Standard packaging and distribution
--
## Web Components Standards
* Custom Elements v1
* Shadow DOM v1
* HTML Templates
* Custom events
* webcomponentjs polyfill
--
## Custom elements v1
* Make your own HTML Elements
* Define their behavior and presentation
* ES6 classes that extend `HTMLElement`
* `customElements.define('my-tag', MyTagElement)`
--
### Custom element lifecycle methods
  * constructor
  * `attributeChanged`
  * `connectedCallback`
--
```
class HelloWorld extends HTMLElement {
  connectedCallback() {
    this.innerHTML = "Hello, world!";
  }
}

customElements.define('hello-world', HelloWorld);
```
```html
<html>
<head>
  <script type="module">
    import HelloWorld from './src/hello-world.js';
    customElements.define('hello-world', HelloWorld)
  </script>
</head>
<body>
  <hello-world></hello-world>
</body>
</html>
```
--
## [Hello World](http://localhost:8081/hello-world.html)
--
## Shadow DOM v1
* `element.attachShadow({mode: 'open'})`
* creates a `shadowRoot` property
* Total encapsulated DOM within a DOM
* selectors from outer page don't apply
* CSS in Shadow DOM doesn't leak out
--
```JavaScript
class HelloShadow extends HTMLElement {
  connectedCallback() {
    this.attachShadow({mode: 'open'});
    this.shadowRoot.innerHTML = `
<style>
  .shadow {
    text-shadow: 5px 5px gray;
  }
</style>
<h1 class="shadow">This has a shadow but ain't red</h1>
    `;
  }
}

export default HelloShadow;
```
--
```html
<html>
<head>
  <style>
    h1 {
      color: red;
    }
  </style>
  <script type="module">
    import HelloShadow from './src/hello-shadow.js';
    customElements.define('hello-shadow', HelloShadow)
  </script>
</head>
<body>
  <h1 class="shadow">Got no shadow but red</h1>
  <hello-shadow></hello-shadow>
</body>
</html>
```
--
## [Hello shadow](http://localhost:8081/hello-shadow.html)
--
## Composition and slots
* Uses a shadow DOM as a template
* Smerges Light DOM and Shadow DOM
* shadow DOMs use a `<slot></slot>`
* light DOM is rendered into the slot
--
```JavaScript
class HelloSlots extends HTMLElement {
  connectedCallback() {
    this.attachShadow({mode: 'open'});
    this.shadowRoot.innerHTML = `
      Hi there, <slot></slot>!
    `;
  }
}

export default HelloSlots;
```
```html
<html>
<head>
  <script type="module">
    import HelloSlots from './src/hello-slots.js';
    customElements.define('hello-slots', HelloSlots)
  </script>
</head>
<body>
  <hello-slots>Momentum peeps</hello-slots>
</body>
</html>
```
--
## [Hello slots](http://localhost:8081/hello-slots.html)
--
## Semanticker markup
### e. g., from this..
```html
<ul class="list-group">
  <li class="list-group-item">
    <div class="form-check">
      <input type="checkbox" class="form-check-input" id="exampleCheck1">
      <label class="form-check-label" for="exampleCheck1">Left wheel</label>
    </div>
  </li>
</ul>
```
--
### To this...
```html
<flight-checklist>
  <checklist-item>Left wheel</checklist-item>
</flight-checklist>
```
--
## [Checklist example](http://localhost:8083)
--
## Data flow
![flux](flux.png)
--
## Could we do this without a framework?
--
## Custom events
* Not really part of Webcomponents
* Just what the name implies
* "payload" goes in `detail`
--
## My data flow experiment
* Build app using only browser provided API
  * Bonus points for no build tool
* Use "off the shelf" web components
* Figure out how to wire things together in a sensible way
--
## [FlightPlanner](http://localhost:8082)
--
## Testing web components
* Test frameworks often coupled to web frameworks
* Fake DOMs are fake
* Puppeteer isn't :)
--
## Test example
--
## Things worth checking out
* [Webcomponents.org](http://webcomponents.org)
* [Polymer](https://www.polymer-project.org/)
  * [lit-html](https://github.com/Polymer/lit-html)
* [SkateJS](http://skatejs.netlify.com/)
* [Others](https://www.webcomponents.org/introduction#libraries-for-building-web-components)
--
## Thanks!
#### @superchris
#### github.com/superchris
--
