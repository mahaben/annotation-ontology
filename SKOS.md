### Qualifiers and SKOS ###

Qualifier is one of the key annotation types in AO as it allows defining a parallelism between AO and the Simple Knowledge Organization System (SKOS) model. A Qualifier is defining a generic connection between the annotated entity and a semantic entity. This is mimicking the relationship skos:relatedMatch. Qualifier SKOS-compatible subclasses that are: ExactQualifier, CloseQualifier, NarrowQualifier and BroadQualifier; these correspond respectively to the SKOS properties: skos:exactMatch, skos:closeMatch, skos:broaderMatch and skos:narrowerMatch. See the following table for more details:

| **Annotation Type** | **SKOS Property** | **Definition** |
|:--------------------|:------------------|:---------------|
| Qualifier           | skos:relatedMatch | It expresses a relationship between the object of the annotation and a well-defined semantic entity. It allows also a free text body. If only the latter is present this is equivalent to a tag. |
| ExactQualifier      | skos:exactMatch   | Used when the object of the relationship ao:hasTopic is representing exactly the portion of the annotated document. |
| CloseQualifier      | skos:closeMatch   | Used when the object of the relationship ao:hasTopic is representing closely but not exactly the portion of the annotated document. |
| BroadQualifier      | skos:broadMatch   | Used when the object of the relationship ao:hasTopic is representing broadly the portion of the annotated document. |
| NarrowQualifier     | skos:narrowMatch  | Used when the object of the relationship ao:hasTopic is representing a more specific entity than the portion of the annotated document. |

### How this can be used for ontology building/linking ###


![http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20and%20SKOS%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20and%20SKOS%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1 - Two annotations on the same text fragment using two different vocabularies.</b>

In figure 1, we depict two annotations for the same text fragment. The first one is of type ExactQualifier and qualify the text fragment as exactly "Beta Secretase 1" of the PRO ontology. The second one is of type BroadQualifier and states that BIRNLex Protein is a broader concept than the one represented by the text fragment.

Given the two annotations we could infer that PRO:000004615 is a narrower match (skos:narrowMatch) than BIRNLex:birnlex\_23. Therefore, annotations provided by the same of different users could help, for instance, in mapping concepts belonging to different ontologies.