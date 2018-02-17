# jQuery Basic

`$` - dollar sign operator / bling

<!-- TOC -->

- [jQuery Basic](#jquery-basic)
  - [Linking jQuery to HTML Page](#linking-jquery-to-html-page)
  - [.addClass](#addclass)
  - [.removeClass](#removeclass)
  - [.css](#css)
  - [.prop](#prop)
  - [.html](#html)
  - [.text](#text)
  - [.remove](#remove)
  - [.appendTo](#appendto)
  - [.clone](#clone)
  - [.parent](#parent)
  - [.children](#children)
  - [.child](#child)

<!-- /TOC -->
## Linking jQuery to HTML Page

In order for jQuery to work, you must link your HTML page to the jQuery file.

You can [download the required files](https://jquery.com/download/) and store it on your project's folder.

Or you can use any reliable CDN (Content Delivery Network), such as Google, Microsoft, and Firefox, like so:

```html
// Add directly proceeding the </body> tag.
// At the time of writing, the latest jQuery version is 3.3.1.

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
```


```html
<script>
  $(document.ready(function() {
    // Add jQuery code
  });
</script>
```

## .addClass

Example: `$("___").addClass("animated bounce");`

Fill the underline part with any ID/Class name such as `.well`, `#target` or any element such as `button`, `p`.

## .removeClass

Example: `$("___").removeClass("btn-default");

Fill the underline part with any ID/Class name such as `.well`, `#target` or any element such as `button`, `p`.

## .css

Allows you to change the CSS of an element.

Example: `$("#hero").css("color", "red");`

## .prop

Allows you to adjust the properties of an element

Example: `$(".selectors").prop("disabled", true);

## .html

Changes the text inside an opening and closing tag.

You can embed any HTML tags inside and jQuery will evaluate and render them properly.

Example: `$("h1").html("<i>Hi there</i>");`

## .text

Changes the text inside the opening and closing tag of an element.

Unlike its sibling [`.html`](#html), `.text` does not evaluate any HTML tag. So if you try `<i>Hi</i>`, then the result will not be an italicized version of the word Hi.

Example: `$("h1").html("Hi");`

## .remove

Remove an HTML element.

Example: `$("#target").remove();`

## .appendTo

Append (or *move*) selected HTML elements to another element.

Example: `$("#target").appendTo("#target-2");`

In this example, `target` is appended to `target-2`.

## .clone

Makes a copy of the selected element.

Example: `$("#target").clone();`

But usually you'll do something after performing a clone via **functional chaining**: `("#target").clone().appendTo("#target-2");`

## .parent

Access the parent element of a selected child element.

Example: `$("#inner-child").parent();`

## .children

Access the child element of whichever element you've selected.

Example: `$("#inner-child").children();`

## .child

Select the nth element with the target class or element type.

Here is the format: `target:nth-child(n)`.

Example: `$("#testimonial:nth-child(3)").addClass("animated bounce");`