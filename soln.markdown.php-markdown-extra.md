---
id: 659fUF9wKybhz2RU7d3lj
title: Php Markdown Extra
desc: ''
updated: 1638021085782
created: 1637979232539
---


- [[p.hasSpecification]] https://michelf.ca/projects/php-markdown/extra/
- [ ] PHP Markdown Extra has ideas for [[gd]] and fixes for [[soln.Dendron]]

## Special Attributes

With Markdown Extra, you can set the id and class attribute on certain elements using an attribute block. For instance, put the desired id prefixed by a hash inside curly brackets after the header at the end of the line, like this:

Header 1            {#header1}
========

## Header 2 ##      {#header2}

Then you can create links to different parts of the same document like this:

[Link back to header 1](#header1)

To add a class name, which can be used as a hook for a style sheet, use a dot like this:

## The Site ##    {.main}

You can also add custom attributes having simple values by specifying the attribute name, followed by an equal sign, followed by the value (which cannot contain spaces at this time):

## Le Site ##    {lang=fr}

The id, multiple class names, and other custom attributes can be combined by putting them all into the same special attribute block:

## Le Site ##    {.main .shine #the-site lang=fr}

At this time, special attribute blocks can be used with

    headers,
    fenced code blocks,
    links, and
    images.

For image and links, put the special attribute block immediately after the parenthesis containing the address:

[link](url){#id .class}  
![img](url){#id .class}

...

You can specify a class name that will apply to a code block. This is useful if you want to style differently code blocks depending on the language. Or you could also use it to tell a syntax highlighter what syntax to use.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~ .html
<p>paragraph <b>emphasis</b>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The class name is placed at the end of the first fence. It can be preceded by a dot, but this is not a requirement. You can also use a special attribute block:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~ {.html #example-1}
<p>paragraph <b>emphasis</b>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

