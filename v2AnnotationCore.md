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

### The core of Annotation Ontology ###

Annotation Ontology works around a handful of classes and properties:

  * ao:Annotation is the superclass of every annotation class.
  * ao:annotatesResource identifies the target of the annotation
  * [ao:body](v2AnnotationBody.md) identifies some content that is somehow about the annotated resource.
  * [ao:hasTopic](v2AnnotationTopic.md) refers to a URI that identifies the he subject matter of the targeted resource.

If we want to be more accurate, we can identify a fragment of the annotated resource through the use of selectors:

  * [ao:Selector](v2Selectors.md) identifies, when necessary, a fragment of a resource, and may work differently for different types of documents and content types.
  * ao:context links the annotation with a [ao:Selector](v2Selectors.md)

### Annotation of an entire document ###

### Annotea and Annotation Ontology ###

The annotation core has been strongly inspired by the model proposed by the [Annotea Project](http://www.w3.org/2001/Annotea/). In both cases, annotations live outside the annotated resource. The following entities/properties have been extended/reused in AO:

  * [Annotation (class)](http://www.w3.org/2000/10/annotation-ns#Annotation): A super class describing the common features of annotations. In AO we use the class _ao:Annotation_ sub-class of the Annotea Annotation class with AO related constraints.
  * [annotates](http://www.w3.org/2000/10/annotation-ns#annotates): The relation between an annotation resource and the resource to which the annotation applies. In AO we introduced a sub-property, named _ao:annotates_ where the domain is the class _ao:Annotation_.
  * [context](http://www.w3.org/2000/10/annotation-ns#context): Context within the resource named in annotates to which the annotation most directly applies. In AO we introduced a sub-property, named _ao:context_ as well, where the domain and range are restricted to AO classes _ao:Annotation_ and _ao:Selector_. Read more about the [ao:Selector here](v2Selectors.md).
  * [body](http://www.w3.org/2000/10/annotation-ns#body): The content of the annotation. It can be text - including hypertext - or a resource identified by a URI - an HTML document. Read more about the [use of ao:body here](v2AnnotationBody.md).

In Annotea, annotations are typed. It is possible to subclass _Annotation_ into more specific annotation classes with their own In AO we adopt a similar mechanism to cover **highlights, tagging, comments, notes, examples, errata...** see [AO Annotation Types](v2AnnotationTypes.md)