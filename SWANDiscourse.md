## Integration with the SWAN 2.0 Discourse Elements ##

AO can be integrated with any version of the SWAN Ontology. However, the following examples are related to SWAN Ontology 2.0

### Annotation Type: SWAN Claim ###

```
    <rdf:Description rdf:about="http://my.example.org/ann/82400">
        <rdf:type rdf:resource="http://purl.org/swan/2.0/discourse-elements/Claim"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/2ak4nkd"/>
        <swande:description>Testosterone may play an important role in the prevention of
                Alzheimer’s disease (AD) in men</swande:description>
        ...
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description>
```

### Annotation Type: SWAN Hypothesis ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20swan%20hypothesis%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Annotation%20swan%20hypothesis%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />

```
    <rdf:Description rdf:about="http://my.example.org/ann/82400">
        <rdf:type rdf:resource="http://purl.org/swan/2.0/discourse-elements/Hypothesis"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/27z7ow2"/>
        <swande:description> Genetic depletion of aromatase in male APP transgenic mice
                down-regulates beta-secretase (BACE1) and prevents Alzheimer-like 
                pathology and cognitive impairment</swande:description>
        <swanrel:cites rdf:resource="http://purl.org/obo/owl/HP#HP_0002511" />
        ...
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description>
```

### Annotation Type: SWAN Research Question ###

```
    <rdf:Description rdf:about="http://my.example.org/ann/82400">
        <rdf:type rdf:resource="http://purl.org/swan/2.0/discourse-elements/ResearchQuestion"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/25gcavg"/>
        <swande:description>Can overexpressed DR6 in neurons trigger ligand-independent
                degeneration, as reported for p75NTR?</swande:description>
        ...
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description>
```