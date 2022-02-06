---
title: Why use this approach?
order: 10
tags:
  - pdfContent
---

### Maintaining multiple versions of a document is hard

If you are publishing a document in multiple formats (eg. a print document designed in InDesign, a Microsoft Word version and HTML content to be inserted into a CMS), it can be difficult to keep each version up to date. If a content change needs to be made, you might need to change it in three places.

Ideally, you should be able to edit content in one place, and then generate multiple outputs from that single source of truth. That's what this approach gives you:

- you edit your content in your preferred content management system
- Eleventy pulls in that content and creates:
  - a website for people reading the information on a screen (eg. computer, tablet, phone)
  - a special 'PDF content' webpage, which forms the basis of the PDF output
- Prince takes the 'PDF content' webpage and turns it into a PDF, for people who want to print out the document

### Word, InDesign require manual accessibility work before publishing

If you want to create an accessible PDF from Microsoft Word or Adobe InDesign, you need to do some manual work before publishing the document.

This can involve making sure:

- the content shows up in the tags of the PDF, so that assistive technology will announce the content of the document properly
- the tags are in the correct order

If you are creating complex layouts, this 'accessibility work' step can take a long time. If you are using tables in Word to align content visually, it can be tedious to remove that table structure so that the content is announced by assistive technology.

If you are creating many documents, this step can slow you down and make it more difficult to make changes later. You might end up directly making text changes to an accessible PDF and hoping that your hacky little changes don't break things.

By using accessible, semantic HTML as the starting point, and using Prince to convert that into a PDF, we can do away with the manual accessibility work step.

HTML is the best starting point for accessible documents because there is no separation between the content and its representation for assistive technology (compare this to 'content' and 'tags' in a PDF).

- semantic information about the content
- the order of the content in the HTML is what assistive technology

This means that you can create a simple webpage, and by using semantic HTML, you can create an accessible document for people who use assistive technology, without the extra accessibility work before publishing.

This also means that Prince can take that webpage, and create an accessible PDF by incorporating that semantic information.
