# Smooth Scroll
A lightweight script to animate scrolling to anchor links. [View the demo](http://cferdinandi.github.io/smooth-scroll/).

**In This Documentation**

1. [Getting Started](#getting-started)
2. [Options & Settings](#options-and-settings)
3. [Browser Compatibility](#browser-compatibility)
4. [Contributors](#contributors)
5. [License](#license)
6. [Changelog](#changelog)
7. [Older Docs](#older-docs)



## Getting Started

### 1. Include Smooth Scroll on your site.

```html
<script src="js/smooth-scroll.js"></script>
```

### 2. Add the markup to your HTML.

```html
<a data-scroll href="#bazinga">Anchor Link</a>
...
<span id="bazinga">Bazinga!</span>
```

Turn anchor links into Smooth Scroll links by adding the `[data-scroll]` data attribute. Give the anchor location an ID just like you normally would.

### 3. Initialize Smooth Scroll.

```html
<script>
	smoothScroll.init();
</script>
```

In the footer of your page, after the content, initialize Smooth Scroll. And that's it, you're done. Nice work!



## Options and Settings

Smooth Scroll includes smart defaults and works right out of the box. But if you want to customize things, it also has a robust API that provides multiple ways for you to adjust the default options and settings.

### Global Settings

You can pass options and callbacks into Smooth Scroll through the `init()` function:

```javascript
smoothScroll.init({
	speed: 500, // How fast to complete the scroll in milliseconds
	easing: 'easeInOutCubic', // Easing pattern to use
	updateURL: false, // Boolean. Whether or not to update the URL with the anchor hash on scroll
	callbackBefore: function () {}, // Function to run before scrolling
	callbackAfter: function () {} // Function to run after scrolling
});
```

#### Easing Options

**Linear**
*Moves at the same speed from start to finish.*

* `Linear`


**Ease-In**
*Gradually increases in speed.*

* `easeInQuad`
* `easeInCubic`
* `easeInQuart`
* `easeInQuint`


**Ease-In-Out**
*Gradually increases in speed, peaks, and then gradually slows down.*

* `easeInOutQuad`
* `easeInOutCubic`
* `easeInOutQuart`
* `easeInOutQuint`


**Ease-Out**
*Gradually decreases in speed.*

* `easeOutQuad`
* `easeOutCubic`
* `easeOutQuart`
* `easeOutQuint`


Learn more about the different easing patterns and what they do at [easings.net](http://easings.net/).

### Override settings with data attributes

Smooth Scroll also lets you override global settings on a link-by-link basis using the `[data-options]` data attribute:

```html
<a data-scroll
   data-options="speed: 500;
                 easing: easeInOutCubic;
                 updateURL: false"
>
	Anchor Link
</a>
```

### Use Smooth Scroll events in your own scripts

You can also call Smooth Scroll's scroll animation events in your own scripts:

```javascript
smoothScroll.animateScroll(
	toggle, // Node that toggles the animation. ex. document.querySelector('#toggle')
	anchor, // ID of the anchor to scroll to. ex. '#bazinga'
	options, // Classes and callbacks. Same options as those passed into the init() function.
	event // Optional, if a DOM event was triggered.
);
```

### Fixed Headers

Add a `[data-scroll-header]` data attribute to fixed headers. Smooth Scroll will automatically offset scroll distances by the header height. If you have multiple fixed headers, add `[data-scroll-header]` to the last one in the markup.

```html
<nav data-scroll-header>
	...
</nav>
```


## Browser Compatibility

Smooth Scroll works in all modern browsers, and IE 9 and above.

Smooth Scroll is built with modern JavaScript APIs, and uses progressive enhancement. If the JavaScript file fails to load, or if your site is viewed on older and less capable browsers, anchor links will jump the way they normally would. If you need to smooth scrolling for older browsers, [download the jQuery version of Smooth Scroll on GitHub](https://github.com/cferdinandi/smooth-scroll/tree/archive-v1).



## Contributors

* [Willem Liu](https://github.com/willemliu)
* [Gaëtan Renaudeau](https://gist.github.com/gre/1650294)
* [Robert Pate](https://github.com/robertpateii)
* [Arndt von Lucadou](https://github.com/a-v-l)
* [Alex Guzman](https://github.com/alexguzman)
* [Luke Siedle](https://github.com/luke-siedle)



## License
Smooth Scroll is licensed under the [MIT License](http://gomakethings.com/mit/).



## Changelog
* v4.0 - February 21, 2014
	* Better public/private method namespacing.
	* Require `init()` call to run.
	* New API exposes additional methods for use in your own scripts.
	* Better documentation.
* v3.3 - February 19, 2014
	* [Add `offsettTop` to `offsetHeigh`t for `scrollHeader`. Allows for multiple fixed headers, or a fixed header that sits slightly below the top of the page.](https://github.com/cferdinandi/smooth-scroll/pull/36)
* v3.2 - February 10, 2014
	* [Fixes iOS infinite loop](https://github.com/cferdinandi/smooth-scroll/pull/35) and [Chrome browser zoom](https://github.com/cferdinandi/smooth-scroll/issues/31) bugs.
* v3.1 - February 4, 2014
	* Reverted to `Array.protype.foreach` loops.
* v3.0 - January 28, 2014
	* Switched to a data attribute for the toggle selector.
	* Added namespacing to IIFE.
	* Updated looping method and event listener.
* v2.19 - January 23, 2014
	* [Fix back button behavior in Chrome.](https://github.com/cferdinandi/smooth-scroll/issues/26#issuecomment-33172325)
* v2.18 - January 23, 2014
	* [Update URL before animation.](https://github.com/cferdinandi/smooth-scroll/pull/27)
	* [Fix back button behavior in Firefox.](https://github.com/cferdinandi/smooth-scroll/issues/26)
* v2.17 - January 17, 2014
	* [Fixed back button behavior when using `data-url` feature.](https://github.com/cferdinandi/smooth-scroll/pull/18)
* v2.16 - January 16, 2014
	* [Updated variables for more accurate easing math when scrolling to top of page.](https://github.com/cferdinandi/smooth-scroll/pull/25#issuecomment-32566729)
* v2.15 - January 16, 2014
	* [Fixed bug that caused "scroll-to-top" animation to create endless loop.](https://github.com/cferdinandi/smooth-scroll/issues/24)
* v2.14 - January 15, 2014
	* [Fixed bug that caused animation to stop several pixels short.](https://github.com/cferdinandi/smooth-scroll/pull/15#issuecomment-32380770)
* v2.12 - January 7, 2014
	* [Added fixed header support.](https://github.com/cferdinandi/smooth-scroll/pull/20#issuecomment-31773547)
* v2.11 - January 4, 2014
	* [Change `offsetHeight` to `scrollHeight` to fix fixed/absolute positioning issues.](https://github.com/cferdinandi/smooth-scroll/pull/14)
* v2.10 - December 31, 2013
	* [Added URL history support.](https://github.com/cferdinandi/smooth-scroll/pull/17)
* v2.9 - December 9, 2013
	* [Added fixed for infinite loop when scrolling up.](https://github.com/cferdinandi/smooth-scroll/issues/13)
* v2.8 - December 3, 2013
	* [Fixed false distance reading.](https://github.com/cferdinandi/smooth-scroll/issues/11)
	* Added linear easing as fallback when easing pattern not recognized to prevent script from failing.
* v2.7 - November 25, 2013
	* Converted naming conventions back to mathmatical roots (ex. `easeInCubic`) to remain consistent with development community language.
* v2.6 - November 26, 2013
	* Missing character was causing certain easing functions to break.
* v2.5 - November 22, 2013
	* Changed the default easing to `easeInOutNormal`.
* v2.4 - November 21, 2013
	* Added easing support with contributions from [Willem Liu](https://github.com/willemliu) and code from [Gaëtan Renaudeau](https://gist.github.com/gre/1650294).
* v2.3 - August 27, 2013
	* Added missing semicolons.
	* Defined `animationStop` variable once, add values later.
	* Activated strict mode.
	* Wrapped in IIFE.
* v2.2 - August 17, 2013
	* Now you can set the animation speed with the `data-speed` attribute. (ex. `data-speed="400"`)
* v2.1 - August 17, 2013
	* Improvement animation function interval for smoother animation.
	* Updated to allow for scrolling up the page.
* v2.0 - August 14, 2013
	* Converted to vanilla JavaScript.
	* Removed dependency on jQuery.
* v1.1 - June 7, 2013
	* Switched to MIT license.
* v1.1 - May 18, 2013
	* Added jQuery noConflict mode.
	* Updated tutorial.
* v1.0 - January 24, 2013
	* Initial release.



## Older Docs

* [Version 3](http://cferdinandi.github.io/smooth-scroll/archive/v3/)
* [Version 1](https://github.com/cferdinandi/smooth-scroll/tree/archive-v1)