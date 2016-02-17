Curation is a crucial aspect for performing annotation in scientific communities but not only. A typical example comes from the usage of text mining services. Text mining services produce several annotation items and not all of them are accurate. Often a human curation is required and we need to be able to record the original annotation and the curation performed on it. In the case of text mining services, the results of the curation process can be sent back to the text mining service provider as feedback on the accuracy of the service.

### Examples of Curation ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20Curation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20Curation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1 - Example of curation of an annotation on textual content performed by a text mining service. In this case, the foaf:Person named Paolo Ciccarese accepted the annotation. Other agents such as foaf:Group or foaf:Organization can perform the curation.</b>

The annotation:

```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&ann;Anntoation"/>
        <rdf:type rdf:resource="&ao;Anntoation"/>
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <rdf:type rdf:resource="&aot;ExactQualifier"/>
        <ao:context rdf:resource="http://my.example.org/sel/20300"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.textmining.org/v1"/>
        <pav:curatedBy rdf:resource="http://my.example.org/cur/3472"/>
    </rdf:Description> 
```

the text selector

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

the software:

```
    <rdf:Description rdf:about="http://www.textmining.org/v1">
        <rdf:type rdf:resource="http://purl.org/swan/1.2/agents/Software"/>
        <foaf:name>My text mining v1</foaf:name>
    </rdf:Description> 
```

the curation:

```
    <rdf:Description rdf:about="http://my.example.org/cur/3472">
        <rdf:type rdf:resource="&pav;Curation"/>
        <pav:curates rdf:resource="http://my.example.org/ann/21332"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

the curator:

```
    <rdf:Description rdf:about="http://www.hcklab.org/foaf.rdf#me">
        <rdf:type rdf:resource="http://xmlns.com/foaf/0.1/Person"/>
        <foaf:name>Paolo Ciccarese</foaf:name>
    </rdf:Description> 
```


![http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20Multiple%20Curation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20Annotation%20Multiple%20Curation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2 - Example of multiple curation of an annotation on textual content performed by a text mining service. In this case, the foaf:Person named Paolo Ciccarese rejected the annotation. A second foaf:Person questioned the decision and finally the first foaf:Person made the decision to accept the annotation.</b>

![http://annotation-ontology.googlecode.com/svn/trunk/images/Multiple%20Curation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Multiple%20Curation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 3 - Same example of figure 2, where the relationships between the multiple curation instances are shown.</b>

The first curation:

```
    <rdf:Description rdf:about="http://my.example.org/cur/3472">
        <rdf:type rdf:resource="&pav;Curation"/>
        <pav:curates rdf:resource="http://my.example.org/ann/21332"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

the second curation:

```
    <rdf:Description rdf:about="http://my.example.org/cur/3473">
        <rdf:type rdf:resource="&pav;Curation"/>
        <pav:curates rdf:resource="http://my.example.org/ann/21332"/>
        <pav:previousCuration rdf:resource="http://my.example.org/cur/3472" />
        <pav:createdOn>2010-03-22</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.personexample.org/foaf.rdf#me"/>
    </rdf:Description> 
```

the third curation:

```
    <rdf:Description rdf:about="http://my.example.org/cur/3474">
        <rdf:type rdf:resource="&pav;Curation"/>
        <pav:curates rdf:resource="http://my.example.org/ann/21332"/>
        <pav:previousCuration rdf:resource="http://my.example.org/cur/3473" />
        <pav:createdOn>2010-03-23</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

---

[Namespaces used above](Namespaces.md)