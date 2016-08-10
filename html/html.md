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

Attributes and Tags 
============

All tags and attributes must be written in lowercase. Additionally, attribute values should be lowercase when the purpose of the text therein is only to be interpreted by machines. For instances in which the data needs to be human readable, proper title capitalization should be followed.

For machines:
`<meta http-equiv="content-type" content="text/html; charset=utf-8" />`

For humans:
`<a href="http://example.com/" title="Description Here">Example.com</a>`

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
