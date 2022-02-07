---
title: "Adding styling to the PDF"
order: 30
tags:
  - pdfContent
---

As you can see in the PDF, Prince does a lot more than your average 'print to PDF' function.

It makes it possible to do things like:

- add the current page number in the bottom corner
- add page numbers to hyperlinks, like in the table of contents
- add the document title in the header, and the current section title in the footer.

Prince does this with custom CSS rules.

This code, in `src/css/print.css`, controls the header and footer content:

```

/* Set variables to use in the header and footer */
#doctitle {
  string-set: doctitle content();
}

h2.page-break-before {
  string-set: sectionName content();
}
/* Add page number to bottom of pager */
@page {
  /* Add document title to top left */
  @top-left {
    content: string(doctitle);
  }

  /* Add section name to bottom left */
  @bottom-left {
    content: string(sectionName);
  }

  /* Add page number to bottom right */
  @bottom-right {
    content: "Page " counter(page) " of " counter(pages);
  }
}
```
