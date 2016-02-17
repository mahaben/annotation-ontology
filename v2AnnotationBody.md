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

## ao:body ##

| _**ao:body**_ | The _ao:body_ property identifies some content that is somehow about the annotated resource. |
|:--------------|:---------------------------------------------------------------------------------------------|

## Body content as Literals ##

The simplest case of _ao:body_ is when it is modeled as a [rdfs:Literal](http://www.w3.org/TR/rdf-schema/#ch_literal) ([plain](http://www.w3.org/TR/2004/REC-rdf-concepts-20040210/#dfn-plain-literal) or [typed](http://www.w3.org/TR/2004/REC-rdf-concepts-20040210/#dfn-typed-literal)). As we are talking about a Literal, no URI is defined for it.

Here is a very simple example in [Notation3 (N3)](http://www.w3.org/TeamSubmission/n3/):

```
 # Example 1: body as literals

 <http://www.example.org/annotation/10022> a ao:Annotation ;
    ao:annotatesResource <http://annotationframework.org> ;
    ao:body "Domeo Annotation Toolkit homepage"@en ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
```
![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Body%20Annotation%20using%20literals%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Body%20Annotation%20using%20literals%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />

The interpretation of the above set of triples is simple: the textual body "Domeo Annotation Toolkit homepage" is somehow about the resource identified by the URI http://annotationframework.org.

**Notes**:
  * This solution is very simple to implement, however, as no URI is defined for the body content, it will not be possible to directly refer to it or target it with another annotation.
  * It is not recommended to serialize RDF content as a [rdfs:Literal](http://www.w3.org/TR/rdf-schema/#ch_literal), a more appropriate representation is available for this specific use case and makes use of Named Graphs with the annotation type _ao:GraphAnnotation_.

## Body as resource identified by URI ##

In alternative to [rdfs:Literal](http://www.w3.org/TR/rdf-schema/#ch_literal), the _ao:body_ can be modeled as an entity of its own identified by a URI.

### Body identified by dereferenceable URIs ###

Here is a simple example in [Notation3 (N3)](http://www.w3.org/TeamSubmission/n3/) where the the body is identified by a dereferenceable URI, a resource retrieval mechanism that uses any of the internet protocols - e.g. HTTP -  to obtain a copy or representation of the resource it identifies:

```
 # Example 2: body identified by dereferenceable URI

 <http://www.example.org/annotation/10023> a ao:Annotation ;
    ao:annotatesResource <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> ;
    ao:body <http://www.example.org/body/1002.html> ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
```

The interpretation of the above set of triples is simple: the URI linked by the _ao:body_ is a representation about the resource identified by the URI `http://www.hcklab.org/images/people/paolo_ciccarese.jpg`

**Notes**:
  * as it is identified by a resolvable URI, the body content can be published on the web and can be target for external annotations.
  * by using _ao:Annotation_ and _ao:body_ no particular assumption has been made in regards to the nature of the underlying represenation.

### Body identified by URNs ###

URNs can also be used to identify the body. This would allow to specify inline content along with formats and encoding, for instance through the W3C Working Draft [Representing Content in RDF 1.0](http://www.w3.org/TR/Content-in-RDF10/).

```
 # Example 3: URN as body content identifier

 <http://www.example.org/annotation/10022> a ao:Annotation ;
    ao:annotatesResource <http://annotationframework.org> ;
    ao:body <urn:uuid:6e8bc430-9c3a-11d9-9669-0800200c9a66> ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .

 <urn:uuid:6e8bc430-9c3a-11d9-9669-0800200c9a66> a cnt:ContentAsText ;
    cnt:characterEncoding "utf-8" ;
    cnt:char "Domeo Annotation Toolkit homepage" .
    
```

**Notes**:
  * a URN is a URI but it only defines a name, it provides no details about how to get the resource over a network. For locating the resource it is necessary to resort to a resolver.
  * it is not recommended to serialize RDF with this mechanism as it would make it opaque to SPARQL queries. For embedding RDF in the body, see the next section.

## Body as a Named Graph ##

When the annotation content is intended for machines and is described by a set of triples about a resource, it is recommended to collect them in a [Named Graph](http://www.w3.org/2004/03/trix/) and to refer to them. This is the case of the following example in [TriG format](http://www4.wiwiss.fu-berlin.de/bizer/trig/):

```
 # Example 4

{
 <http://www.example.org/annotation/10024> a ao:GraphAnnotation ;
    ao:annotatesResource <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> ;
    ao:body :graphExample ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
}

:graphExample {
    <http://www.hcklab.org/foaf.rdf#me> a foaf:Person ;
        foaf:name "Paolo Ciccarese" ;
        foaf:homepage "http://www.paolociccarese.info/" .
}

```

The above annotation states that the graph _:graphExample_ is about the target image. The graph is usually intended for machine consumption and it is possible to be more specific by stating, in the graph, a more specific relationship of the _foaf:Person_ with the image as follows:

```
 # Graph alternative for Example 4 

:graphExample {
    <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> a foaf:Image .

    <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> foaf:depicts 
        <http://www.hcklab.org/foaf.rdf#me> .

    <http://www.hcklab.org/foaf.rdf#me> a foaf:Person ;
        foaf:name "Paolo Ciccarese" ;
        foaf:homepage "http://www.paolociccarese.info/" .
}

```

In the graphs it is possible to use any ontology of interest exactly as it would work without using Annotation Ontology.

### Other examples ###

  * Hypertextual note targeting an image [(ex0003)](v2Ex0003NoteOnImage.md)
  * Textual note targeting a document [(ex0004)](v2Ex0004NoteOnDocument.md)
  * Note Body as a Document [(ex0033)](v2Ex0033DocumentNoteOnDocument.md)
  * Annotation of Body Document [(ex0034)](v2Ex0034DocumentNoteOnDocument.md)
  * Annotation of Body Document Fragment [(ex0034)](v2Ex0034DocumentNoteOnDocument.md)