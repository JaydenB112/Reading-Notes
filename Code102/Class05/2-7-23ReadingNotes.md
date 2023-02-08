# What is CSS?
CSS is a language designed to further be able to control how documents are styled and presented.

When we talk about making a document presentable to your audience, it means optimizing the website or document o loo it's best and transition to different elements easily.

CSS can be used for simple font or color changes, it can create a layout. 

## CSS Syntax 
CSS is a rule based language, rules are defined by specifying groups of styles that should be applied to particular elements or groups of elements on your web page.

If you wanted to make your header red for example, you would frame out the rules for the words to be red.

## CSS Modules 
As here are so many things that you could style using CSS, the language itself is broken down into modules. This way they can be easily grouped on reference pages. While knowing how CSS is structured isn't imperative right now it might be important.

## CSS Specs
All web technologies meaning HTML,CSS,Javascript, etc are defined in documents called specifications. These are published by standards organizations like W3C,WHATWG,and ECMA and they define precisely how these technologies are supposed to behave.

New CSS features are developed by the CSS working group often because web designers are asking for a specific feature, other times because the group itself has identified a requirement.

When a CSS feature has been specified then it is only useful when it has been implemented on one or more browsers. It's unusual for all browsers to implement the feature at the same time, for this reason being able to check implementation progress is important. It's kept on every MDN CSS property page in a table called 'Browser Compatibility".

## External CSS
With an external style sheet, you can change how your website looks without cluttering your html file or origin file.

Each HTML page must include a reference to the external style sheet, or the effects won't be seen on your webpage. You do this by using the < link > element, inside of the head section.

External style sheets need to have .css extensions and can't have HTML tags.

## Internal CSS
A style sheet can be used if one HTML page has it's own unique style.

When using an internal style you must use the < style >, inside the head section.

## Cascading Order 
What style will be used when there is more than one style specified for an HTML element?

All the styles in a page will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:

1. Inline style (inside an HTML element)
2. External and internal style sheets (in the head section)
3. Browser default
So, an inline style has the highest priority, and will override external and internal styles and browser defaults.


