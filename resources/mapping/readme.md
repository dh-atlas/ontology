# README MAPPING

# About

The ATLAS data model is composed of six main classes:

1. Research Project;
2. Research Product (and its subclasses: Digital Scholarly Edition; Linked Open Data; Ontology; Software; Text Collection);
3. Person;
4. Organization;
5. Computer Program;
6. Web Site.

The classes and properties listed above were selected through a mapping of various existing models, specifically:

- [RO-crate](https://www.researchobject.org/ro-crate/specification/1.1/index.html);
- OpenAIRE ([Graph](https://graph.openaire.eu/docs/) and [Application Profile](https://guidelines.openaire.eu/en/latest/literature/application_profile.html));
- [SKG IF](https://skg-if.readthedocs.io/en/latest/);
- IRIS;
- [KNOT](https://icdp-digital-library.github.io/KNOT/website/ENG/data_model.html).

Following the selection of classes and properties, the ATLAS data model was constructed based on three existing models: [schema.org](https://schema.org/), [Dublin Core](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/) and [FaBiO](https://sparontologies.github.io/fabio/current/fabio.html).

These files represent the outcome of the mapping process and the resulting ATLAS data model.

# Disclaimer

This initial version of the mapping files is provisional.

The following properties presented in the Research Product file are unstable and may be modified in future versions of the mapping:

- Text Collection
    - Edited work (M)
    - Reference to the edited text
    - Bibliographic reference of edited text
    - Specifications on the edited text
    - Author(s) of the edited text
    - Type of the edited text
    - Genre of the items
- Digital Scholarly Edition
    - Edited work (M)
    - Reference to the edited text
    - Bibliographic reference of edited text
    - Specifications on the edited text
    - Author(s) of the edited text
    - Type of the edited text
    - Genre
    - Type of edition