<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0007: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Note on image and webpage ##

| _A **note** is defined as a brief record of facts, topics, or thoughts, written down as an aid to memory. When using the term 'Note' we here refer only to free text notes._ |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

Annotation Ontology (AO) allows to annotate multiple resources at the same time by defining multiple relationships ao:annotatesResources.

### Example ###

This example show how to target resources of different kind. It is obviously possible to target any resource that is identified by a URI simply adding additional relationships ao:annotatesResources.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0007%20Note%20on%20image%20and%20webpage%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0007%20Note%20on%20image%20and%20webpage%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: an example (free text) Note targeting an image and a webpage._

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0007%20Note%20on%20image%20and%20webpage%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0007%20Note%20on%20image%20and%20webpage%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: a (free text) Note targeting an image and a webpage._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21314"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:annotatesResource rdf:resource="http://www.ogunquitmaine.com/Perkins-Cove.html"/>
   <ao:body>Multiple resources about Perkin's Cove in Ogunquit, Maine</ao:body>  
</rdf:Description> 
```

### Adding provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0007%20Note%20on%20image%20and%20webpage%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0007%20Note%20on%20image%20and%20webpage%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: a (free text) Note targeting an image and a webpage._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21314"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:annotatesResource rdf:resource="http://www.ogunquitmaine.com/Perkins-Cove.html"/>
   <ao:body>Multiple resources about Perkin's Cove in Ogunquit, Maine</ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Note on document](v2Ex0004NoteOnDocument.md)
  * [Note on image](v2Ex0003NoteOnImage.md)
  * [Note on image fragment](v2Ex0015NoteOnImageFragment.md)
  * [Note on text fragment](v2Ex0014NoteOnTextFragment.md)
  * [Note on multiple images](v2Ex0006NoteOnImages.md)