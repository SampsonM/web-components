# Templates

## Current approaches
HTML in script tags
- \+ Nothing is run or rendered
- \- Not DOM elements, risks XSS from using innerHTML

Hidden DOM Elements
- \+ Easy to clone
- \- Everything still runs, may throw 404

We need the positives of both, we need to be allowed to define template, html, css that is inert until to cloned, but something easy to travers and clone.

#
## **Template tags!**

- Inert - Does nothing until cloned, does not render or run, script tags etc inside aren't run until its cloned for use
- Hidden from selectors - Content is unselectable by getElementBy.. etc, child nodes accessible but hidden from traditional techniques
- Flexible placement - Can be plaecd anywhere head, body, frameset etc

#
## Template Activation

```javascript
const template = document.querySelector('#mytemplate')
// any traditional metod works here

const clone = document.importNode(template.content, true)
// true determines whether it should be deep copy or not, normally true

document.body.appendChild(clone)
// append clone where ever you need!
```

#
## Inject data into template

```javascript
const template = document.querySelector('#mytemplate')
const clone = document.importNode(template.content, true)

clone.querySelector('.verb').textcontent = 'shite!'
// attach your data like this or by any other standard means!

document.body.appendChild(clone)
```

#
## Nested Templates

Must manually clone both parent and child templates.
If your parent template is not yet visible the child template will not be visible to clone and append!

```html
<template>
	<div>
		Content cloned as normal
		<template>
			<p>More content that needs cloned manually</p>
		</template>
	</div>
</template>
```