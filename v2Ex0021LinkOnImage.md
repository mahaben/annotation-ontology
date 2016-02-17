<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0021: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Annotating an image with a URL ##

### The Example ###

While creating notes with free text is common practice, creating annotation pointing to URIs can be more powerful and easier to understand by machines. In Annotation Ontology (AO) we can create annotation pointing to URIs through the relationship _ao:hasTopic_.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: in this example the Wikipedia link to the town of Ogunquit, Maine is attached to an image as annotation._

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: this is how a linked annotation is represented in AO._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
</rdf:Description> 
```

### Adding provenance: human annotation ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20provenance%20human%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20provenance%20human%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: the same example displaying also provenance data._

The RDF of the example in figure 3 - which include provenance data - would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### Adding provenance: machine annotation ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20provenance%20machine%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20provenance%20machine%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 4: the same example displaying also provenance data. In this case the link to Wikipedia has been crated by a Software._

The RDF of the example in figure 4 - which include provenance data - would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:hasTopic rdf:resource="http://en.wikipedia.org/wiki/Ogunquit"/>
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://my.example.org/service/wikipedia"/> 
</rdf:Description> 
```