<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0027: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Exact and Broad Qualifier on text fragment ##

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20Exact%20Broad%20Qualifiers%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20Exact%20Broad%20Qualifiers%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: example with an ExactQualifier and a BroadQualifier on a text fragment._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20Exact%20Broad%20Qualifiers%20on%20document%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20Exact%20Broad%20Qualifiers%20on%20document%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: example with an ExactQualifier and a BroadQualifier on a text fragment._

In figure 1, we depict two annotations for the same text fragment. The first one is of type ExactQualifier? and qualify the text fragment as exactly "Beta Secretase 1" of the PRO ontology. The second one is of type BroadQualifier? and states that BIRNLex Protein is a broader concept than the one represented by the text fragment.

Given the two annotations we could infer that PRO:000004615 is a narrower match (skos:narrowMatch) than BIRNLex:birnlex\_23. Therefore, annotations provided by the same of different users could help, for instance, in mapping concepts belonging to different ontologies.

The RDF of the example would look like the following:
```
<rdf:Description rdf:about="http://my.example.org/ann/21332">
    <rdf:type rdf:resource="&ao;ExactQualifier"/>
    <!-- The following can be added for querying with SPARQL 
    <rdf:type rdf:resource="&ao;Qualifier"/>
    <rdf:type rdf:resource="&ao;Annotation"/>
    -->
    <ao:context rdf:resource="http://my.example.org/sel/10300"/>
    <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/>
    <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
    <pav:createdOn>2010-03-21</pav:createdOn>
    <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
</rdf:Description> 
```

the text selector ([PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)):

```
<rdf:Description rdf:about="http://my.example.org/sel/10300">
    <!-- The following can be added for querying with SPARQL 
    <rdf:type rdf:resource="&ao;PrefixSuffixTextSelector"/>
    <rdf:type rdf:resource="&ao;TextSelector"/>
    <rdf:type rdf:resource="&ao;Selector"/>
    -->
    <ao:exact>BACE1</ao:exact>
    <ao:prefix>Cognitive and behavioral deficits related to</ao:prefix>
    <ao:postfix>inhibition may be magnified in humans who</ao:postfix>
    <ao:onResource rdf:resource="http://tinyurl.com/ykjn87p"/>
</rdf:Description>
```