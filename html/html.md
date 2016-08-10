Closing Elements
============
All tags must be properly closed. Never omit optional closing tags (e.g. `</li>` or `</body>`) For tags that can wrap nodes such as text or other elements, termination is a trivial enough task. 
For tags that are self-closing, the forward slash should have exactly one space preceding it:
`<br />`

rather than the compact but incorrect:
`<br/>`

[The W3C specifies that a single space should precede the self-closing slash](http://w3.org/TR/xhtml1/#C_2)

Doctype
============
Enforce standards mode and more consistent rendering in every browser possible with this simple doctype at the beginning of every HTML page.

```html
<!DOCTYPE html>
<html>
  <head>
  </head>
</html>
```

Language Attribute
============
From the HTML5 spec:

>Authors are encouraged to specify a lang attribute on the root html element, giving the document's language. This aids speech synthesis tools to determine what pronunciations to use, translation tools to determine what rules to use, and so forth.

Read more about the lang attribute in [the spec](http://reference.sitepoint.com/html/lang-codes).

IE compatibility mode
============
Internet Explorer supports the use of a document compatibility `<meta>` tag to specify what version of IE the page should be rendered as. Unless circumstances require otherwise, it's most useful to instruct IE to use the latest supported mode with edge mode.

```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

Character encoding
============

Quickly and easily ensure proper rendering of your content by declaring an explicit character encoding. When doing so, you may avoid using character entities in your HTML, provided their encoding matches that of the document (generally UTF-8).

```html
<head>
  <meta charset="UTF-8">
</head>
```

CSS and JavaScript includes
============
Per HTML5 spec, typically there is no need to specify a type when including CSS and JavaScript files as text/css and text/javascript are their respective defaults.
```html
<!-- External CSS -->
<link rel="stylesheet" href="code-guide.css">

<!-- In-document CSS -->
<style>
  /* ... */
</style>

<!-- JavaScript -->
<script src="code-guide.js"></script>
```

Attributes and Tags 
============

All tags and attributes must be written in lowercase. Additionally, attribute values should be lowercase when the purpose of the text therein is only to be interpreted by machines. For instances in which the data needs to be human readable, proper title capitalization should be followed.

For machines:
`<meta http-equiv="content-type" content="text/html; charset=utf-8" />`

For humans:
`<a href="http://example.com/" title="Description Here">Example.com</a>`


## Attribute order

HTML attributes should come in this particular order for easier reading of code.

- class
- id, name
- data-*
- src, for, type, href, value
- title, alt
- role, aria-*
Classes make for great reusable components, so they come first. Ids are more specific and should be used sparingly (e.g., for in-page bookmarks), so they come second.

```html
<a class="..." id="..." data-toggle="modal" href="#">
  Example link
</a>

<input class="form-control" type="text">

<img src="..." alt="...">
```


Quotes
============

[All attributes must have a value, and must use double-quotes](http://www.w3.org/TR/xhtml1/#h-4.4). The following are examples of proper and improper usage of quotes and attribute/value pairs.

Correct:
```
<input type="text" name="email" disabled="disabled" />
```

Incorrect:
```
<input type=text name=email disabled>
<input type='text' name='email' disabled='disabled' />
```

In HTML, attributes do not all have to have values, and attribute values do not always have to be quoted. While all of the examples above are valid HTML, failing to quote attributes can lead to security vulnerabilities. Always quote attributes.

Indentation
============
As with PHP, HTML indentation should always reflect logical structure. Use tabs and not spaces.

When mixing PHP and HTML together, indent PHP blocks to match the surrounding HTML code. Closing PHP blocks should match the same indentation level as the opening block.

Correct:
```php
<?php if ( ! have_posts() ) : ?>
    <div id="post-1" class="post">
        <h1 class="entry-title">Not Found</h1>
        <div class="entry-content">
            <p>Apologies, but no results were found.</p>
            <?php get_search_form(); ?>
        </div>
    </div>
<?php endif; ?>
```

Incorrect:
```php
        <?php if ( ! have_posts() ) : ?>
        <div id="post-0" class="post error404 not-found">
            <h1 class="entry-title">Not Found</h1>
            <div class="entry-content">
            <p>Apologies, but no results were found.</p>
<?php get_search_form(); ?>
            </div>
        </div>
<?php endif; ?>
```

Reducing markup
============
Whenever possible, avoid superfluous parent elements when writing HTML. Many times this requires iteration and refactoring, but produces less HTML. Take the following example:
```html
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```
