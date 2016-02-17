[<< Back to Main](v2Main.md)

### Tagging of an image ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/Tag%20image%20-%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/Tag%20image%20-%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1:_

The RDF of the example in picture 1 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10405"/> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

and the text selector (InitEndImageSelector):

```
<rdf:Description rdf:about="http://my.example.org/sel/10405"> 
   <rdf:type rdf:resource="&ao;InitEndImageSelector"/> 
   <!-- 
   <rdf:type rdf:resource="&ao;ImageSelector"/> 
   <rdf:type rdf:resource="&ao;Selector"/> 
   --> 
   <ao:init>(10, 42)</ao:init> 
   <ao:end>(30, 68)</ao:end> 
   <ao:unit>%</ao:unit> 
   <ao:onResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
</rdf:Description> 
```