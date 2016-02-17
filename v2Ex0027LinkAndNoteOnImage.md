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

## Annotating an image simultaneously with a URL and a Note ##

If you need to attach to an image a URL and a Note you can do it with two separate annotations. However, sometimes it is necessary to declare explicitly the connection of the two annotations (for example URL and Note). For doing this we attach one or more bodies and one or more topics to the annotation instance.

### The Example ###

In AO it is possible to provide one or mote topics for each basic Annotation Type. Therefore, if we create an annotation of type Note, we can provide one or more URIs as topic(s).

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20URL%20and%20Note%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20URL%20and%20Note%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: example where the user annotates an image with a textual description and a topic defined through a URI ._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20URL%20and%20Note%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20URL%20and%20Note%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: AO representation of a user annotating an image with a textual description and a topic defined through a URI._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
   <ao:body>Perkin's Cove, Ogunquit, Maine</ao:body>
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20URL%20and%20Note%20on%20image%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0027%20URL%20and%20Note%20on%20image%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: AO representation - with Provenance - of a user annotating an image with a textual description and a topic defined through a URI._

The RDF of the example in figure 3, which includes provenance data, would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
   <ao:body>Perkin's Cove, Ogunquit, Maine</ao:body>
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```