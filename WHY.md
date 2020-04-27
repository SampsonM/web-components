
# HTML5 Web Components

## Why?

- Current websites us undescriptive markup, generice divs, spans etc
- No component standard
- Style conflicts, which results in iframes, !important
- No native templates so lots of approaches with frameworks
- No bundling standard to bundle all
- Static site generators require minimal amount of tooling using web components, masisvely reducing bundle size

Web components are not here to tackle state management within the UI, thats the purpose of the framework. Web Components are about allowing use of the same UI components across frameworks.
Frameworks allow for things such as concurrent rendering, 

#
## Solution?
### **Web Components**

4 new technologies encompass and solve the previous problems

- Templates
	- allow inert reusable markup
- Custom Elements
	- Define our own elements extending html
- Shadow DOM
	- encapsulation of markup & styling
- Imports
	- Supports bundling of HTML, JS & CSS into single package

#
## Why learn web components?

It's important to know the underlying functionality before the  abstraction, otherwise you won't undertsand why the avstraction has broken and thus how to fix your issues.

Fewer integration mistakes, clearer common ap/interface, easily replaced and upgraded, descriptive markup!!
