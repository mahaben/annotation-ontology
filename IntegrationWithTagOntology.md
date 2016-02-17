### Integration with Tag Ontology ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1 - Example of annotation on the whole document with AO.</b>

The example inf figure 1:

```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="Qualifier"/>
        <rdf:type rdf:resource="http://www.w3.org/2000/10/annotation-ns#Annotation"/>
        <ann:annotates rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

can be transposed in [Tag ontology](http://www.holygoat.co.uk/projects/tags/) as:

```
    <tag:RestrictedTagging>
       <tag:taggedResource rdf:resource="http://my.example.org/ann/21332"/>
       <foaf:maker rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
       <tag:tagName>BACE1</tag:tagName>
    </tag:RestrictedTagging>
```