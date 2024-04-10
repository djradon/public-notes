---
id: f0rdphtaqbrdl5p8qapzibb
title: Lyo Designer
desc: ''
updated: 1712686216279
created: 1712686192361
---

## Features

Lyo Designer includes a integrated code generator that synthesizes the model into almost-complete Lyo-compliant running implementation. The resulting code includes:

    Java classes with appropriate Lyo annotations to reflect the modelled RDF resource shapes
        This automates the marshaling/unmarshaling of Java instances as Linked Data RDF resources.
    JAX-RS Service operations for accessing, updating, creating and deleting RDF resources.
        These operations handle any of the supported formats (turtle, RDF/XML, Json, etc.)
        For debugging purposes, JSP pages are also produced to deliver HTML representations of all RDF resources.
    JAX-RS Service operations to completely handle Delegated UI for both creation and selection dialogs.
        Including the initial generation of basic JSP pages for the html-representation of the dialogs.
    JAX-RS Service operations to handle Resource Preview
        Including the initial generation of basic JSP pages for the html-representation of the resource previews.

Lyo Designer supports incremental development, where manual changes to the generated code are preserved upon changes to the model, and subsequent code regeneration.