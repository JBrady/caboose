Caboose
=========

RED Interactive's SCSS + Compass framework

## Includes

* Standardizes defaults across projects
* Robert Penner's easings ported to SASS
* Several helper mixins and placeholders to get you started

## Mixins
Mixins can be found in the scss/modules/mixins directory

### `_animation.scss`
A "polyfill" while Compass 0.13 is still in alpha/beta. The mixin [will be standard](https://github.com/chriseppstein/compass/blob/master/frameworks/compass/stylesheets/compass/css3/_animation.scss) once 0.13 is stable, and supports everything the upcoming build will.

[Compass Animation](http://beta.compass-style.org/reference/compass/css3/animation/)

### `_experimental-both.scss`
This mixin functions like Compass' [@experimental](http://compass-style.org/reference/compass/css3/shared/#mixin-experimental), except it will prefix the property and the value. Useful for mask-image: gradient(); and other types of methods that require property and value prefixing.

```scss
body {
	@include experimental-both(mask-image, $gradient);
}
```

### `_grad.scss`
A fallback-friendly gradient mixin. Takes two values and mixes them into one solid color for non-grad-supporting browsers, and generates a gradient for those that support CSS3 gradients.

```scss
body {
	@include grad(#000, #333);
}
```

### `_ie-friendly-transform.scss`
A fallback-friendly 3d-transform mixin. Outputs a 2d-fallback transform property for browsers that don't support 3d transforms, and auto-magic-bullets those that do.

```scss
body {
	@include ie-friendly-transform(translateX(100px) translateY(100px));
}
```

### `_mask-image.scss`
Mixins for CSS3 mask images.

```scss
body {
	@include mask-image(image-url("path/to/image.png"));
}
```

### `_respond-to.scss`
A mixin for media-queries. Supports a wide array of widths to respond to:

```scss
body {
	background: blue;

	@include respond-to("handheld") {
		background: red;
	}

	@include respond-to("tablet") {
		background: black
	}
}
```

## Placeholders
Placeholders can be found in the scss/modules/placeholders directory

### `_debug.scss`
Adds a debug outline to any targeted element. This extend rule is optional, make sure to flag it as such.

```scss
body {
	@extend %debug !optional;
}
```

### `_global-transition.scss`
Define a global transition and share it with multiple elements.

```scss
body {
	@extend %global-transition;
}
```

### `_magic-bullet-fix.scss`
Adds the [magic bullet fix](http://www.html5rocks.com/en/tutorials/speed/html5/#transanim) to targeted elements.

```scss
body {
	@extend %magic-bullet-fix;
}
```

### `_microfix.scss`
A better [micro clearfix](http://nicolasgallagher.com/micro-clearfix-hack/) hack.

```scss
body {
	@extend %microfix;
}
```

### `_position-zero.scss`
Position the element absolute, with top / left / bottom / right set to zero.

```scss
body {
	@extend %position-zero;
}
```

### `_scrollable.scss`
Sets overflow to auto and adds `overflow-scrolling: touch` to applicable browsers.

```scss
body {
	@extend %scrollable;
}
```

### `_typeface.scss`
A [Better Helvetica Font Stack](http://j.mp/9t6O6Z).

```scss
body {
	@extend %typeface;
}
```

### License

**Released under the MIT License**

	Copyright (c) 2012 by RED Interactive Agency

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in
	all copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
	THE SOFTWARE.
