### Annotation Ontology Architecture and Namespaces ###

Annotation Ontology (AO) is composed by the following modules (files):
  * **core**: is defining the core functionalities of AO including the tools for organizing annotation items in sets and sets in perspectives.
  * **selectors**: is listing all the currently available [selectors](Selectors.md).
  * **types**: is defining all the [annotation types](AnnotationTypes.md) other than the generic  _Annotation_
  * **Annotea Integration**: is defining the mapping of AO with the Annotea project ontology.
  * **FOAF Integration**: is defining the mapping and the constraints to integrate AO with the FOAF vocabulary.

These can be imported in one shot as follow:

```
   <owl:imports rdf:resource="http://purl.org/ao/"/>
```

Here are the correspondent namespaces with the prefixes as they will used in the rest of the documentation:

| **Prefix** | **Name**| **Namespace**|
|:-----------|:--------|:-------------|
| ao         | **Annotation Core** |  http://purl.org/ao/core/|
| aot        | **Annotation Types** | http://purl.org/ao/types/ |
| aos        | **Annotation Selectors** | http://purl.org/ao/selectors/ |
| aoa        | **Annotation Ontology Integration with Annotea** | http://purl.org/ao/annotea/ |
| aof        | **Annotation Ontology Integration with FOAF** | http://purl.org/ao/foaf/ |

<br />
### Related Ontologies Namespaces ###
| pav | Provenance, Authoring and Versioning (v. 2.0) | http://purl.org/pav/ |
|:----|:----------------------------------------------|:---------------------|
| ann | Annotea                                       | http://www.w3.org/2000/10/annotation-ns# |
| pro | PRotein Ontology (PRO)                        | http://purl.obolibrary.org/obo/ |
| foaf | Friend Of A Friend (FOAF)                     | http://xmlns.com/foaf/0.1/ |
| dct | Dublin Core Terms                             | http://purl.org/dc/terms/ |
| sioc | SIOC Ontology                                 | http://rdfs.org/sioc/ns# |
|sioct| SIOC Ontology Types                           | http://rdfs.org/sioc/types# |