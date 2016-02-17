In Annotea, annotations are typed. It is possible to subclass _Annotation_ into more specific annotation classes with their own properties. In AO we adopt a similar mechanism - it is possible to create annotation types by sub-classing or by composition - to cover **much more than simple tagging: comments, notes, examples, erratum, definition, hypothesis, claims, research questions...** all with respect to the existing ontologies.

| OWL File | http://annotation-ontology.googlecode.com/svn/trunk/annotation-types.owl  |
|:---------|:--------------------------------------------------------------------------|

## Types by sub-classing ##
Like it was happening in Annotea it is possible to create new types simply sub-classing the Annotation class.

### Annotation Type: Note ###

A **Note** is a body of text/html attached to a document or part of it. The class _Note_ is a subclass of the class _Annotation_.

![http://annotation-ontology.googlecode.com/svn/trunk/images/Image%20Annotation%20Note%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Image%20Annotation%20Note%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1 - Example of note in AO. As it was happening in Annotea, in AO we can subclass the Annotation class into a more specific annotation class. In this case we have a Note regarding a portion of an image. The latter is specified through a particular kind of <i>Image Selector</i>.</b>

The RDF of the example in picture 1 would look like the following:
```
    <rdf:Description rdf:about="http://my.example.org/ann/82400">
        <rdf:type rdf:resource="&aot;Note"/>
        <!--
        The following can be added for querying with SPARQL
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        -->
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/37jn32r"/>
        <ao:context rdf:resource="http://my.example.org/sel/20300"/>
        <ann:body>This visual cluster is probably representing the Foo Community</ann:body>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description>
```

and the image selector:

```
    <rdf:Description rdf:about="http://my.example.org/sel/20300">
        <rdf:type rdf:resource="&aos;Selector"/>
        <rdf:type rdf:resource="&aos;ImageSelector"/>
        <rdf:type rdf:resource="&aos;InitEndCornerSelector"/>
        <aof:onDocument rdf:resource="http://tinyurl.com/37jn32r"/>
        <aos:init>(280,30)</aos:init>
        <aos:end>(380,120)</aos:end>
    </rdf:Description>
```

As you might notice, the annotation instance is declared of both type _Note_ and _Annotation_, this is common in RDF to allow querying without the need of inference.

### Annotation Type: Erratum ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20Erratum%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20Erratum%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2 - Example of erratum in AO. The text 'BACE' should be replaced by 'BACE1'. The content of the 'ann:body' can be also HTML.</b>

The RDF of the erratum example:
```
    <rdf:Description rdf:about="http://my.example.org/ann/82400">
        <rdf:type rdf:resource="&aot;Erratum"/>
        <!--
        The following 2 lines have been added for querying with SPARQL
        -->
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <!--
        The previous 2 lines have been added for querying with SPARQL
        -->
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:context rdf:resource="http://my.example.org/sel/20300"/>
        <ann:body>BACE1</ann:body>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description>
```

It would be possible also to develop different types of errata to cover all the possible cases.

### Annotation Type: Qualifier ###

A <b>Qualifier</b> expresses a relationship between the object of the annotation and a well-defined semantic entity. It allows also a free text body. If only the latter is present this is equivalent to a classic tag. For more info on qualifiers see [Qualifiers and Integration with SKOS](Qualifiers.md).

![http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 3 - Example of annotation of type Qualifier. The entire document is linked to the entity Beta-Secretase-1 from the PRotein Ontology (PRO). Defining a Qualifier means relating the annotated document - or part of it - and the semantic entity.</b>

The RDF of the example in picture 3 would look like the following:
```
    <rdf:Description rdf:about="http://my.example.org/ann/82400">
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <!--
        The following 2 lines have been added for querying with SPARQL
        -->
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <!--
        The previous 2 lines have been added for querying with SPARQL
        -->
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>      
        <ao:onSourceDocument rdf:resource="http://my.example.org/sd/2339"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description>
```

the source document:

```
    <rdf:Description rdf:about="http://my.example.org/sd/2339">
        <rdf:type rdf:resource="&pav;SourceDocument"/>
        <pav:retrievedFrom rdf:resource="http://tinyurl.com/ykjn87p"/>
        <pav:sourceAccessedOn>2010-03-26</pav:sourceAccessedOn>
    </rdf:Description> 
```

## Types by composition ##
Instead of subclassing the _Annotation_ class as it was happening in Annotea, it is also possible to define an instance of the annotation inheriting from multiple classes. This approach allows for instance to easily integrate the existing _Discourse Elements_ classes of the [SWAN ontology](http://swan.mindinformatics.org/ontology.html) in the Annotation Ontology (see [Integration with SWAN](SWANDiscourse.md))

---

[Namespaces used above](Namespaces.md)