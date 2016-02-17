### Annotation Core ###

The annotation core has been strongly inspired by the model proposed by the [Annotea Project](http://www.w3.org/2001/Annotea/). In both cases, annotations live outside the annotated resource. In particular, the following entities/properties have been extended/reused:

  * [Annotation (class)](http://www.w3.org/2000/10/annotation-ns#Annotation): A super class describing the common features of annotations. The AO class Annotation is sub-classing the Annotea Annotation class and imposing AO related constraints.
  * [annotates](http://www.w3.org/2000/10/annotation-ns#annotates): The relation between an annotation resource and the resource to which the annotation applies. In AO we introduced a sub-property, named _annotates_ as well, where the domain is the class ao:Annotation.
  * [context](http://www.w3.org/2000/10/annotation-ns#context): Context within the resource named in annotates to which the annotation most directly applies. In AO we introduced a sub-property, named _context_ as well, where the domain and range are restricted to AO classes. The Annotea relationship can still be used for XPointer style context specification.
  * [body](http://www.w3.org/2000/10/annotation-ns#body): The content of the annotation. It can be text or a resource identified by a URI.

In Annotea, annotations are typed. It is possible to subclass _Annotation_ into more specific annotation classes with their own In AO we adopt a similar mechanism to cover **tagging, comments, notes, examples, erratum, definition, hypothesis, claims, research questions...** see [AO Annotation Types](AnnotationTypes.md)

| Core OWL File | http://annotation-ontology.googlecode.com/svn/trunk/annotation-core.owl  |
|:--------------|:-------------------------------------------------------------------------|
| Annotea Integration OWL File | http://annotation-ontology.googlecode.com/svn/trunk/annotation-annotea.owl  |

### Annotation of an entire document ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1 - Example of annotation on a whole document with AO. This kind of anntoation is really similar to a Tag with the difference that a semantically defined entity has been used instead of free text. The document provenance section will be omitted in the following examples to keep the pictures simple.<br>
</b>

Using Qualifier(s) is equivalent in tagging a document where, instead of a free text tag, a specific entity in the [PRO ontology](http://pir.georgetown.edu/pro/pro.shtml) has been used.

The RDF of the example in picture 1 would look like the following:
```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <!--
        The following can be added for querying with SPARQL
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        -->
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

> the author:

```
    <rdf:Description rdf:about="http://www.hcklab.org/foaf.rdf#me">
        <rdf:type rdf:resource="http://xmlns.com/foaf/0.1/Person"/>
        <foaf:name>Paolo Ciccarese</foaf:name>
    </rdf:Description> 
```

> and the PRO entry for beta-secretase 1:

```
    <rdf:Description rdf:about="http://purl.obolibrary.org/obo/PRO_000004615">
        <!--
            Properties extracted from the PRO ontology OBO files:

            name: beta-secretase 1
            def: "A protein that is a translation product of the BACE1 gene or a 1:1  ortholog thereof." [PRO:DNx]
            comment: Category=gene.
            synonym: "beta-site amyloid precursor protein cleaving enzyme 1" EXACT []
            synonym: "beta-site APP cleaving enzyme 1" EXACT []
            synonym: "membrane-associated aspartic protease 2" EXACT []
            synonym: "memapsin-2" EXACT []
            synonym: "aspartyl protease 2" EXACT []
            synonym: "Asp 2" EXACT [DNx]
            synonym: "ASP2" EXACT []
            synonym: "BACE1" RELATED []
            synonym: "BACE" RELATED []
            synonym: "KIAA1149" RELATED []
            is_a: PRO:000000001 ! protein
        -->
    </rdf:Description> 

```


### Annotation of a document part ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2 - Example of text annotation with AO. Using Qualifier(s) is equivalent in performing tagging of a part of the document where, instead of a free text tag, a specific entity in this case from the <a href='http://pir.georgetown.edu/pro/pro.shtml'>PRO ontology</a> has been used. </b>

The RDF of the example in picture 2 would look like the following:
```
    <rdf:Description rdf:about="http://my.example.org/ann/21300">
        <rdf:type rdf:resource="&aot;ExactQualifier"/>
        <!--
        The following can be added for querying with SPARQL
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        -->
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:context rdf:resource="http://my.example.org/sel/10300"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description>
```

and the text selector (PrefixPostfixSelector):

```
    <rdf:Description rdf:about="http://my.example.org/sel/10300">
        <rdf:type rdf:resource="&aos;TextSelector"/>
        <rdf:type rdf:resource="&aos;PrefixPostfixSelector"/>
        <aos:exact>BACE1</aos:exact>
        <aos:prefix>Cognitive and behavioral deficits related to</aos:prefix>
        <aos:postfix>inhibition may be magnified in humans who</aos:postfix>
        <ao:onSourceDocument rdf:resource="http://my.example.org/sd/1339"/>
        <aof:onDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
    </rdf:Description>
```

with a different text selector (OffsetRangeSelector) it would have been:

```
    <rdf:Description rdf:about="http://my.example.org/sel/10300">
        <rdf:type rdf:resource="&aos;TextSelector"/>
        <rdf:type rdf:resource="&aos;OffsetRangeSelector"/>
        <aos:exact>BACE1</aos:exact>
        <aos:offset>765</aos:offset>
        <aos:range>5</aos:range>
        <ao:onSourceDocument rdf:resource="http://my.example.org/sd/1339"/>
        <aof:onDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
    </rdf:Description>
```

---

[Namespaces used above](Namespaces.md)