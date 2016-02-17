<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0004: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Note (text and hypertext) targeting a document as a whole ##

| _A **note** is defined as a brief record of facts, topics, or thoughts, written down as an aid to memory. When using the term 'Note' we here refer only to free text notes._ |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: a (free text) note attached to a document identified by a URL_

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: a (free text) note attached to a digital document identified by a URI. The nature of the annotation is defined through the type ao:Note._

The RDF of the example in picture 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0004"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>This article explains the rationale behind the architectural
     design of the Annotation Ontology </ao:body> 
</rdf:Description> 
```

### Adding provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20with%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: a free text note attached to a digital document identified by a URI. The nature of the annotation is defined through the type ao:Note._

The RDF of the example in picture 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0004"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>This article explains the rationale behind the architectural
     design of the Annotation Ontology </ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### Including Hypertext ###

The content of the ao:body property can be either plain text or hypertext.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20hypertext%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0004%20Note%20on%20document%20hypertext%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 4: a hypertext note attached to a digital document identified by a URI._

```
<rdf:Description rdf:about="http://my.example.org/ann/0004"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:body>
      This article explains the rationale behind the architectural design of the  
      &lt;a href="http://code.google.com/p/annotation-ontology/"&gt; Annotation Ontology&lt;/a&gt;
   </ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```


### See also ###

  * [Note on image](v2Ex0003NoteOnImage.md)
  * [Note on image fragment](v2Ex0015NoteOnImageFragment.md)
  * [Note on text fragment](v2Ex0014NoteOnTextFragment.md)
  * [Note on multiple images](v2Ex0006NoteOnImages.md)
  * [Note on an image and a webpage](v2Ex0007NoteOnImageAndWebpage.md)