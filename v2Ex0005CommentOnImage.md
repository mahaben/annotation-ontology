<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0005: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Comment targeting an image as a whole ##

| _A **Comment** is a remark expressing an opinion or reaction. When using the term 'Comment' we here refer only to free text comments._ |
|:---------------------------------------------------------------------------------------------------------------------------------------|

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0005%20Comment%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0005%20Comment%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: a (free text) Comment attached to an image identified by a URL_

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0005%20Comment%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0005%20Comment%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: a (free text) Comment attached to a digital image identified by a URI. The nature of the annotation is defined through the type ao:Note._

The RDF of the example in picture 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0005"> 
   <rdf:type rdf:resource="&ao;Comment"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>The intensity of the sky color is a little weak</ao:body> 
</rdf:Description> 
```

### Adding provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0005%20Comment%20on%20image%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0005%20Comment%20on%20image%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: a (free text) Comment attached to a digital image identified by a URI. The nature of the annotation is defined through the type ao:Note._

The RDF of the example in picture 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0005"> 
   <rdf:type rdf:resource="&ao;Comment"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>The intensity of the sky color is a little weak</ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Comment on multiple images](v2Ex0008CommentOnImages.md)
  * [Comment on image fragment](v2Ex0016CommentOnImageFragment.md)