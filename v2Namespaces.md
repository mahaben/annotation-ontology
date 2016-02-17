[<< Back to Main](v2Main.md)

### Annotation Ontology v.2 Architecture and Namespaces ###

While the v.1 of Annotation Ontology (AO) was composed by several modules (and relative files), in v.2 the number of namespaces has been reduced to one:

| **Prefix** | **Name and Description**| **Namespace** |
|:-----------|:------------------------|:--------------|
| ao         | **Annotation Ontology Core**. It defines the core functionalities of AO including the tools for organizing annotation items in sets and sets in perspectives. It includes all the officially available Selectors and Annotation Types. | http://purl.org/ao/|

To import Annotation Ontology Core:
```
   <owl:imports rdf:resource="http://purl.org/ao/"/>
```

### Integration modules ###
These are additional modules that integrate AO with FOAF and Annotea. Annotation Ontology v2 does not require these modules to operate but they can be used for integration purposes.

| **Prefix** | **Name and Description**| **Namespace** |
|:-----------|:------------------------|:--------------|
| aof        | **Annotation Ontology Integration with FOAF**. This module is optional and offers specific properties and mappings to FOAF. | http://purl.org/ao/foaf/ |
| aoa        | **Annotation Ontology Integration with Annotea**. This module is optional and enables back compatibility with Annotea content. | http://purl.org/ao/annotea/ |

### Related Ontologies Namespaces ###
The following namespaces will be used in explanations and examples.
| pav | Provenance, Authoring and Versioning (v. 2.0) | http://purl.org/pav/ |
|:----|:----------------------------------------------|:---------------------|
| ann | Annotea                                       | http://www.w3.org/2000/10/annotation-ns# |
| pro | PRotein Ontology (PRO)                        | http://purl.obolibrary.org/obo/ |
| foaf | Friend Of A Friend (FOAF)                     | http://xmlns.com/foaf/0.1/ |
| dct | Dublin Core Terms                             | http://purl.org/dc/terms/ |
| sioc | SIOC Ontology                                 | http://rdfs.org/sioc/ns# |
|sioct| SIOC Ontology Types                           | http://rdfs.org/sioc/types# |
| cnt | W3C Content Vocabulary                        | http://www.w3.org/2008/content# |
| ore | Object Reuse and Exchange                     | http://www.openarchives.org/ore/terms/ |