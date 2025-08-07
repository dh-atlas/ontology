# 📘 Changelog - ATLAS Ontology v2.0

**Version IRI**: [https://w3id.org/dh-atlas/2.0](https://w3id.org/dh-atlas/2.0)  
**Release date**: 2025-08-06  
**Changelog author**: Sebastiano Giacomini

---

## 🚀 Highlights

- Introduced two new classes: `atlas:LanguageModel` and `atlas:3DDigitalTwin`
- Added alignment with external ontologies: [OntoSoft Ontology](http://ontosoft.org/software), [BIBFRAME](http://id.loc.gov/ontologies/bibframe/)
- Removed deprecated namespaces: `foaf`, `swo`
- Multiple RDF property updates and refinements for more precise modelling

---

## 🧩 Updated Namespace Declarations

| Prefix | URI | Change |
|--------|-----|--------|
| `bf` | http://id.loc.gov/ontologies/bibframe/ | ✅ Added |
| `osw` | http://ontosoft.org/software# | ✅ Added |
| `foaf` | http://xmlns.com/foaf/0.1 | ❌ Removed |
| `swo` | http://www.ebi.ac.uk/swo/ | ❌ Removed |

---

## 📦 Changes by Research Product Type

### `schema:Dataset` (generic)
#### 📘 Class Overview
| Version | Class            | Subclasses                                                                                                        |
| ------- | ---------------- | ----------------------------------------------------------------------------------------------------------------- |
| v1.0    | `schema:Dataset` | Digital Scholarly Edition, Text Collection, Linked Open Data, Ontology, Software                                  |
| v2.0    | `schema:Dataset` | Digital Scholarly Edition, Text Collection, Linked Open Data, Ontology, Software, Language Model, 3D Digital Twin |

#### 🔄 Updated Properties
| Property Description     | Previous RDF Property | New RDF Property              | Change Notes                                                                                       |
| ------------------------ | --------------------- | ----------------------------- | -------------------------------------------------------------------------------------------------- |
| Custom Type              | `dct:type`            | `dct:type`                    | Previously used with `fabio:ComputerProgram`. ATLAS recommends using terms from the [KNOT Taxonomy](https://w3id.org/knot/taxonomy/). |
| Size                     | `schema:size`         | `schema:size`                 | Extended from `atlas:TextCollection` to all Research Products.                                           |
| Note on Research Product | `atlas:noteOnSource`  | `atlas:noteOnResearchProduct` | Replaces and generalises previous usage from `atlas:DigitalScholarlyEdition` and `atlas:TextCollection`.                              |
| Mentions                 | —                     | `schema:mentions`             | New property introduced.                                                                           |

### `atlas:Software`
#### 📘 Class Overview
| Version | Class            | Subclass Of                                    |
| ------- | ---------------- | ---------------------------------------------- |
| v1.0    | `atlas:Software` | `schema:Dataset`; `fabio:ComputerProgram`      |
| v2.0    | `atlas:Software` | `schema:Dataset`; `schema:SoftwareApplication` |

#### 🔄 Updated Properties
| Property Description | Previous RDF Property | New RDF Property                | Change Notes                                      |
| -------------------- | --------------------- | ------------------------------- | ------------------------------------------------- |
| Code Repository URL  | `schema:archivedAt`   | `osw:hasCodeLocation`           | Same meaning; OSW term preferred for consistency. |
| Programming Language | `swo:00000741`        | `osw:hasImplementationLanguage` | Same meaning; OSW term preferred for consistency. |
| Input Format         | `swo:0000086`         | `osw:hasInput`                  | Same meaning; OSW term preferred for consistency. |
| Output Format        | `swo:0000087`         | `osw:hasOutput`                 | Same meaning; OSW term preferred for consistency. |


### `atlas:LinkedOpenData`
#### 📘 Class Overview
| Version | Class                  | Subclass Of                        |
| ------- | ---------------------- | ---------------------------------- |
| v1.0    | `atlas:LinkedOpenData` | `schema:Dataset`; `fabio:DataFile` |
| v2.0    | `atlas:LinkedOpenData` | `schema:Dataset`                   |

#### 🔄 Updated Properties
| Property Description            | Previous RDF Property | New RDF Property   | Change Notes                                                                                            |
| ------------------------------- | --------------------- | ------------------ | ------------------------------------------------------------------------------------------------------- |
| RDF Vocabularies and Ontologies | `dct:references`      | `atlas:vocabulary` | Replaces generic reference with `atlas:vocabulary`, which requires a URI identifying a used vocabulary. |

### `atlas:DigitalScholarlyEdition`
#### 🔄 Updated Properties
| Property Description                | Previous RDF Property | New RDF Property              | Change Notes                                                          |
| ----------------------------------- | --------------------- | ----------------------------- | --------------------------------------------------------------------- |
| Edited Work                         | `dct:source`          | `bf:expressionOf`             | More precise modelling.                                               |
| Original Document(s) or Witness(es) | `dct:references`      | `bf:associatedResource`       | Clarifies the relationship with source materials.                     |
| Note on the Edited Text             | `atlas:notesOnSource` | `atlas:noteOnResearchProduct` | Replaces and generalises previous usage from DSE and Text Collection. |
| Facsimile(s) available at           | —                     | `bf:accompaniedBy`            | New property added to indicate linked facsimiles.                     |

### `atlas:TextCollection`
#### 🔄 Updated Properties
| Property Description        | Previous RDF Property | New RDF Property              | Change Notes                                                          |
| --------------------------- | --------------------- | ----------------------------- | --------------------------------------------------------------------- |
| Collected Works             | `dct:source`          | `bf:expressionOf`             | More precise modelling.                                               |
| Note on the Text Collection | `atlas:notesOnSource` | `atlas:noteOnResearchProduct` | Replaces and generalises previous usage from DSE and Text Collection. |
| Geographical Coverage       | —                     | `schema:spatialCoverage`      | New property introduced.                                              |
| Temporal Coverage           | —                     | `schema:temporalCoverage`     | New property introduced.                                              |


### `atlas:LanguageModel` (new class)
#### 📘 Class Overview
| Version | Class                 | Subclass Of                                    |
| ------- | --------------------- | ---------------------------------------------- |
| v2.0    | `atlas:LanguageModel` | `schema:Dataset`; `schema:SoftwareApplication` |

#### 🔄 Properties
| Property Description        | RDF Property                      | Change Notes                                                            |
| --------------------------- | --------------------------------- | ----------------------------------------------------------------------- |
| Task                        | `schema:applicationCategory`      | Inherited from `schema:SoftwareApplication`.                            |
| Execution Specification     | `atlas:noteOnResearchProduct`     | Inherited from `schema:Dataset`.                                        |
| Used Libraries              | `schema:isBasedOn`                | Inherited from `schema:SoftwareApplication`.                            |
| Parameters Number           | `schema:size`                     | Inherited from `schema:Dataset`.                                        |
| Related Dataset Description | `atlas:used → schema:description` | Requires a new `schema:Dataset` instance as the object of `atlas:used`. |
| Related Dataset Size        | `atlas:used → schema:size`        | Requires a new `schema:Dataset` instance as the object of `atlas:used`. |


### `atlas:3DDigitalTwin` (new class)
#### 📘 Class Overview
| Version | Class                 | Subclass Of      |
| ------- | --------------------- | ---------------- |
| v2.0    | `atlas:3DDigitalTwin` | `schema:Dataset` |

#### 🔄 Properties
| Property Description     | RDF Property             | Change Notes                                                                                     |
| ------------------------ | ------------------------ | ------------------------------------------------------------------------------------------------ |
| Has 3D Model             | `schema:associatedMedia` | Property to link a 3D model of type `schema:3DModel`.                                            |
| Reproduces Creative Work | `schema:exampleOfWork`   | Property to link the digital twin to a `schema:CreativeWork` (e.g., a cultural heritage object). |

---

## 🧭 Access Points

### `schema:WebSite`, `schema:SoftwareApplication`
- `fabio:WebSite` → `schema:WebSite`
- `fabio:ComputerProgram` → `schema:SoftwareApplication`
  - `dct:type` → `schema:applicationCategory`

---

## 👥 Agent Updates

### `schema:Person`, `schema:Organization`, `schema:ResearchProject`
- Removed `foaf:Agent` as superclass from both `schema:Person` and `schema:Organization`.
- Introduced the `schema:sameAs` property.

---

## 🧹 Renamed & Deprecated Terms

| Old Name | New Name | Notes |
|----------|----------|-------|
| `atlas:notesOnSource` | `atlas:noteOnResearchProduct` | Generalised and reused across product types |
