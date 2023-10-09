---
id: 8q2u8jftsp9sx5akld4eaq3
title: Polynote
desc: ''
updated: 1696886924463
created: 1694117982293
---

- #url https://polynote.org
- #repo https://github.com/polynote/polynote
- [[p.supports]] [[prdct.vega]] #scala #python

## [[prdct.windows.wsl]]

- https://github.com/polynote/polynote/issues/671 : change listen host to 0.0.0.0

## [[p.vs]]

- Current notebook solutions, like Jupyter and Zeppelin, are lacking in some fundamental features:

    Code editing – the code editing capabilities in most notebook tools leave plenty to be desired. Why can't a notebook tool have modern editing capabilities like those you'd find in an IDE? Polynote provides useful autocomplete, parameter hints, and more – we're planning to add even more features, like jump-to-definition.
    Text editing – you can use the WYSIWYG editor for composing text cells, so you'll know what the text will look like as you're writing. TeX equations are also supported.
    Multi-language support – Polynote allows you to mix multiple languages in one notebook, while sharing definitions seamlessly between them.
    Runtime insight – Polynote tries to keep you informed of what's going on at runtime:
        The tasks area shows you what the kernel is doing at any given time.
        The symbol table shows you what variables and functions you've defined, so you don't have to scroll around to remind yourself.
        Compile failures and runtime exceptions are highlighted in the editor (for supported languages), so you can see exactly what's going wrong.
