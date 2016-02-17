<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0016: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Comment on image fragment ##

| _A **Comment** is a remark expressing an opinion or reaction. When using the term 'Comment' we here refer only to free text comments._ |
|:---------------------------------------------------------------------------------------------------------------------------------------|

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0016%20Comment%20on%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0016%20Comment%20on%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: example of comment attached to an image fragment_

### Representation with AO ###

Attaching a comment to an image fragment requires to identify a particular region of the image. The fragment selection can be performed with an appropriate Selector. In the following example we are using the [RectangularImageSelector](v2RectangularImageSelector.md) which is simply identifying a rectangular region of the referenced image. More elaborate Selectors can be defined for more specific use cases.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0016%20Comment%20on%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0016%20Comment%20on%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: A free text Comment attached to a fragment of an image through a [RectangularImageSelector](v2RectangularImageSelector.md) able to identify a rectangular fragment of the resource. The interpretation of the free text as a comment is determined by the annotation type Comment._

The RDF of the example in picture 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Comment"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10405"/>
   <ao:body>It would be nice if the reflections of all the boats were all sharp as this one </ao:body> 
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
   <ao:end>(30, 70)</ao:end> 
   <ao:unit>%</ao:unit> 
   <ao:onResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
</rdf:Description> 
```


### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0016%20Comment%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0016%20Comment%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: the same example with provenance_


The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Comment"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10405"/>
   <ao:body>It would be nice if the reflections of all the boats were all sharp as this one </ao:body> 
   <pav:createdOn>2010-03-21</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```


### See also ###

  * [Comment on image](v2Ex0005CommentOnImage.md)
  * [Comment on multiple images](v2Ex0008CommentOnImages.md)