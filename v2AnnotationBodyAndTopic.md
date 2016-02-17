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

# Combination of Topic (ao:hasTopic) and Body (ao:body) #

When using _ao:Annotation_ with _ao:hasTopic_ it is also possible to add a _ao:body_ property which is usually intended as a description of the object of the _ao:hasTopic_ predicate. Such description can be used when, for any reason, the URI is not dereferenceable.

```
 # Example 1: combining ao:body and ao:hasTopic

 <http://www.example.org/annotation/10023> a ao:Qualifier ;
    ao:annotatesResource <http://www.hcklab.org/images/people/paolo_ciccarese.jpg> ;
    ao:hasTopic <http://www.hcklab.org/foaf.rdf#me>  ;
    ao:body "The image topic is Paolo Ciccarese"@en
    pav:createdBy <http:/www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
```

A similar approach can be used to combine the URI of the topic with a Graph related to it. With this approach, if the topic URI is not dereferenceable, the graph carries information about it. In [TriG format](http://www4.wiwiss.fu-berlin.de/bizer/trig/):

```
 # Example 2: combining ao:body and ao:hasTopic

{
 <http://www.example.org/annotation/10024> a ao:Qualifier, ao:GraphAnnotation ;
    ao:annotatesResource <http://alturl.com/gq3bh> ;
    ao:hasTopic <http://purl.obolibrary.org/obo/PRO_000004168>
    ao:body :graphDescription ;
    pav:createdBy <http://www.hcklab.org/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
}

:graphDescription {
    <http://purl.obolibrary.org/obo/PRO_000004168> a <http://purl.obolibrary.org/obo/PR_000000001> ;
       rdfs:label "amyloid beta A4 protein" ;        
       dct:description "A protein that is a translation product of the APP gene or a 1:1 ortholog thereof." .

    <http://purl.obolibrary.org/obo/PR_000000001>
       rdfs:label "Protein" ;
       dct:description "An amino acid chain that is produced de novo by
            ribosome-mediated translation of a genetically-encoded mRNA." .       
}
```

In the previous example (Example 2), the annotation is of types ao:Qualifier and [ao:GraphAnnotation](v2GraphAnnotation.md). Because of the first type, the expectation is for the topic URI to be machine processable. Because of the second type, the object of the body is expected to be a graph.

**Note**: The example #2 is a short cut for something like the following snippet in [TriG format](http://www4.wiwiss.fu-berlin.de/bizer/trig/). As you may notice, using the graph gives total flexibility. In fact, it is possible to arbitrarily pick the relationship relating the image and the protein.
```
 # Example 3: alternative to example 2

{
 <http://www.example.org/annotation/10024> a ao:GraphAnnotation ;
    ao:annotatesResource <http://alturl.com/gq3bh> ;
    ao:body :graphDescription ;
    pav:createdBy <http://www.paolociccarese.info/foaf.rdf#me> ;
    pav:createdOn "2012-02-12T15:02:14Z"^^xsd:dateTime .
}

:graphDescription {
    <http://alturl.com/gq3bh> a foaf:Image ;
       foaf:depicts <http://purl.obolibrary.org/obo/PRO_000004168>

    <http://purl.obolibrary.org/obo/PRO_000004168> a <http://purl.obolibrary.org/obo/PR_000000001> ;
       rdfs:label "amyloid beta A4 protein" ;        
       dct:description "A protein that is a translation product of the APP gene or a 1:1 ortholog thereof." .

    <http://purl.obolibrary.org/obo/PR_000000001>
       rdfs:label "Protein" ;
       dct:description "An amino acid chain that is produced de novo by
            ribosome-mediated translation of a genetically-encoded mRNA." .       
}
```