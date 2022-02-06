---
title: "How this works"
order: 20
tags:
  - pdfContent
---

This project uses two tools:

- Eleventy to turn your content into a website
- Prince to turn one of the webpages into an accessible PDF with special CSS rules that affect the PDF output

### Eleventy

Eleventy makes it easy to build HTML webpages by fitting content into a template.

Here's a simple example of how Eleventy works:

- you give Eleventy a HTML template. For example:

```
<html>
  <head>
    <title>{{title}}</title>
  </head>
  <body>
  {{content|safe}}
  </body>
</html>
```

- you give Eleventy some content. For example:

```
---
title: Larry Hudson
---
# About me

My name is Larry. You can follow me on
[Twitter](http://twitter.com/larryhudsondev).
```

- Eleventy builds the finished webpage by fitting the content into the template. This is what the output might look like:

```
<html>
  <head>
    <title>Larry Hudson</title>
  </head>
  <body>
  <h1>About me</h1>
  <p>
    My name is Larry.
    You can follow me on
    <a href="http://twitter.com/larryhudsondev">Twitter</a>.</p>
  </body>
</html>
```

### Prince

Prince is a powerful tool that converts webpages to PDFs.
