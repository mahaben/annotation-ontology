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

## ao:hasTopic ##

| _**ao:hasTopic**_ | The _ao:hasTopic_ property refers to a URI that identifies the subject matter of the targeted resource. |
|:------------------|:--------------------------------------------------------------------------------------------------------|

**Note 1:**
Every annotation is a point of view. Different agents can specify different subject matters while referring to the same resource. Some subject matters can be semantically compatible, some others might be not. This is a desired behavior as long as it is accompanied with proper provenance information.

### General annotation topics ###

The simplest example consists in linking a resource as follow:

```
 # Example 1

 <http://www.example.org/annotation/10023> a ao:Annotation ;
    ao:annotatesResource <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> ;
    ao:hasTopic <http://www.paolociccarese.info/>  ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
```

The interpretation of the above statements is that the targeted image has a topic defined by the URI `http://www.paolociccarese.info/`. As you can easily verify, the URI `http://www.paolociccarese.info/` points to an HTML document, in general, when using the combination _ao:Annotation_ and _ao:hasTopic_, there is no expectation on the nature of the content.

### Machine ready annotation topics ###

By using the annotation type _ao:Qualifier_ and the relationship _ao:hasTopic_ linking a URI, the expectation is to be able, through such URI, to retrieve information that can be read automatically by machines. This URIs can refer to terms belonging to ontologies or to structured data published according to the [Linked Open Data](http://linkeddata.org/) method.

```
 # Example 2

 <http://www.example.org/annotation/10023> a ao:Qualifier ;
    ao:annotatesResource <http://alturl.com/t9yo7> ;
    ao:hasTopic <http://dbpedia.org/page/Paris>  ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
```

Using type _ao:Qualifier_ and the relationship _ao:hasTopic_, the topic identified by the DBpedia entry `http://dbpedia.org/page/Paris` is supposed to enable machine consumption. In fact, when an application reads the URI, it can potentially retrieve additional statements about it (see [Linked Open Data](http://linkeddata.org/)).

See also [Additional resources on the advanced use of Qualifiers](v2StructuredAnnotationQualifiers.md)

**Note 2:**
The above set of statements (Example 2) could be expressed in a less concise way with the construct [ao:GraphAnnotation](v2GraphAnnotation.md) and [ao:body](v2AnnotationBody.md) and a graph such as:

```
 # Alternative to Example 2 (using ao:GraphAnnotation and ao:body)

 {
 <http://www.example.org/annotation/10023> a ao:GraphAnnotation ;
    ao:annotatesResource <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> ;
    ao:body :graphExample  ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
 }

 :graphExample {
    <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> a foaf:Image .

    <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> foaf:depicts 
        <http://www.hcklab.org/foaf.rdf#me> .

    <http://www.hcklab.org/foaf.rdf#me> a foaf:Person ;
        foaf:name "Paolo Ciccarese" ;
        foaf:homepage "http://www.paolociccarese.info/" .
 }
```

This approach is more powerful and flexible. In fact, it is possible to use any domain ontology for defining the relationships - in the above example _foaf:depicts_ - instead of the standard AO relationship _ao:hasTopic_. However, this method less concise and usually more complicated for applications to take care of. The construct _ao:Qualifier_ and _ao:hasTopic_ provides a shortcut.

**Note 3:**
Changing the annotation type of Example 2 back to _ao:Annotation_ is equivalent to referring, for the topic of the target, to an RDF file that has to be intended for human consumption (for a machine it is equivalent to set the topic to an HTML page):

```
 # Alternative to Example 2 (ao:Annotation instead of ao:Qualifier)

 <http://www.example.org/annotation/10023> a ao:Annotation ;
    ao:annotatesResource <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> ;
    ao:hasTopic <http://www.hcklab.org/foaf.rdf#me>  ;
    pav:createdBy <http://www.paolociccarese.info/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
```

Using the _ao:Annotation_ with _ao:hasTopic_ is equivalent to define a topic in a less formal way as the interpretation of the annotation is left to the human agent.