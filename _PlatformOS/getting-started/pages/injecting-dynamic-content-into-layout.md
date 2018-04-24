---
title: Injecting Dynamic Content into a Layout
permalink: /get-started/pages/injecting-dynamic-content-into-layout
---
This guide will help you inject dynamic content from a page into a layout using the `content_for` and `yield` tags. This is often used when setting metadata for a particular page (i.e. title tag contents), loading per-page javascript, or per-page stylesheet. 

## Requirements
To follow the steps in this tutorial, you should have created a page and a layout. 

* [Creating a Page]()
* [Creating a Layout]()

## Steps 

Injecting dynamic content into a layout is a two-step process:

1. Use `yield` in layout
2. Use `content_for` in page

### Step 1: Use `yield` in layout

Add the yield tag to the previously created `application.liquid` layout file, e.g. switch the layout title to dynamic content with the `yield` tag: 

{% raw %}

```liquid
<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <title>
  {% yield 'meta_title' %}
  </title>
</head>

<body>
<h1>Layout</h1>
{{ content_for_layout }}

</body>

</html>

```

{% endraw %}


### Step 2: Use `content_for` in page

Add the `content_for` tag in the previously created `home.liquid` page. The positioning of this line doesn't matter as long as it's in the content part of the page. 

{% raw %}

```liquid
---
slug: /
---

{% content_for 'meta_title' %}Homepage title{% endcontent_for %}


Homepage
```

{% endraw %} 

Sync or deploy. You can now see that the Homepage title is displayed in your browser's title bar or tab. 

Add `content_for` to all pages in the same way, and the page title will be dynamically displayed for each page. 

## Next steps
Congratulations! You have injected dynamic content into a layout. Now you can learn how to reuse code across multiple pages using partials.  

* [Reusing Code Across Multiple Pages]()

## Questions?

We are always happy to help with any questions you may have. Consult our  [documentation](), [contact support](), or  [connect with our sales team](). 