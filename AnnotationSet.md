Annotation Set(s) are container of Annotation items. They are used to organize collection of items and refer to them as a whole. This can be particularly useful for defining access restriction rules on a set of Annotation items and/or for grouping Annotation items with similar topic. For instance, in figure 1 the declared topic is PRO:00000001 (Protein).

![http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20Set%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20Set%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1: example of Annotation Set with a single Annotation item. In the same pictures the integration with the SIOC ontology is shown, see <a href='IntegrationWithSIOC.md'>Integration with SIOC</a></b>

The annotation:

```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&ann;Annotation"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.textmining.org/v1"/>
    </rdf:Description> 
```

the software:

```
    <rdf:Description rdf:about="http://www.textmining.org/v1">
        <rdf:type rdf:resource="http://purl.org/swan/1.2/agents/Software"/>
        <foaf:name>My text mining v1</foaf:name>
    </rdf:Description> 
```

the annotation set:

```
    <rdf:Description rdf:about="http://my.example.org/set/21332">
        <rdf:type rdf:resource="&ao;AnnotationSet"/>
        <aof:onDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:item rdf:resource="http://my.example.org/ann/21332"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000000001"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.textmining.org/v1"/>
        <pav:lastUpdatedOn>2010-03-21</pav:createdOn>
        <pav:lastUpdatedBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
        <pav:versionNumber>10</pav:versionNumber>
        <pav:previousVersion rdf:resource="http://my.example.org/set/20332"/>
    </rdf:Description> 
```

In figure 1, the set has a declared topic: "Protein". It could be possible to automatically verify that all the items in the set are actually proteins but this is left to the application. Also, it is possible to associate multiple topics to the _AnnotationSet_ if it is necessary.

![http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20Set%201%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20Set%201%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2: example of Annotation Set with two Annotation items. Even if a pav:createdBy connection has been omitted both annotations have been produced by the text mining service.</b>

The annotation:

```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&ann;Annotation"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.textmining.org/v1"/>
    </rdf:Description> 

    <rdf:Description rdf:about="http://my.example.org/ann/21333">
        <rdf:type rdf:resource="&ann;Annotation"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004168"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.textmining.org/v1"/>
    </rdf:Description>
```

the annotation set:

```
    <rdf:Description rdf:about="http://my.example.org/set/21332">
        <rdf:type rdf:resource="&ao;AnnotationSet"/>
        <aof:onDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:item rdf:resource="http://my.example.org/ann/21332"/>
        <ao:item rdf:resource="http://my.example.org/ann/21333"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000000001"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.textmining.org/v1"/>
        <pav:lastUpdatedOn>2010-03-21</pav:createdOn>
        <pav:lastUpdatedBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
        <pav:versionNumber>10</pav:versionNumber>
        <pav:previousVersion rdf:resource="http://my.example.org/set/20332"/>
    </rdf:Description> 
```


![http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20Set%20Derived%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20Set%20Derived%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 3: example of Annotation Set derived from an existing annotation set - connected by the relationship <i>derivedFrom</i> - and another Annotation Set as new version of an existing one.</b>

---

[Namespaces used above](Namespaces.md)