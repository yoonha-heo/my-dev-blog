---
title: Sever Side Rendering & Client Side Rendering
date: 2019-07-17 14:07:02
category: Development
---

## How Server Side Rendering works?

We load up .html pages on the server, then the server turns them into useful documents on the user's browsers.
SSR is the traditional rendering method and it worked just as fine until the webs became so complicated and interactive.

- A bit faster at the initial reqeust
- Renders the entire new page each time users visit a page though the page has only subtle differences, whcih leads to the slightly slower load for all subsequent pages.
- Seach engines can crawl the site for better SEO

## How's Client Side Rendering works?

A more recent kind of rendering method where the contents are rendered in the browser via a JavaScript framework. CSR takes two round trips to the server. First request is to get the bare-bones HTML source code which has very little indexable HTML in it, then in the second request, the rest of the site will rendered from .js file using browser.

- Slow initial load
- Once the initial request is complete, it offers blazing fast experience since the users will only be loading a mall section of the page instead of loading the entire page.
- Low SEO if not implemented correctly

## SEO Implications of SSR and CSR

**How Google Search Engine works**

- The first wave requests source code, crawls and indexes present HTML
- It returns for the additional indexable content when the pages are fully rendered and this takes from a few hours to a few weeks.

The initial page with CSR will be like this:

```
<html>
<head>
  <script src="js-framwork.js"></script>
  <script src="app.js"></script>
</head>
<body>
  <div id="root"></div>
</body>
</html>
```

app.js will have all the HTML contents in JS as strings. Before the page is fully rendered, the search engine can't locate any stuff from body.

For SSR, having HTML content in the source code, the search engine can request, crawl and index it during the first wave. Thus it is advantageous to appear in search results in short time.

With CSR, since the content is not rendered until the page is loaded on the browser, the web page will have to wait for the second wave when the indexable content is finally available.

But the thing is not every search engine employs the JS rendering capabilities like Google does. Resulting in web developers struggling with thier CSR not being ranked in search results.

## Solution for this

- SSR for the first page load
- CSR for all subsequent page loads

<br>
<br>
<br>

_Sources_

https://medium.com/@benjburkholder/javascript-seo-server-side-rendering-vs-client-side-rendering-bc06b8ca2383
https://medium.com/@adamzerner/client-side-rendering-vs-server-side-rendering-a32d2cf3bfcc
https://www.freecodecamp.org/news/what-exactly-is-client-side-rendering-and-hows-it-different-from-server-side-rendering-bd5c786b340d/

<br>
<br>
