# 📘 Changelog - ATLAS Ontology v2.0

**Version IRI**: [https://w3id.org/dh-atlas/2.0](https://w3id.org/dh-atlas/2.0)  
**Release date**: 2025-08-06  
**Changelog author**: Sebastiano Giacomini

---

## 1 Highlights

- Introduced two new classes: atlas:LanguageModel and atlas:3DDigitalTwin
- Added alignment with external ontologies: [OntoSoft Ontology](http://ontosoft.org/software), [BIBFRAME](http://id.loc.gov/ontologies/bibframe/)
- Removed deprecated namespaces: foaf, swo
- Multiple RDF property updates and refinements for more precise modelling


## 2 Updated Namespace Declarations

Table 1: Updated Namespace Declarations
| Prefix | URI | Change |
| :---: | :---: | :---: |
| bf | id.loc.gov/ontologies/bibframe/ | $\checkmark$ Added |
| osw | ontosoft.org/software\# | $\checkmark$ Added |
| foaf | xmlns.com/foaf/0.1 | $\times$ Removed |
| swo | ebi.ac.uk/swo/ | $\times$ Removed |


## 3 Changes by Research Product Type

## 3.1 schema:Dataset (generic)

### 3.1.1 Class Overview

Table 2: Class overview by version.
| Version | Class | Subclasses |
| :--- | :--- | :--- |
| v1.0 | schema:Dataset | Digital Scholarly Edition, Text Collection, Linked Open Data, Ontology, Software |
| v2.0 | schema:Dataset | Digital Scholarly Edition, Text Collection, Linked Open Data, Ontology, Software, Language Model, 3D Digital Twin |


### 3.1.2 Updated Properties

Table 3: Updated RDF Properties in version 2.0
| Property Description | Previous RDF Property | New RDF Property | Change Notes |
| :--- | :--- | :--- | :--- |
| Custom Type | dct:type | dct:type | Previously used with fabio: ComputerProgram. ATLAS recommends using terms from the KNOT Taxonomy. |
| Size | schema:size | schema:size | Extended from atlas:TextCollection to all Research Products. |
| Note on Research Product | atlas:noteOnSource | atlas:noteOnResearchProduct | Replaces and generalises previous usage from atlas: DigitalScholarlyEdition and atlas:TextCollection. |
| Mentions | - | schema:mentions | New property introduced. |


## 3.2 atlas:Software

### 3.2.1 Class Overview

Table 4: Class overview for atlas:Software
| Version | Class | Subclass Of |
| :---: | :---: | :---: |
| v1.0 | atlas:Software | schema:Dataset; fabio: ComputerProgram |
| v2.0 | atlas:Software | schema:Dataset; schema:SoftwareApplication |


### 3.2.2 Updated Properties

Table 5: Updated properties for atlas: Software
| Property Description | Previous RDF Property | New RDF Property |
| :--- | :--- | :--- |
| Code Repository URL | schema:archivedAt | osw: hasCodeLocation |
| Programming Language | swo:00000741 | osw: has ImplementationLanguage |
| Input Format | swo:0000086 | osw: has Input |
| Output Format | swo:0000087 | osw:hasOutput |


## 3.3 atlas:LinkedOpenData

### 3.3.1 Class Overview

Table 6: Class overview for atlas:LinkedOpenData
| Version | Class | Subclass Of |
| :---: | :---: | :---: |
| v1.0 | atlas:LinkedOpenData | schema:Dataset; fabio:DataFile |
| v2.0 | atlas:LinkedOpenData | schema:Dataset |


### 3.3.2 Updated Properties

Table 7: Updated properties for atlas:LinkedOpenData
| Property Description | Previous RDF Property | New RDF Property | Change Notes |
| :--- | :--- | :--- | :--- |
| RDF Vocabularies and Ontologies | dct:references | atlas:vocabulary | Replaces generic reference with atlas: vocabulary, which requires a URI identifying a used vocabulary. |


## 3.4 atlas:DigitalScholarlyEdition

### 3.4.1 Class Overview

Table 8: Class overview for atlas:DigitalScholarlyEdition
| Version | Class | Subclass Of |
| :---: | :---: | :---: |
| v1.0 | atlas:DigitalScholarlyEdition | schema:Dataset; fabio:MetadataDocument |
| v2.0 | atlas:DigitalScholarlyEdition | schema:Dataset; fabio:MetadataDocument |


### 3.4.2 Updated Properties

Table 9: Updated properties for atlas:DigitalScholarlyEdition
| Property Description | Previous RDF Property | New RDF Property | Change Notes |
| :--- | :--- | :--- | :--- |
| Edited Work | dct:source | bf: expression0f | More precise modelling. |
| Original Document(s) or Witness(es) | dct:references | bf:associatedResource | Clarifies the relationship with source materials. |
| Note on the Edited Text | atlas:notesOnSource | atlas:noteOnResearchProduct | Replaces and generalises previous usage from atlas:DigitalScholarlyEdition and atlas: TextCollection. |
| Facsimile(s) available at | - | bf:accompaniedBy | New property added to indicate linked facsimiles. |


## 3.5 atlas:TextCollection

### 3.5.1 Class Overview

Table 10: Class overview for atlas:TextCollection
| Version | Class | Subclass Of |
| :---: | :---: | :---: |
| v1.0 | atlas:TextCollection | schema:Dataset; fabio:Anthology |
| v2.0 | atlas:TextCollection | schema:Dataset; fabio:Anthology |


### 3.5.2 Updated Properties

Table 11: Updated properties for atlas:TextCollection
| Property Description | Previous RDF Property | New RDF Property | Change Notes |
| :--- | :--- | :--- | :--- |
| Collected Works | dct:source | bf: expression0f | More precise modelling. |
| Note on the Text Collection | atlas:notesOnSource | atlas:noteOnResearchProduct | Replaces and generalises previous usage. |
| Geographical Coverage | - | schema:spatialCoverage | New property introduced. |
| Temporal Coverage | - | schema:temporalCoverage | New property introduced. |


## 3.6 atlas:LanguageModel (new class)

### 3.6.1 Class Overview

Table 12: Class overview for atlas:LanguageModel
| Version | Class | Subclass Of |
| :---: | :---: | :---: |
| v2.0 | atlas:LanguageModel | schema:Dataset; schema:SoftwareApplication |


### 3.6.2 Properties

Table 13: Properties for atlas:LanguageModel
| Property Description | RDF Property | Notes |
| :--- | :--- | :--- |
| Task | schema:applicationCategory | Inherited from schema:SoftwareApplication. |
| Execution <br> Specification | atlas:noteOnResearchProduct | Inherited from schema: Dataset. |
| Used Libraries | schema:isBasedOn | Inherited from <br> schema:SoftwareApplication. |
| Parameters <br> Number | schema:size | Inherited from <br> schema:Dataset. |
| Related <br> Dataset <br> Description | atlas:used $\rightarrow$ <br> schema:description | Requires a new schema:Dataset instance as the object of atlas: used. |
| Related <br> Dataset <br> Description | atlas:used $\rightarrow$ <br> schema:description | Requires a new schema: Dataset instance as the object of atlas: used. |


## 3.7 atlas:3DDigitalTwin (new class)

### 3.7.1 Class Overview

Table 14: Class overview for atlas:3DDigitalTwin
| Version | Class | Subclass Of |
| :---: | :---: | :---: |
| v2.0 | atlas: 3DDigitalTwin | schema: Dataset |


### 3.7.2 Properties

Table 15: Properties for atlas:3DDigitalTwin
| Property Description | RDF Property | Notes |
| :--- | :--- | :--- |
| Has 3D Model | schema:associatedMedia | Property to link a 3D model of type schema:3DModel. |
| Reproduces Creative Work | schema: exampleOfWork | Property to link the digital twin to a schema:CreativeWork (e.g., a cultural heritage object). |


## 4 Access Points

## 4.1 schema:WebSite, schema:SoftwareApplication

Table 16: Mappings for access-related classes and properties
| Old Term | New Term | Notes |
| :--- | :--- | :--- |
| fabio:WebSite | schema:WebSite | Class mapping for access points - web sites |
| fabio:ComputerProgram | schema:SoftwareApplication | Class mapping for software access |
| dct:type | schema:applicationCategory | Property used within schema:SoftwareApplication |


## 5 Agent Updates

## 5.1 schema:Person, schema:Organization, schema:ResearchProject

Table 17: Updates to agent modeling
| Change | Notes |
| :--- | :--- |
| Removed foaf: Agent superclass | Affects both schema:Person and schema:Organization |
| Introduced schema:sameAs | Supports alignment with external authorities |


## 6 Renamed \& Deprecated Terms

Table 18: Renamed terms in ATLAS v2. 0
| Old Name | New Name | Notes |
| :---: | :---: | :--- |
| atlas:notesOnSource | atlas:noteOnResearchProduct | Generalised and reused <br> across product types |


## 7 Removed Named Individuals

Several named individuals defined in ATLAS v1.0 have been removed in v2.0. These instances represented either:

- Edition types: specific editorial methodologies or strategies;
- Work types: categories of literary artefacts such as diaries, letters, or collected works.


### 7.1 Edition Types

The following individuals, previously used to classify different editorial approaches, have been deprecated. Equivalent concepts are now available in the Edition Types Vocabulary (ETV) at https://w3id.org/dh-atlas-vocabularies/etv:

- atlas:BestManuscriptEdition
- atlas:CriticalEdition
- atlas:DiplomaticEdition
- atlas:DocumentaryEdition
- atlas:EclecticEdition
- atlas:MonotypicEdition
- atlas:SynopticEdition
- atlas:DigitalEdition

These terms were moved to a dedicated vocabulary to improve modularity and enable reuse across ontologies.

### 7.2 Work Types

The following individuals described the type of work or document being edited (e.g., diary, letter, collected works). These have also been removed from the core ontology in v2.0. Equivalent or more precise modelling is expected to rely on external vocabularies or specific metadata fields.

- atlas:CollectedWorks
- atlas:CollectionOfTexts
- atlas:SingleWork
- atlas:SingleManuscript
- atlas:Chapter
- atlas:Diary
- atlas:Letter
- atlas:Paper
- atlas:SerialDocuments
- atlas:Inscription


[^0]:    Note: All changes adopt OSW terms with equivalent meaning, preferred for consistency across software-related properties.

