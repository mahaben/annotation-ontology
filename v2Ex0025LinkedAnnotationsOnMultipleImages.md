<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0025: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Linked Annotations on multiple images ##

### The Example ###

In AO it is possible to provide one or mote topics for each basic Annotation Type. Therefore, if we create an annotation of type Note, we can provide one or more URIs as topic(s).

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0025%20URI%20on%20images%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0025%20URI%20on%20images%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: example of annotating two images with a URI ._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0025%20URI%20on%20images%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0025%20URI%20on%20images%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: how to annotate with AO two images with a topic (URI)._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3uu5z25"/>
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
</rdf:Description> 
```


### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0025%20URI%20on%20images%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0025%20URI%20on%20images%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: how to annotate - including provenance - with AO two images with a topic (URI)._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3uu5z25"/>
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```