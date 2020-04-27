
# HTML5 Web Components

## Why?

- Current websites use undescriptive markup, generice divs, spans etc
- No component standard
- Style conflicts, which results in hacks using iframes or !important
- No native templates so lots of different approaches used by different frameworks
- No bundling standard to bundle all
- Static site generators require minimal amount of tooling using web components, masisvely reducing bundle size (Static sites make up for large percentage of the web)

Web components are not here to tackle state management within the UI, thats the purpose of the framework. Web Components are about allowing use of the same UI components across frameworks.
Frameworks allow for things such as concurrent rendering which are not included in web standard

#
## Solution?
### **Web Components**

4 new technologies encompass and solve the previous problems

- Templates
	- allow inert reusable markup
- Custom Elements
	- Define our own elements extending existing html elements
- Shadow DOM
	- encapsulation of markup & styling
- Imports
	- Supports bundling of HTML, JS & CSS into single package

#
## Why learn web components?

It's important to know the underlying functionality before the  abstraction, otherwise you won't undertsand why the avstraction has broken and thus how to fix your issues.

Fewer integration mistakes, clearer common ap/interface, easily replaced and upgraded, descriptive markup!!
