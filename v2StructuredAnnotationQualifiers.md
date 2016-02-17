<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
<img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Advanced use of Qualifiers ##

The Qualifier is one of the key annotation types in AO as it allows defining a parallelism between AO and the Simple Knowledge Organization System (SKOS) model. A Qualifier is defining a generic connection between the annotated entity and a semantic (or structured) entity. This is mimicking the relationship skos:relatedMatch. Qualifier SKOS-compatible subclasses that are: ExactQualifier, CloseQualifier, NarrowQualifier and BroadQualifier; these correspond respectively to the SKOS properties: skos:exactMatch, skos:closeMatch, skos:broaderMatch and skos:narrowerMatch. See the following table for more details:

| **Annotation Type** | **SKOS Property** | **Definition** |
|:--------------------|:------------------|:---------------|
| Qualifier           | skos:relatedMatch | A **qualifier** expresses a relationship between the target of the annotation and a well-defined semantic or structured entity consisting of a term in a controlled vocabulary or ontology. |
| ExactQualifier      | skos:exactMatch   | Used when the object of the relationship ao:hasTopic is representing exactly the portion of the annotated document. |
| CloseQualifier      | skos:closeMatch   | Used when the object of the relationship ao:hasTopic is representing closely but not exactly the portion of the annotated document. |
| BroadQualifier      | skos:broadMatch   | Used when the object of the relationship ao:hasTopic is representing broadly the portion of the annotated document. |
| NarrowQualifier     | skos:narrowMatch  | Used when the object of the relationship ao:hasTopic is representing a more specific entity than the portion of the annotated document. |

<br />
### Exact and Broad Qualifiers (on document fragment) ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20Exact%20Broad%20Qualifiers%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20Exact%20Broad%20Qualifiers%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: example with an ExactQualifier and a BroadQualifier on a text fragment._

[How to represent an Exact and Broad Qualifier on text fragment in AO](v2Ex0027ExactBroadQualifiers.md)

### Broad Qualifier with note (on image fragment) ###


![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0028%20Broad%20Qualifier%20on%20image%20fragment%20provenance%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0028%20Broad%20Qualifier%20on%20image%20fragment%20provenance%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: example with a BroadQualifier represented by a term from a controlled vocabulary on an image fragment. The free text Note attempts to give a more precise definition of the image fragment._

[How to represent a Broad Qualifier with note on image fragment in AO](v2Ex0028BroadQualifiers.md)