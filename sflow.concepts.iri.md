---
id: eo43ueh0viren1xkjcjregc
title: Semantic Flow IRIs
desc: ''
updated: 1750464030937
created: 1750368774797
---

### Types of IRIs in Semantic Flow



#### **Content IRIs**

IRIs that point to **concrete information resources** (files on disk or over HTTP):

* **Distribution IRIs** → materialized datasets, e.g. `.ttl`, `.jsonld`, `.trig`, etc.
* **HTML Page IRIs** → e.g. `index.html`
* **Asset IRIs** → e.g. `.png`, `.css`, `.js`

These are *retrievable representations* (materialized content).

---

#### **Referential IRIs**

IRIs that refer to **non-retrievable resources or conceptual entities**, including:

* **Thing IRIs** → People, places, concepts, characters, etc.
* **Namespace IRIs** → Organizational containers
* **Dataset IRIs** → The dataset-as-entity
    * **Dataset Series IRIs** → Versioning containers
    * **Catalog IRIs** → Collections of referents (or datasets)

Even though datasets live under `_data/`, their IRIs refer to datasets **as abstract, non-retrievable entities**. Only Distribution IRIs refer to concrete, downloadable data.

---

### 🧾 Summary Rule of Thumb

- If the IRI ends with a file name, it's a **Content IRI** and has the sense of referring to the concrete, retrievable web resource that it locates**
- If the IRI ends with a slash, it's a **Sense IRI** and it has the sense of refering to an entity (e.g., thing, dataset, series, catalog)**

---

### 🌿 Optional Lexicon (if you want labels)

| IRI Type        | Refers to...              | Example                             |
| --------------- | ------------------------- | ----------------------------------- |
| Namespace IRI | A namespace                 | `/ns/`                       |
| Thing IRI | entity           | `/ns/dave/` (thing)               |
| Dataset IRI | Dataset or dataset series | `/ns/_data/dave/`                 |
| Catalog IRI | Catalog                   | `/ns/dave/_catalog/`              |
| Material IRI    | Distribution file         | `/ns/_data/dave/_dist/dave.ttl` |
| Material IRI    | HTML index                | `/ns/dave/index.html`             |
| Material IRI    | Image, asset, etc.        | `/assets/logo.svg`                  |

---

Let me know if you’d like this turned into a diagram or included in a formal writeup.
