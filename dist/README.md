# Polymer Snippets for Sublime

## Install

To install through [Package Control](http://wbond.net/sublime_packages/package_control),
search for **Polymer & Web Component Snippets**. If you still don't have Package Control in Sublime Text, [go get it](http://wbond.net/sublime_packages/package_control/installation).
It's pure awesomeness.

If you don't use Package Control, you can download the package and put it manually inside your `Packages` directory. It should work but will not update automatically.

## Elements

Type the name of [any `iron-*` or `paper-*` element](https://elements.polymer-project.org), then hit `tab` to auto complete. Ex:

![Using snippets](https://cloud.githubusercontent.com/assets/1066253/8323071/77f4173c-19f4-11e5-94d2-a22e3b3e526e.gif)

OR, start typing the prefix for an element and hit `ctrl+space` to fuzzy search for a completion. Ex:

![Fuzz auto complete](https://cloud.githubusercontent.com/assets/1066253/8323081/87cd9890-19f4-11e5-9005-bf627ab30ea5.gif)

## Polymer

### [pe] polymer element

```html
<dom-module id="$1">
	<template>
		<style>
			:host {
				display: block;
			}
		</style>
		$2
	</template>
	<script>
		Polymer({
			is: '$1'
		});
	</script>
</dom-module>
```

### [pes] polymer element with external stylesheet

```html
<dom-module id="$1">
	<link rel="import" type="css" href="$1.css">
	<template>
		$2
	</template>
	<script>
		Polymer({
			is: '$1'
		});
	</script>
</dom-module>
```

### [hi] html import *(I use this one a lot)*

```html
<link rel="import" href="${1:bower_components}/${0}/${0}.html">
```

### [hii] html import iron-* element

```html
<link rel="import" href="${1:bower_components}/iron-${2}/iron-${2}.html">
```

### [hip] html import paper-* element

```html
<link rel="import" href="${1:bower_components}/paper-${2}/paper-${2}.html">
```

## Web Components

### [template] template
```html
<template$1>$0</template>
```

### [ce] custom element

```javascript
var ${4:tmpl} = document.querySelector('${5:template}');

var ${1:WidgetProto} = Object.create(HTMLElement.prototype);

${1:WidgetProto}.createdCallback = function() {
	var root = this.createShadowRoot();
	root.appendChild(document.importNode(${4:tmpl}.content, true));
};

var ${2:Widget} = document.registerElement('${3:my-widget}', {
	prototype: ${1:WidgetProto}
});
```

## HTML

### [ph] HTML template with Web Components polyfill

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">

	<title>${1}</title>
	<meta name="description" content="${2}">

	<!-- Mobile -->
	<meta name="viewport" content="width=device-width, minimum-scale=1.0, initial-scale=1.0, user-scalable=yes">

	<!-- Chrome / Android -->
	<meta name="mobile-web-app-capable" content="yes">
	<meta name="theme-color" content="black">
	<link rel="icon" href="icon.png">

	<!-- Safari / iOS -->
	<meta name="apple-mobile-web-app-capable" content="yes">
	<meta name="apple-mobile-web-app-status-bar-style" content="black">
	<link rel="apple-touch-icon-precomposed" href="apple-touch-icon.png">

	<!-- Web Components -->
	<script src="bower_components/webcomponentsjs/webcomponents-lite.js"></script>
</head>
<body unresolved>
	$0
</body>
</html>
```

## Thanks 

Thanks to [Rob Dodson](https://github.com/robdodson) for all of his hard work on [snippets](https://github.com/robdodson/PolymerSnippets) for Sublime!

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License

Copyright (c) 2015 Ryan Edge


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
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
