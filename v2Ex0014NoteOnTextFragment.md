<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0014: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Note on text fragment ##

| _A **note** is defined as a brief record of facts, topics, or thoughts, written down as an aid to memory. When using the term 'Note' we here refer only to free text notes._ |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0014%20Note%20on%20text%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0014%20Note%20on%20text%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: note attached to a text fragment_

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0014%20Note%20on%20text%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0014%20Note%20on%20text%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: note attached to a text fragment identified through a [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md). The annotation type ao:Note defines the nature of the annotation._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21304"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10402"/>
   <ao:body>Tagging is only performed through free text.</ao:body> 
</rdf:Description> 
```

And the text selector (PrefixSuffixTextSelector):

```
<rdf:Description rdf:about="http://my.example.org/sel/10402"> 
   <rdf:type rdf:resource="&ao;PrefixSuffixTextSelector"/> 
   <!-- 
   <rdf:type rdf:resource="&ao;TextSelector"/> 
   <rdf:type rdf:resource="&ao;Selector"/> 
   --> 
   <ao:exact>The process of tagging allows association of free text to web resources,</ao:exact> 
   <ao:prefix>have become increasingly popular with the advent of Web 2.0 [26].</ao:prefix> 
   <ao:suffix>thus improving their classification and organization</ao:suffix> 
   <ao:onResource rdf:resource="http://my.example.org/sel/10405"/> 
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0014%20Note%20on%20text%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0014%20Note%20on%20text%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: note attached to a text fragment identified through a [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md). The annotation type ao:Note defines the nature of the annotation._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21304"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10402"/>
   <ao:body>Tagging is only performed through free text.</ao:body> 
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Note on document](v2Ex0004NoteOnDocument.md)
  * [Note on image](v2Ex0003NoteOnImage.md)
  * [Note on image fragment](v2Ex0015NoteOnImageFragment.md)
  * [Note on multiple images](v2Ex0006NoteOnImages.md)
  * [Note on an image and a webpage](v2Ex0007NoteOnImageAndWebpage.md)