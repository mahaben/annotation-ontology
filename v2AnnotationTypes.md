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

## Annotation Types ##

The following _Annotation Types_ are included in the core of AO. Additional annotation types can be created extended the class _ao:Annotation_ or its subclasses.

| **Type** | **Description** | **Links** |
|:---------|:----------------|:----------|
| [ao:Cursor](v2CursorAnnotation.md) | A **cursor** records the last location of the reading process. |           |
| [ao:Highlight](v2HighlightAnnotation.md) | A **highlight** is the process of marking a fragment of a resource with some - usually visual - mechanism.|           |
| [ao:Tag](v2AnnotationTag.md) | **Tagging** means 'attaching a label'. When using the word **Tag** we here refer only to free text labels. |           |
| [ao:Qualifier](v2AnnotationQualifier.md) | A **qualifier** expresses a relationship between the target of the annotation and a well-defined semantic or structured entity consisting of a term in a controlled vocabulary or ontology.  | [More on Qualifiers](v2StructuredAnnotationQualifiers.md) |
| [ao:GraphAnnotation](v2GraphAnnotation.md) | An annotation where the body is a RDF Named Graph. |           |
| ao:Note  | A **note** is defined as a brief record of facts, topics, or thoughts, written down as an aid to memory. When using the term 'Note' we here refer only to free text notes. |           |
| ao:Erratum | An **erratum** identifies an error in a resource. |           |
| ...      |                 |           |