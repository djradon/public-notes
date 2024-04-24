---
id: 36h5cstfnd55cap4r9jcxlb
title: Yaml
desc: ''
updated: 1713554351719
created: 1700803399777
---

## Features

- "YAML 1.2 is a valid superset of JSON"

## Comparison

### vs [[prdct.json]]

- YAML has overcome JSON’s limitations (e.g., namespace, comment, attribute, and complex configuration).
  - @chatgpt.3.5: " you can create structures in YAML that help organize data in a way that resembles namespaces or scopes in other systems."

## Issues

- YAML lacks protections from corrupted YAML files. [^1]
- why not just assume that if the values don't start with a single or double quote, it should just be interpretted as the whole line is quoted

## Example

![](/assets/images/2023-12-11-11-24-46.png)
![](/assets/images/2023-12-11-11-25-10.png)
![](/assets/images/2023-12-11-11-27-05.png)

## Resources

- https://developers.redhat.com/blog/2020/11/25/how-to-configure-yaml-schema-to-make-editing-files-easier#yaml_schema
- https://yaml-multiline.info/


## References

- [^1]: https://www.nclouds.com/blog/what-is-yaml-data-serialization/
- https://dev.to/this-is-learning/- yaml-collections-sequences-and-mappings-4meb
- https://stackoverflow.com/questions/19109912/yaml-do-i-need-quotes-for-strings-in-yaml