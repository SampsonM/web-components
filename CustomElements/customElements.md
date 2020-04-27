# Custom Elements

## Why?

Non descriptive html tags carry no meaning and don't help the maintainer developer.
Good markup: 
- describes what you are rendering and conveys additional information
- it improves SEO
- it enhances accessibility
- speeds up development by reducing styling required to create what you want
- Aids mantenance by improving description of elements

Generic divs, spans html tags are generic, they do not tell you what you are describing, what should be rendered?

Main point is simpler markup, should we make such a large change for improved markup? Yes.

#
## How?

- Custom elements must have dash, <my-component>, <a-component>
- Extend existing elements with is attribute, <input type="text" is="search-input">

#
## Registering element
Create a prototype
```javascript
const SlickTabs = Object.create(HTMLElement.prototype)
// Add functions and properties to prototype here
```

Register new element
```javascript
document.registerElement('slick-tabs')
```

Use it!
```javascript
document.body.appendChild(new SlickTabs())
// OR in HTML
<slick-tabs></slick-tabs>
```

You can even extend!
```javascript
const SlickTabsExtendedProto = Object.create(HTMLElement.prototype)

document.registerElement('slick-tabs-extended', {
	protoType: SlickTabsExtendedProto,
	extends: 'slick-tabs'
})
```


#
## Instantiate!

1. Markup
```html
<slick-tabs></slick-tabs>
```

2. New operator
```javascript
const slickTabs = new SlickTabs()
document.body.appendChild(slickTabs)
```

3. createElement
```javascript
const slickTabs = document.createElement('slick-tabs')
document.body.appendChild(slickTabs)
```

3. inner html
```javascript
document.body.innerHTML = '<slick-tabs></slick-tabs>'
```

#
## Instantiate extended components

1. Declare in markup
```html
<button is="make-shift-comment"></button>
```

2. JavaScript
```javascript
// Second param defines the component to extend
const button = document.createElement('button', 'slick-tabs')
document.body.appendChild(button)
```

3. New operator
```javascript
document.body.appendChild(new SlickTabs())
```

#
## Custom Element lifecycle hooks!

- createdCallback - instance **created**
- attachedCallback - instance **inserted** into DOM
- detachedCallback - instance **removed** from DOM
- attributeChangedCallback - attrs added, removed or updated


#
## Namespacing approaches

With the whole internet creating new component libraries to be widely used we should prefix components to prevent namespace collisions. No standard or convention currently exists

- company name
- github name
- brand name
- application name

```html
<MY-PREFIX-button></MY-PREFIX-button>
```

## *Reserved names*
```html
<annotationn-xml></annotationn-xml>
<color-profile></color-profile>
<font-face></font-face>
<font-face-src></font-face-src>
<font-face-uri></font-face-uri>
<font-face-format></font-face-format>
<font-face-name></font-face-name>
<missing-glyph></missing-glyph>
```