# sticky.ts
A library for sticky elements written in TypeScript and compiled to vanilla JavaScript.

> sticky-ts is a library for creating sticky elements for your website. It is originally inspired by [sticky-js](https://github.com/rgalus/sticky-js) and its many forks.

[DEMO](https://jziggas.github.io/sticky-ts/)

## Features

- No dependencies
- The safety of TypeScript and the minimalism of vanilla JavaScript
- Lightweight
- You may sticky an element the entire page or a specific container
- No additional CSS needed

## Install

````
npm install sticky-ts
````

## Usage

Include the module in your bundle or the dist build into your HTML.

```html
<script src="sticky.min.js"></script>
```

```js
import {Sticky} from 'sticky-ts'
```

And given an element

```html
<div class="selector">Sticky element</div>
```

Initialize in your code

```js
let sticky = new Sticky('.selector');
```

Syntax

```js
new Sticky([selector:string], [global options:object])
```

## Examples

Multiple sticky elements with data-sticky-container and [options](https://github.com/jziggas/sticky-ts#available-options)

```html
<div class="row" data-sticky-container>
  <div class="medium-2 columns">
    <img src="http://placehold.it/250x250" class="sticky" data-margin-top="20" data-sticky-for="1023" data-sticky-class="is-sticky">
  </div>
  <div class="medium-8 columns">
    <h1>Sticky-js</h1>
    <p>Lorem ipsum.....</p>
  </div>
  <div class="medium-2 columns">
    <img src="http://placehold.it/250x250" class="sticky" data-margin-top="20" data-sticky-for="1023" data-sticky-class="is-sticky">
  </div>
</div>

<script src="sticky.min.js"></script>
<script>
  var sticky = new Sticky('.sticky');
</script>
```

## Methods

Update sticky, e.g. when parent container (data-sticky-container) change height

```js
var sticky = new Sticky('.sticky');

// and when parent change height..
sticky.update();
```

Destroy sticky element

```js
var sticky = new Sticky('.sticky');

sticky.destroy();
```

## Available options

Option | Type | Default | Description
------ | ---- | ------- | ----
data-sticky-wrap | boolean | false | When it's `true` sticky element is wrapped in `<span></span>` which has sticky element dimensions. Prevents content from "jumping".
data-margin-top | number | 0 | Margin between page and sticky element when scrolled
data-sticky-for | number | 0 | Breakpoint which when is bigger than viewport width, sticky is activated and when is smaller, then sticky is destroyed
data-sticky-class | string | null | Class added to sticky element when it is stuck

## Browser Compatibility

Library is using ECMAScript 5 features.

* IE 9+
* Chrome 23+
* Firefox 21+
* Safari 6+
* Opera 15+

If you need this library working with older browsers you should use ECMAScript 5 polyfill.

[Full support](http://caniuse.com/#search=ECMAScript%205)

* * *

### Website

https://jziggas.github.io/sticky-ts/

### License

[MIT License](https://github.com/jziggas/sticky-ts/blob/master/LICENSE)