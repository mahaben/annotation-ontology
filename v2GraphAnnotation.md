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

# Graph Annotation #

When the annotation content is intended for machines and is described by a set of triples about a resource, it is recommended to collect them in a graph and to refer to them through an _Annotation_ of type _ao:GraphAnnotation_.

### Named Graph ###

| [Named Graphs](http://en.wikipedia.org/wiki/Named_graph) is the idea that having multiple RDF graphs in a single document/repository and naming them with URIs provides useful additional functionality built on top of the RDF Recommendations. |
|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

With annotation of the type ao:GraphAnnotation it is possible to attach a set of statements to a target, these are the result of the annotation process carried out in specific conditions that can be encoded in the provenance data. This is the case of the following example in [TriG format](http://www4.wiwiss.fu-berlin.de/bizer/trig/):

```
 # Example #1

{
 <http://www.example.org/annotation/10030> a ao:GraphAnnotation ;
    ao:annotatesResource <http://alturl.com/xxbxn> ;
    ao:body :graphExample ;
    pav:createdWith <http://annotaitonframework.org/foaf.rdf#me> ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
}

:graphExample {
    <http://alturl.com/xxbxn> a foaf:Image ;
        foaf:depicts <http://dbpedia.org/page/Eiffel_Tower> .
}
```

The example #1 could be depicted as follows:

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Graph%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Graph%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />

### Graphs as inline content ###

Graphs can be used also to incorporate some additional information about topics. For example, an annotation of type ao:Qualifier is expected to point to a dereferenceable URI through the property ao:hasTopic. However, it is possible to include in the annotation some useful information about the topic so that, if the URI is not dereferenceable for any reason, the annotation can still be informative. In [TriG format](http://www4.wiwiss.fu-berlin.de/bizer/trig/):

```
# Example 3: using graph to describe the topic inline

 {
 <http://www.example.org/annotation/10032> a ao:Qualifier, ao:GraphAnnotation ;
    ao:annotatesResource <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> ;
    ao:hasTopic <http://www.hcklab.org/foaf.rdf#me> ;
    ao:body :graphDescription  ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
 }

 :graphDescription {
    <http://www.paolociccarese.info/foaf.rdf#me> a foaf:Person ;
        foaf:name "Paolo Ciccarese" ;
        foaf:homepage "http://www.paolociccarese.info/" .
 }
```

Both types _ao:Qualifier_ and [ao:GraphAnnotation](v2GraphAnnotation.md) have been used. The expectation is that the topic URI is dereferenceable to machine readable content and that the body points to a graph.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Graph%20Annotation%20with%20inline%20topic%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Graph%20Annotation%20with%20inline%20topic%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />

### Graphs for relating multiple targets ###

Another possible use of _ao:GraphAnnotation_ is for relating multiple targets. For example it is possible to state that two annotation instances are not consistent.

For example, two different subject can annotate the same image to be two different things that are not compatible with each other. In the following snippet, the picture of the Eiffel Tower has been related to two entries in Wikipedia that don't seem compatible:

```
# Example 4: graph for relating existing annotations

{
 <http://www.example.org/annotation/10033> a ao:Annotation ;
    ao:annotatesResource <http://alturl.com/xxbxn> ;
    ao:hasTopic <http://en.wikipedia.org/wiki/Eiffel_Tower> ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
}

{
 <http://www.example.org/annotation/10034> a ao:Annotation ;
    ao:annotatesResource <http://alturl.com/xxbxn> ;
    ao:hasTopic <http://en.wikipedia.org/wiki/Tower_bridge> ;
    pav:createdBy <http://www.example.com/person/1> ;
    pav:createdOn "2012-01-12T15:02:14Z"^^xsd:dateTime .
}


{
 <http://www.example.org/annotation/10035> a ao:GraphAnnotation ;
    ao:annotatesResource <http://www.example.org/annotation/10033> ;
    ao:annotatesResource <http://www.example.org/annotation/10034> ;
    ao:body :graphAnnotatingAnnotations ;
    pav:createdBy <http://www.example.com/person/2> ;
    pav:createdOn "2012-01-12T15:02:14Z"^^xsd:dateTime .
}


:graphAnnotatingAnnotations {
    <http://www.example.org/annotation/10033>
        swanrel:inconsistentWith <http://www.example.org/annotation/10034> .
}
```

The example #4 could be depicted as follows - provenance has been omitted to keep the figure simple:

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Graph%20Annotation%20of%20annotations%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Graph%20Annotation%20of%20annotations%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />

In this specific case, recording the geolocation of the person performing the annotation - and her nationality -, would be one way to automatically guess which of the two annotations seems the correct one.