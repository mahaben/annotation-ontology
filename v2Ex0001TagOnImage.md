<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0001: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Tagging an image as a whole ##

| _**Tagging** means 'attaching a label'. When using the word 'Tag' we here refer only to free text labels._ |
|:-----------------------------------------------------------------------------------------------------------|

_Note: the mechanism here illustrated works for any URI no matter what the resource identified by the URI is. This is corresponding to the tagging process of entire resources very popular in communities such as Flickr_ .

### Example ###

In this example an image has been tagged with two (free text) labels or tags.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0001%20Tag%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0001%20Tag%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: a couple of (free text) tags have been attached to an image identified by a URL_

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0001%20Tag%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0001%20Tag%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: two (free text) tags attached to a digital image identified by a URI. The tags are specified through the relationship ao:body and the nature of the annotation is specified through the Annotation Type ao:Tag._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0001a"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>Maine</ao:body> 
</rdf:Description> 

<rdf:Description rdf:about="http://my.example.org/ann/0001b"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>Harbour</ao:body>  
</rdf:Description> 
```

### Adding provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0001%20Tag%20on%20image%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0001%20Tag%20on%20image%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: we can finally provide provenance for the two (free text) tags attached to the same digital image identified by a URL_

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0001a"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>Maine</ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 

<rdf:Description rdf:about="http://my.example.org/ann/0001b"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>Harbour</ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Tag on document](v2Ex0002TagOnDocument.md)
  * [Tag on image fragment](v2Ex0013ExTagImage.md)
  * [Tag on document fragment](v2Ex0012ExTagText.md)