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

# Annotation Sets #

| **Annotation Set(s)** are container of _Annotation_ items. They are used to organize collection of different items and refer to them as a whole. |
|:-------------------------------------------------------------------------------------------------------------------------------------------------|

This can be particularly useful for defining access restriction rules on a set of _Annotation_ items and/or for grouping _Annotation_ items with similar topic, goal or expectation.

## Simple Example ##

The _AnnotationSet_ is characterized by an identity and by the collection of all the _Annotation_ items that it contains.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Annotation%20Set%2001%20-%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2%20Annotation%20Set%2001%20-%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1: simple example of Annotation Set with a single Annotation item consisting in a semantic tag with the protein BACE1 as topic</b>

The annotation:

```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&ao;Qualifier"/>
        <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

the creator (person):

```
    <rdf:Description rdf:about="http://www.hcklab.org/foaf.rdf#me">
        <rdf:type rdf:resource="http://xmlns.com/foaf/0.1/Person"/>
        <foaf:name>Paolo Ciccarese</foaf:name>
    </rdf:Description> 
```

the annotation set:

```
    <rdf:Description rdf:about="http://my.example.org/set/21332">
        <rdf:type rdf:resource="&ao;AnnotationSet"/>
        <ao:onDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:item rdf:resource="http://my.example.org/ann/21332"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```