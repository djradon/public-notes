---
id: 6depmxxn1wui5t4tpdavwkb
title: Annotation of Multimedia Using onto Media
desc: ''
updated: 1727985418002
created: 1727984428790
---

- https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=13a85dd949eefca66c4f6b69187b381a5b5ffd0d
- authors: @michael-jewell @faith-lawrence @m-schraefel
- mentions: [[prdct.fiction-finder]] [[prdct.screenplays-in-xml-six]]

## Abstract

While ontologies exist for the annotation of monomedia, interoperability between these schemes is an important issue. The OntoMedia ontology consists of a generic core, capable of representing a diverse range of media, as well as extension ontologies to focus on specific formats. This paper provides an overview of the OntoMedia ontologies, together with a detailed case study when applied to video, a scripted form, and an associated short story.

## Highlights

### Annotating Multimedia: A Case Study

-  a scene from [[video.total-recall]] was annotated such that the script and associated characters could be represented the framework. The characters from the related book, ‘[[We Can Remember It For You Wholesale|book.we-can-remember-it-for-you-wholesale]]’ were also annotated, and our example queries demonstrate how the two forms may be linked
-  

```xml
<?xml version="1.0" encoding="iso-8859-1" standalone="no" ?>
<sc:script xmlns="http://www.w3.org/1999/xhtml"
xmlns:dc="http://purl.org/dc/elements/1.1/"
xmlns:sc="http://mikesroom.org/script">
  <sc:info>
  <dc:title>Total Recall</dc:title>
  </sc:info>
  
  <sc:location time="day" pos="int">HILTON - CORRIDOR/SERVICE ELEVATOR - 6TH FL.</
  sc:location>
  <sc:dialogue speaker="Lori">Doug...you wouldn&apos;t hurt me, would you, honey?
  </sc:dialogue>
  <sc:direction>She sees his expression.</sc:direction>
  <sc:dialogue speaker="Lori" ctd="1">Sweetheart, be reasonable...We&apos;re
  married.</sc:dialogue>
  <sc:direction>Lori stealthily reaches behind her back for a concealed gun and
  pulls it on him.</sc:direction>
  <sc:direction>Quaid shoots Lori in the forehead, leaving a clean, small hole
  between her eyes.</sc:direction>
  <sc:dialogue speaker="Quaid" paren="rising, to Melina">Consider that a divorce.
  </sc:dialogue>
</sc:script>
```