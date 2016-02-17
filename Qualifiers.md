| OWL File | http://annotation-ontology.googlecode.com/svn/trunk/annotation-types.owl  |
|:---------|:--------------------------------------------------------------------------|

### Annotation Type: Qualifier ###

Using Qualifier(s) is equivalent in tagging a document where, instead of a free text tag, a specific entity - identified by a URI - has been used.

<blockquote>
A <b>Qualifier</b> expresses a relationship between the object of the annotation and a well-defined semantic entity. It allows also a free text body. If only the latter is present this is equivalent to a classic tag.<br>
</blockquote>

![http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1 - Example of annotation of type Qualifier. The entire document is linked to the entity Beta-Secretase-1 from the PRotein Ontology (PRO). Defining a Qualifier means relating the annotated document - or part of it - and the semantic entity.</b>


The RDF of the example would look like the following:
```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

the author:

```
    <rdf:Description rdf:about="http://www.hcklab.org/foaf.rdf#me">
        <rdf:type rdf:resource="http://xmlns.com/foaf/0.1/Person"/>
        <foaf:name>Paolo Ciccarese</foaf:name>
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

### Annotation Type: Exact Qualifier ###

<blockquote>
An <b>Exact Qualifier</b> is used when the object of the relationship ao:hasTopic is representing exactly the portion of the annotated document.<br>
</blockquote>

![http://annotation-ontology.googlecode.com/svn/trunk/images/Exact%20Qualifier%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Exact%20Qualifier%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2 - Example of annotation of type Exact Qualifier. The protein Beta-Secretase-1 from the PRotein Ontology (PRO) represent exactly the annotated portion of the document </b>

The RDF of the example would look like the following:
```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&aot;ExactQualifier"/>
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <ao:context rdf:resource="http://my.example.org/sel/10300"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

the text selector:

```
    <rdf:Description rdf:about="http://my.example.org/sel/10300">
        <rdf:type rdf:resource="&ao;Selector"/>
        <rdf:type rdf:resource="&aos;TextSelector"/>
        <rdf:type rdf:resource="&aos;PrefixPostfixSelector"/>
        <aos:exact>BACE1</aos:exact>
        <aos:prefix>Cognitive and behavioral deficits related to</aos:prefix>
        <aos:postfix>inhibition may be magnified in humans who</aos:postfix>
        <aof:onDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:onSourceDocument rdf:resource="http://my.example.org/sd/2332"/>
    </rdf:Description>
```

the author:

```
    <rdf:Description rdf:about="http://www.hcklab.org/foaf.rdf#me">
        <rdf:type rdf:resource="http://xmlns.com/foaf/0.1/Person"/>
        <foaf:name>Paolo Ciccarese</foaf:name>
    </rdf:Description> 
```

the source document:

```
    <rdf:Description rdf:about="http://my.example.org/sd/2332">
        <rdf:type rdf:resource="&pav;SourceDocument"/>
        <pav:retrievedFrom rdf:resource="http://tinyurl.com/ykjn87p"/>
        <pav:sourceAccessedOn>2010-03-26</pav:sourceAccessedOn>
    </rdf:Description> 
```

### Annotation Type: Broad Qualifier ###

<blockquote>
A <b>Broad Qualifier</b> is used when the object of the relationship ao:hasTopic is representing broadly the portion of the annotated document.<br>
</blockquote>

![http://annotation-ontology.googlecode.com/svn/trunk/images/Broader%20Qualifier%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Broader%20Qualifier%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 3 - Example of annotation of type BroadQualifier. The entity 'Skull Fracture' is a more generic concept representing the portion of the image which is tagged as a 'Linear Skull Fracture' as can be read in the ann:body.</b>

The RDF of the example would look like the following:
```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&aot;BroadQualifier"/>
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <ann:body>This is the Linear Skull Fracture</ann:body>
        <ao:context rdf:resource="http://my.example.org/sel/10301"/>
        <aof:annotatesDocument rdf:resource="http://my.ex.org/img102"/>
        <ao:hasTopic rdf:resource="&ontoexample;46560"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

The image selector:

```
    <rdf:Description rdf:about="http://my.example.org/sel/10301">
        <rdf:type rdf:resource="&ao;Selector"/>
        <rdf:type rdf:resource="&aos;ImageSelector"/>
        <rdf:type rdf:resource="&aos;InitEndCornerSelector"/>
        <aof:onDocument rdf:resource="http://my.ex.org/img102"/>
        <aos:init>(304,507)</aos:init>
        <aos:end>(380,618)</aos:end>
    </rdf:Description>
```

### Annotation Type: Narrow Qualifier ###

<blockquote>
A <b>Narrow Qualifier</b> is used when the object of the relationship ao:hasTopic is representing a more specific entity than the portion of the annotated document.<br>
</blockquote>

### Annotation Type: Close Qualifier ###

<blockquote>
A <b>Close Qualifier</b> is used when the object of the relationship ao:hasTopic is representing closely but not exactly the portion of the annotated document.<br>
</blockquote>

---

[Namespaces used above](Namespaces.md)