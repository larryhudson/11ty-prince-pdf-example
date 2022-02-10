---
title: "How this works"
order: 20
tags:
  - pdfContent
---

This project uses two tools:

- [Eleventy](https://www.11ty.dev) to turn your content into a website
- [Prince](https://princexml.com) to turn one of the webpages into an accessible PDF with special CSS rules that affect the PDF output

Here is a summary of the workflow:

### 1. You edit your content

Eleventy makes it possible to pull in content from many different sources. So you can write your content in the way you prefer.

You can use:

- [Markdown](https://www.markdownguide.org/) (.md) files inside the Eleventy project - this is the most direct way to get content into your Eleventy site
- a content management system, which Eleventy pulls data from when the site is built - eg. [WordPress](https://wordpress.org/), [Drupal](https://www.drupal.org/), [KeystoneJS](https://keystonejs.com/). The content management system needs to allow you to access the data through an API (eg. a [REST API](https://developer.wordpress.org/rest-api/) or [GraphQL](https://graphql.org/))
- Microsoft Word documents as input with the plugin [eleventy-plugin-docx](https://github.com/larryhudson/eleventy-plugin-docx)

### 2. You create the HTML template, and the PDF template

Inside your Eleventy project, you create the HTML template that the content will be inserted into.

You create two separate templates:

- a template for the website, including the navigation between pages
- a specific template for the PDF content, which Prince will convert to a PDF.

In this project, the [/pdf-content/](/pdf-content/) page is the one that gets converted to a PDF.

You can browse the [source code of this project](https://github.com/larryhudson/11ty-prince-pdf-example/) to see an example of this.

### 3. Eleventy builds the website, and Prince converts the 'PDF content' webpage to a PDF

When you run the 'build' command, Eleventy will build the HTML pages ready for publishing.

With the [eleventy-plugin-prince-pdf](https://github.com/larryhudson/eleventy-plugin-prince-pdf) plugin installed, Prince will automatically convert the specified webpage to a PDF after Eleventy builds the website.

If you deploy to a platform like Netlify, it will automatically rebuild the website each time you make changes to the Git repository. If you're using a CMS, you can also set up a 'webhook' that tells Netlify to rebuild the site, when you make content changes.
