# HTML5 Semantic Elements

## Problem Statement

We have `div` elements to organize and label sections of HTML. But too many `div` tags makes our HTML document look cluttered and confusing. Even when we identify or classify them with specific names, it's a lot to keep track of. It would be clearer for both developers and browsers if we could use more descriptive HTML elements to arrange our content. That's where semantic elements come in.

## Objectives

1. Explain the historical reasoning behind semantic elements
2. Identify specific HTML5 semantic elements
 
## Explain the Historical Reasoning Behind Semantic Elements

When developers first began defining containers to structure HTML, they had only one generic element available to them: the `div`. Creating complex page layouts then required dozens of `div` elements that were often difficult to organize or locate within the code. They needed a way to distinguish one `div` from another, which led to `id` and `class` attributes on elements being misused in an attempt to communicate what the `div` was doing. For example, a document usually has only one header, so it seemed sensible to write `div id="header"` as a way to say something stronger than, "this is a text division." Developers wanted to say, "this is a special block of introduction," but lacked the specific language to express it. They wanted those sections to have a semantic meaning.

```html
<div id="header">
  <div class="wrapper">...</div>
</div>
```

When the W3C (the organization that oversees the specifications for HTML and CSS) started writing the specification for HTML5 they wanted to create new elements that would eliminate the need to label so many `div` elements. The goals were to make the code more readable for developers and more descriptive for browsers. It turned out that many developers were already using the same names to label their elements, such as `id="header"`, `id="footer"`, `id="nav"`, `class="article"`, etc. So HTML5 provided semantic elements that explicitly described those functions for developers to use instead.

We once used to have to identify a `div` as our header section.

```html
<div id="header">...</div>
```

Now we use the `header` element.

```html
<header></header>
```

Why do we call these semantic elements? "Semantic" indicates a relationship of meaning. Semantic elements are elements that we use when the content within the element all has the same related meaning. In our `header` example above, all the content we would put within the `header` element would relate to introductory content, such as titles or navigation.

Let's take a layout that uses `div` elements and convert it to use semantic elements instead. This is the markup we begin with:

```html
<div class="wrapper">
  <div id="header">
     <div id="nav">...</div>
  </div>
  <div id="main">
    <div id="music">
      <div id="rock">...</div>
      <div id="jazz">...</div>
    </div>
  </div>
  <div id="aside">...</div>
  <div id="footer">...</div>
</div>
```

Now we'll replace each instance of a `div` with a semantic element that matches the type of content we want it to contain.

```html
<div class="wrapper">
  <header>
     <nav>...</nav>
  </header>
  <main>
    <section id="music">
      <article id="rock">...</article>
      <article id="jazz">...</article>
    </section>
  </main>
  <aside>...</aside>
  <footer>...</footer>
</div>
```

Notice that in cases where the content within the element is not semantically related or we have the need to create a generic box such as the `wrapper`, we can still use `div` elements as we please.

## Identify Specific HTML5 Semantic Elements

Now that we have so many semantic elements we can use in our HTML pages, let's cover the most common and useful ones.

As a developer, keep in mind that while these elements are intended for certain content, there are no hard rules about how to configure them. You should feel comfortable configuring them in any way that makes the most sense to you and best suits your layout needs.

The following descriptions come from the documentation at the Mozilla Developer Network.

### Article

`<article>...</article>`

The HTML `<article>` element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable (e.g., in syndication). This could be a forum post, a magazine or newspaper article, a blog entry, an object, or any other independent item of content. Each `<article>` should be identified, typically by including a heading (`<h1>-<h6>` element) as a child of the `<article>` element.

### Aside

`<aside>...</aside>`

The HTML `<aside>` element represents a section of the page with content connected tangentially to the rest, which could be considered separate from that content. These sections are often represented as sidebars or inserts. They often contain the definitions on the sidebars, such as definitions from the glossary; there may also be other types of information, such as related advertisements; the biography of the author; web applications; profile information or related links on the blog.

### Details

`<details>..</details>`

The HTML Details Element (`<details>`) is used as a disclosure widget from which the user can retrieve additional information.

### Figure & Figcaption

`<figure>...<figcaption>...</figcaption></figure>`

The HTML `<figure>` element represents self-contained content, frequently with a caption (`<figcaption>`), and is typically referenced as a single unit. While it is related to the main flow, its position is independent of the main flow. Usually this is an image, an illustration, a diagram, a code snippet, or a schema that is referenced in the main text, but that can be moved to another page or to an appendix without affecting the main flow.

The HTML `<figcaption>` element represents a caption or a legend associated with a figure or an illustration described by the rest of the data of the `<figure>` element which is its immediate ancestor which means `<figcaption>` can be the first or last element inside a `<figure>` block. Also, the HTML Figcaption Element is optional; if not provided, then the parent figure element will have no caption.

### Footer

`<footer>...</footer>`

The HTML `<footer>` element represents a footer for its nearest sectioning content or sectioning root element. A footer typically contains information about the author of the section, copyright data or links to related documents.

### Header

`<header>...</header>`

The HTML `<header>` element represents a group of introductory or navigational aids. It may contain some heading elements but also other elements like a logo, wrapped section's header, a search form, and so on.

### Main

`<main>...</main>`

The HTML `<main>` element represents the main content of  the `<body>` of a document or application. The main content area consists of content that is directly related to, or expands upon the central topic of a document or the central functionality of an application. This content should be unique to the document, excluding any content that is repeated across a set of documents such as sidebars, navigation links, copyright information, site logos, and search forms (unless the document's main function is as a search form).

### Mark

`<mark>...</mark>`

The HTML Mark Element (`<mark>`) represents highlighted text, i.e., a run of text marked for reference purpose, due to its relevance in a particular context. For example it can be used in a page showing search results to highlight every instance of the searched-for word.

### Nav

`<nav>...</nav>`

The HTML `<nav>` element (HTML Navigation Element) represents a section of a page that links to other pages or to parts within the page: a section with navigation links.

### Section

`<section>...</section>`

The HTML `<section>` element represents a generic section of a document, i.e., a thematic grouping of content, typically with a heading. Each `<section>`should be identified, typically by including a heading (`<h1>-<h6>` element) as a child of the `<section>` element.

### Time

`<time>`

The HTML `<time>` element represents either a time on a 24-hour clock or a precise date in the Gregorian calendar (with optional time and timezone information).

This element is intended to be used presenting dates and times in a machine readable format. This can be helpful for user agents to offer any event scheduling for user's calendar.

## Conclusion

If the content within an element is all semantically related, it is best practice to use the appropriate HTML5 semantic element if one applies. This cleans up our code and makes it more readable for developers and more descriptive to browsers. There are a variety of semantic elements you can use to structure your content, and you can also still use `div` elements to create generic boxes or grouping elements as needed.

## Resources

- [Presentation Slides](https://docs.google.com/presentation/d/1tl0aB0EUOhLMi1Xr19UCAUTCY20FRqEDv-oDGg2cTkg/edit?usp=sharing)
- [HTML5 Semantic Elements Lecture Video](https://www.youtube.com/embed/V28xLFEYaSQ)
- [Dive into HTML5 - Semantic Elements](http://diveintohtml5.info/semantics.html#new-elements)
- [MDN - HTML - Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/HTML5-Semantic-Elements' title='HTML5 Semantic Elements'>HTML5 Semantic Elements</a> on Learn.co and start learning to code for free.</p>
