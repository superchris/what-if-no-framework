### To all the Web frameworks I've loved before
* Backbone
* Angular
* React (kinda)
--
## Good ideas from web frameworks
* Reusable components
* Actions up, data down
  * AKA Dumb Components
  * AKA One way binding
  * AKA ...
--
## State of webcomponents
* Custom Elements v1
* Shadow DOM v1
* HTML templates
* Custom events
* webcomponentsj polyfill
--
## Custom elements v1
* ES6 classes that extend `HTMLElement`
* `customElements.define('my-tag', MyTagElement)`
* lifecyle methods
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
## Shadow DOM Slots
* Define placeholders in your shadow DOM
* `<slot name="foo"></slot>` with shadow DOM
* `<span slot="foo">what goes in foo slot</span` in custom element children
--
## Custom events
* Not really part of Webcomponents
* Just what the name implies
* "payload" goes in `detail`
--
## The experiment
* Build app out of webcomponents with only browser provided API
* Use "off the shelf" from other frameworks
* Figure out how to wire things together
--
### github.com/superchris/aviation-webcomponents
--
#### Current web frameworks : Web components
#### ::
#### Coffeescript : ESNext
--
## Stuff to check out
* Webcomponents.org
* Polymer
* SkateJS
