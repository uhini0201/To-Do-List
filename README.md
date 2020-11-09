# To-Do-List

Embedded JavaScript templates<br/>
[![Build Status](https://img.shields.io/travis/mde/ejs/master.svg?style=flat)](https://travis-ci.org/mde/ejs)
[![Developing Dependencies](https://img.shields.io/david/dev/mde/ejs.svg?style=flat)](https://david-dm.org/mde/ejs?type=dev)
[![Known Vulnerabilities](https://snyk.io/test/npm/ejs/badge.svg?style=flat)](https://snyk.io/test/npm/ejs)
=============================

## Installation

```bash
$ npm install ejs
```

## Features

  * Control flow with `<% %>`
  * Escaped output with `<%= %>` (escape function configurable)
  * Unescaped raw output with `<%- %>`
  * Newline-trim mode ('newline slurping') with `-%>` ending tag
  * Whitespace-trim mode (slurp all whitespace) for control flow with `<%_ _%>`
  * Custom delimiters (e.g. `[? ?]` instead of `<% %>`)
  * Includes
  * Client-side support
  * Static caching of intermediate JavaScript
  * Static caching of templates
  * Complies with the [Express](http://expressjs.com) view system

## Example

```ejs
<% if (user) { %>
  <h2><%= user.name %></h2>
<% } %>
```

Try EJS online at: https://ionicabizau.github.io/ejs-playground/.

## Basic usage

```javascript
let template = ejs.compile(str, options);
template(data);
// => Rendered HTML string

ejs.render(str, data, options);
// => Rendered HTML string

ejs.renderFile(filename, data, options, function(err, str){
    // str => Rendered HTML string
});
```

It is also possible to use `ejs.render(dataAndOptions);` where you pass
everything in a single object. In that case, you'll end up with local variables
for all the passed options. However, be aware that your code could break if we
add an option with the same name as one of your data object's properties.
Therefore, we do not recommend using this shortcut.
