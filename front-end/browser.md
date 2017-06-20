Browser
==

## Glossary

- **BOM** - The Browser Object Model (BOM) is a browser-specific convention referring to all the objects exposed by the web browser. The `window` object is one of them.
- **CSSOM** - CSS Object Model.
- **DOM** - The Document Object Model (DOM) is a cross-platform and language-independent convention for representing and interacting with objects in HTML, XHTML, and XML documents.
- **Reflow** - When the changes affect document contents or structure, or element position, a reflow (or relayout) happens.
- **Repaint** - When changing element styles which don't affect the element's position on a page (such as background-color, border-color, visibility), the browser just repaints the element again with the new styles applied (that means a "repaint" or "restyle" is happening).

## Rendering

1. The DOM (Document Object Model) is formed from the HTML that is received from a server.
1. Styles are loaded and parsed, forming the CSSOM (CSS Object Model).
1. On top of DOM and CSSOM, a rendering tree is created, which is a set of objects to be rendered. Render tree reflects the DOM structure except for invisible elements (like the <head> tag or elements that have display:none; set). Each text string is represented in the rendering tree as a separate renderer. Each of the rendering objects contains its corresponding DOM object (or a text block) plus the calculated styles. In other words, the render tree describes the visual representation of a DOM.
1. For each render tree element, its coordinates are calculated, which is called "layout". Browsers use a flow method which only required one pass to layout all the elements (tables require more than one pass).
1. Finally, this gets actually displayed in a browser window, a process called "painting".

Source:

- [What Every Frontend Developer Should Know About Webpage Rendering](http://frontendbabel.info/articles/webpage-rendering-101/)
- [Rendering: repaint, reflow/relayout, restyle](http://www.phpied.com/rendering-repaint-reflowrelayout-restyle/)

## Repaint

When changing element styles which don't affect the element's position on a page (such as background-color, border-color, visibility), the browser just repaints the element again with the new styles applied (that means a "repaint" or "restyle" is happening).

## Reflow

When the changes affect document contents or structure, or element position, a reflow (or relayout) happens. These changes are usually triggered by:
- DOM manipulation (element addition, deletion, altering, or changing element order)
- Contents changes, including text changes in form fields
- Calculation or altering of CSS properties
- Adding or removing style sheets
- Changing the "class" attribute
- Browser window manipulation (resizing, scrolling); Pseudo-class activation (:hover)

## References

- [How Browsers Work](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)
- [What Every Frontend Developer Should Know About Webpage Rendering](http://frontendbabel.info/articles/webpage-rendering-101/)