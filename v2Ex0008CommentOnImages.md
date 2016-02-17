<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0008: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Comment on multiple images ##

| _A **Comment** is a remark expressing an opinion or reaction. When using the term 'Comment' we here refer only to free text comments._ |
|:---------------------------------------------------------------------------------------------------------------------------------------|

Annotation Ontology (AO) allows to annotate multiple resources at the same time through defining multiple relationships ao:annotatesResources.

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0008%20Comment%20on%20images%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0008%20Comment%20on%20images%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: an example (free text) Comment targeting two images._

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0008%20Comment%20on%20images%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0008%20Comment%20on%20images%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: a (free text) Comment targeting two images._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21314"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3uu5z25"/>
   <ao:body>I don't believe these pictures have been taken the very same day</ao:body> 
</rdf:Description> 
```

### Adding provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0008%20Comment%20on%20images%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0008%20Comment%20on%20images%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: a (free text) Comment targeting two images._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21314"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3uu5z25"/>
   <ao:body>I don't believe these pictures have been taken the very same day</ao:body> 
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Comment on image](v2Ex0005CommentOnImage.md)
  * [Comment on image fragment](v2Ex0016CommentOnImageFragment.md)