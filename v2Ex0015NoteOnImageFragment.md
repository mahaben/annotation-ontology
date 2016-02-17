<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0015: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Note on image fragment ##

| _A **note** is defined as a brief record of facts, topics, or thoughts, written down as an aid to memory. When using the term 'Note' we here refer only to free text notes._ |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0015%20Note%20on%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0015%20Note%20on%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: A free text note attached to a fragment of an image._

### Representation with AO ###

Attaching a note to an image fragment requires to identify a particular region of the image. The fragment selection can be performed with an appropriate Selector. In the following example we are using the [RectangularImageSelector](v2RectangularImageSelector.md) which is simply identifying a rectangular region of the referenced image. More elaborate Selectors can be defined for more specific use cases.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0015%20Note%20on%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0015%20Note%20on%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: A free text note attached to a fragment of an image through a [RectangularImageSelector](v2RectangularImageSelector.md) able to identify a rectangular fragment of the resource. The interpretation of the free text as a note is determined by the annotation type Note._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10405"/>
   <ao:body>My friend's boat</ao:body> 
</rdf:Description> 
```

and the text selector ([RectangularImageSelector](v2RectangularImageSelector.md)):

```
<rdf:Description rdf:about="http://my.example.org/sel/10405"> 
   <rdf:type rdf:resource="&ao;RectangularImageSelector"/> 
   <!-- 
   <rdf:type rdf:resource="&ao;ImageSelector"/> 
   <rdf:type rdf:resource="&ao;Selector"/> 
   --> 
   <ao:init>(10, 42)</ao:init> 
   <ao:end>(30, 68)</ao:end> 
   <ao:unit>%</ao:unit> 
   <ao:onResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0015%20Note%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0015%20Note%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: A free text note attached to a fragment of an image through a [RectangularImageSelector](v2RectangularImageSelector.md) able to identify a rectangular fragment of the resource. The interpretation of the free text as a note is determined by the annotation type Note._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10405"/>
   <ao:body>My friend's boat</ao:body> 
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Note on document](v2Ex0004NoteOnDocument.md)
  * [Note on image](v2Ex0003NoteOnImage.md)
  * [Note on text fragment](v2Ex0014NoteOnTextFragment.md)
  * [Note on multiple images](v2Ex0006NoteOnImages.md)
  * [Note on an image and a webpage](v2Ex0007NoteOnImageAndWebpage.md)