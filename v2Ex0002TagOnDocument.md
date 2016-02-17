<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0002: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Tagging a document as a whole ##

| _**Tagging** means 'attaching a label'. When using the word 'Tag' we here refer only to free text labels._ |
|:-----------------------------------------------------------------------------------------------------------|

_Note: the mechanism here illustrated works for any URI no matter what the resource identified by the URI is. This is corresponding to the tagging process of entire resources very popular in communities such as Flickr_ .

### Example ###

In this example a document has been tagged with a (free text) label (or tag).

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0002%20Tag%20on%20document%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0002%20Tag%20on%20document%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: a (free text) tag attached to a document identified by a URL_

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0002%20Tag%20on%20document%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0002%20Tag%20on%20document%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: a (free text) tag attached to a digital document identified by a URL. The nature of the annotation is specified through the Annotation Type ao:Tag._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0002"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>Web 3.0</ao:body> 
</rdf:Description> 
```

### Adding provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0002%20Tag%20on%20document%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0002%20Tag%20on%20document%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: a (free text) tag attached to a digital document identified by a URI. The nature of the annotation is specified through the Annotation Type ao:Tag._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0002"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>Web 3.0</ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Tag on Image](v2Ex0001TagOnImage.md)
  * [Tag on image fragment](v2Ex0013ExTagImage.md)
  * [Tag on document fragment](v2Ex0012ExTagText.md)