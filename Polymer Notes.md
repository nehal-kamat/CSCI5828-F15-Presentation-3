> http://www.2ality.com/2013/05/google-polymer.html

At Google I/O 2013, Google presented a new web user interface (UI) framework called Polymer.

The way it works is indicative of the future of all web UI frameworks.

Polymer
--------
Polymer is composed of the following layers:  

**Foundation (platform.js):** Foundational building blocks. Most, if not all, of these APIs will eventually become native browser APIs.  

**Core (polymer.js):** Helpers complementing Foundation.
Elements: UI and non-UI components built on Core.  

---

1. **The Foundation layer (platform.js)**  

  The Foundation layer comprises the following technologies:

    - DOM Mutation Observers and Object.observe() (probably ECMAScript 7): for observing changes to DOM elements and plain JavaScript objects.
    - Pointer Events: handle mouse and touch in the same manner, on all platforms.
    - Shadow DOM: encapsulate structure and style inside elements (e.g. custom ones).
    - Custom Elements: define your own HTML5 elements. The names of custom elements must contain a dash, which is a simple way of namespacing them and distinguishes them from standard elements.
    - HTML Imports: package custom elements. Such packages include HTML, CSS and JavaScript.
    - Model-Driven Views (MDV): Does data-binding directly in HTML. Not yet in the process of being standardized.
    - Web Animations: API unifying several of the web’s animation approaches.

  APIs 3–5 are part of Web Components, a component model for the web. Web components are the most important foundation of Polymer.

  *platform.js* shims these APIs on browsers where they are not (yet) available. It is only 31KB (if minified and gzipped). One of the declared goals of Polymer is to field-test HTML5 UI APIs before standardizing them.

2. **Layers: Core and Elements**  

  Polymer itself is almost like native HTML5: “attributes in, events out”. One example of using the UI widget polymer-panels:
```
      <polymer-panels
          on-select="panelSelectHandler"
          selected="{{selectedPanelIndex}}">
      </polymer-panels>
```

    Its architecture is very component-oriented, its components being HTML elements. Some of the elements don’t even have a user interfaces themselves.

    For example, animations are elements (you can nest them etc.), they have no user interface, but instead point to UI elements that they animate. Responsive design is built into many widgets, which means that they will transform so that they work best on a given platform (cell phone, tablet, desktop, etc.).

3. **Interoperability**

  Polymer is designed to be à la carte: you pick and choose what you need. Thanks to Web Components, its elements are also highly interoperable.

  In one demo given at I/O, an element coming from the Mozilla project X-Tag (that is similarly based on Web Components) was shown as working inside Polymer.

4. **When can I use it?**

  Polymer is still pre-alpha and thus not yet really ready for public consumption. It is, however, developed in the open and you can already play with its code.

5. **Polymer versus other frameworks**

  Polymer is not the framework to end all other frameworks. Instead, existing frameworks can be based on the same foundations.

  In fact, the functionality of most of the APIs that were mentioned above should look familiar to you if you have already used a UI framework such as Ember.js or AngularJS. As for AngularJS, a recent tweet explains how it will evolve:

  > AngularJS will use Polymer for its widgets. It's win-win.

6. **What does it all mean?**

  Nobody actually wants to use frameworks. We only want to build web user interfaces efficiently and frameworks help. The most important pieces missing from native HTML are:

  - A rich set of widgets. In my opinion, this is the biggest deal about Web Components (and, to a lesser degree, about Polymer). We finally get a large set of widgets that we can use anywhere.
  - User interface layout. I have high hopes for CSS Grid Layout here. Grid Layout is native HTML, so it complements Web Components quite naturally.
  - “Glue” to combine widgets (e.g. data binding).

  Currently, frameworks are largely incompatible: they usually come with their own tool chain, inheritance API, widget infrastructure, etc.

  The developments described in this post, along with ECMAScript 6’s classes and modules, point to a future where everything will be much more interoperable. The benefits for the web development ecosystem are obvious.  

7. **Resources**

  If you want to know more about Web Components and Polymer, you have the following resources at your disposal:

  - Talks at Google I/O 2013:
    - [“Web Components: A Tectonic Shift for Web Development”](https://developers.google.com/events/io/sessions/318907648) by Eric Bidelman
    - [“Web Components in Action”](https://developers.google.com/events/io/sessions/324149970) by Matthew McNulty, Alex Komoroske [builds on the previous talk, covers Polymer  
  - [HTML5 Rocks](http://www.html5rocks.com/en/tutorials/#webcomponents): articles on Web Components.
  - Polymer homepage: [polymer-project.org](polymer-project.org)
