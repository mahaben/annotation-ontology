<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0026: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Qualifier on multiple images ##

A Qualifier is an annotation that attaches a URI with a semantic meaning to a resource. It is different than the annotation of the previous example where the relationship ao:hasTopic was pointing to a URI that could have been, for instance, a webpage with no precise semantics.

### The Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0026%20Qualifier%20on%20images%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0026%20Qualifier%20on%20images%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: example of annotating two images with a Qualifier or semantic tag._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0026%20Qualifier%20on%20images%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0026%20Qualifier%20on%20images%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: how to annotate with AO two images with a Qualifier or semantic tag._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3lxaq52"/> 
   <ao:annotatesResource rdf:resource="http://www.neuronlab.org/images/1228067928.jpg"/>
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0026%20Qualifier%20on%20images%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0026%20Qualifier%20on%20images%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: how to annotate - including provenance - with AO two images with a Qualifier or semantic tag._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3lxaq52"/> 
   <ao:annotatesResource rdf:resource="http://www.neuronlab.org/images/1228067928.jpg"/>
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
   <pav:createdOn>2010-03-21</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```