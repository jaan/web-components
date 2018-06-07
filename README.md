# web-components
Web components gotcha's



## Custom Elements
1. The name of a custom element must contain a dash (-). So `<x-tags>`, `<my-element>`, and `<my-awesome-app>` are all valid names, while <tabs> and <foo_bar> are not. This requirement is so the HTML parser can distinguish custom elements from regular elements. It also ensures forward compatibility when new tags are added to HTML.
2. You can’t register the same tag more than once. Attempting to do so will throw a DOMException. Once you’ve told the browser about a new tag, that’s it. No take backs.
3. Custom elements cannot be self-closing because HTML only allows a few elements to be self-closing. Always write a closing tag (`<app-drawer></app-drawer>`).
4. Set a :host display style (e.g. block, inline-block, flex) unless you prefer the default of inline.  
  4.1  Custom elements are display: inline by default, so setting their width or height will have no effect. This often comes as a surprise to developers and may cause issues related to laying out the page. Unless you prefer an inline display, you should always set a default display value.
