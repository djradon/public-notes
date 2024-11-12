---
id: p8g7ilvbyc3mskdg0p11ecg
title: Fair Code
desc: ''
updated: 1731346792919
created: 1674832022532
---

## ChatGPT summary of the 6 fair-code licenses listed on faircode.io on 2024-11-11

The six **fair-code licenses** you've listed are often used by companies to maintain a balance between **open-source principles** and **commercial protection**. These licenses aim to encourage community contributions and open use, while imposing specific restrictions on commercial exploitation. Let's dive into each license and understand the **key differences**:

### 1. **Business Source License (BSL)**
- **Website**: [MariaDB BSL](https://mariadb.com/bsl11)
- **Key Concept**:
  - **Delayed Open Source**: The **BSL** allows a project to be **closed-source** for a certain period (e.g., 3 years), after which it **automatically converts to an OSI-approved open-source license** (often GPL or Apache).
- **Commercial Restriction**:
  - During the initial period, the BSL allows **free usage** for non-commercial purposes but requires a **commercial license** for production use beyond certain limits.
- **Customization**:
  - The license terms allow the author to specify a **change date**, after which the software becomes fully open source.
- **Target Use Case**:
  - Allows companies to **recoup development costs** while eventually releasing software as **fully open**. Used often for databases like **MariaDB**.

### 2. **Commons Clause with Any OSI-Approved License**
- **Website**: [Commons Clause](https://commonsclause.com)
- **Key Concept**:
  - **Additional Restriction Layer**: The **Commons Clause** is an addendum that can be applied to any **OSI-approved open-source license** (e.g., Apache, MIT).
  - It prevents users from **selling** the software on its own.
- **Commercial Restriction**:
  - Restricts **selling** or offering the software as part of a **commercial SaaS** offering.
  - Maintains **open access to code**, but prevents direct **commercial monetization** without permission.
- **Compatibility**:
  - Since it restricts selling, the result is **no longer open-source** by the OSI definition.
- **Target Use Case**:
  - Suitable for projects that want to **limit competition** from for-profit companies while remaining mostly accessible to users and developers.

### 3. **Confluent Community License (CCL)**
- **Website**: [Confluent Community License](https://www.confluent.io/confluent-community-license)
- **Key Concept**:
  - **Source-Available** but with restrictions on certain use cases.
- **Commercial Restriction**:
  - Limits **use in building a competing SaaS** offering. Specifically, you can't use the software to provide a **commercially competing service**.
  - You can **use, modify, and distribute** the software as long as it’s not used to compete with **Confluent’s business** (e.g., offering managed Apache Kafka).
- **Target Use Case**:
  - Protects the creator from direct competition while still encouraging contributions and community use.

### 4. **Elastic License 2.0 (ELv2)**
- **Website**: [Elastic License 2.0](https://www.elastic.co/licensing/elastic-license)
- **Key Concept**:
  - **Source-Available** with limited restrictions.
- **Commercial Restriction**:
  - Prohibits providing the software as a **managed service** or using it to **circumvent licensing** in a way that competes with **Elastic’s commercial offerings**.
  - Allows other use cases, including modifications, development, and self-hosted deployments.
- **Simplification**:
  - ELv2 is a **simplified version** of their earlier license. It specifically tries to address the concerns with providing a **managed competing service** without overly restricting other uses.
- **Target Use Case**:
  - Meant to allow widespread usage, modification, and even commercial distribution, but **restricts SaaS competitors** who want to offer Elastic’s technology without partnering with them.

### 5. **Server Side Public License (SSPL)**
- **Website**: [MongoDB SSPL](https://www.mongodb.com/licensing/server-side-public-license)
- **Key Concept**:
  - Requires that anyone offering the software as a **service** must **open-source all software** that is required to operate the service.
- **Commercial Restriction**:
  - You can **use, modify, and distribute** the software freely, but if you **offer it as a service**, you must open-source not only the changes to the software but also **all the infrastructure and supporting software**.
- **Criticism**:
  - Due to the conditions it imposes on SaaS, **SSPL** is not recognized as **open-source** by the OSI.
- **Target Use Case**:
  - Designed for software like **MongoDB** to prevent cloud providers from profiting by offering it as a **hosted service** without contributing to the broader ecosystem.

### 6. **Sustainable Use License (SUL)**
- **Website**: [n8n Sustainable Use License](https://github.com/n8n-io/n8n/blob/master/LICENSE.md)
- **Key Concept**:
  - Aimed at encouraging **sustainable community use** while preventing exploitation by large, for-profit entities.
- **Commercial Restriction**:
  - The **Sustainable Use License** allows individuals and companies to use and modify the software but **prevents large-scale, direct monetization** by corporations without compensation to the author.
  - The license is **flexible** and includes clauses that **limit specific types of commercial use**, generally those involving offering the software as a hosted service.
- **Open Access**:
  - The source code is **available** for inspection, modification, and contributions, but certain usages (particularly around SaaS) require **negotiating a commercial license**.
- **Target Use Case**:
  - Primarily intended for projects like **n8n** (a workflow automation tool), which want to maintain a balance between **community accessibility** and **commercial sustainability**.

### **Key Differences in Summary**
| License                         | Type              | Commercial Restriction                                                                                      | Target Use Case |
|---------------------------------|-------------------|------------------------------------------------------------------------------------------------------------|----------------|
| **Business Source License**     | Source-available  | Closed for a set period, after which it becomes open source.                                               | Allow eventual open sourcing after a profit period. Used by databases like MariaDB. |
| **Commons Clause + OSI License**| Open + Restrictive| Prevents **selling** the software as a standalone product or for SaaS.                                     | Limit direct competition while keeping open code. |
| **Confluent Community License** | Source-available  | Prevents **building competing services** with the software (e.g., managed SaaS competing with Confluent).  | Protect core revenue while allowing community-driven improvements. |
| **Elastic License 2.0**         | Source-available  | Restricts **managed services** that directly compete with Elastic.                                         | Allow widespread use, restrict competitors from providing SaaS offerings. |
| **Server Side Public License**  | Source-available  | Requires those providing the software as a **service** to **open-source their entire stack**.              | Prevent cloud providers from offering without contributions. |
| **Sustainable Use License**     | Source-available  | Limits **commercial exploitation**, especially for large SaaS providers, without compensating the creator. | Sustainable community use while avoiding exploitation by large for-profit corporations.|

### **Which License Should You Choose?**
- If you want **eventual open source**, consider **BSL**.
- If you want to prevent the software from being sold directly, use **Commons Clause**.
- If you’re concerned about **SaaS competition**, **Confluent Community License**, **Elastic License**, or **SSPL** may be best, depending on how restrictive you want to be.
- If your goal is **sustainable use** with a focus on preventing **exploitation by large players** without fully locking down the code, **Sustainable Use License** may be the right fit.

These licenses all take different approaches to strike a **balance between community collaboration** and **commercial protection**, making them suitable for different types of projects based on your desired level of **openness** and **control** over commercial usage.


## References

- https://faircode.io


