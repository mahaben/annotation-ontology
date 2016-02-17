<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0013: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Tagging the fragment of an image ##

| _**Tagging** means 'attaching a label'. When using the word 'Tag' we here refer only to free text labels._ |
|:-----------------------------------------------------------------------------------------------------------|

### Example ###


![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0013%20Tag%20on%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0013%20Tag%20on%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: annotation of an image fragment with a free text label or tag_

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0013%20Tag%20on%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0013%20Tag%20on%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: annotation of an image fragment with a free text label or tag. The nature of the annotation - Tag - is specified through the annotation type ao:Tag. The image fragment is identified through the [RectangularImageSelector](v2RectangularImageSelector.md)_

The RDF of the example in picture 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10405"/> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
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

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0013%20Tag%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0013%20Tag%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: annotation of an image fragment with a free text label or tag - with provenance._

The RDF of the example in picture 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10405"/> 
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Tag on Document](v2Ex0002TagOnDocument.md)
  * [Tag on Image](v2Ex0001TagOnImage.md)
  * [Tag on document fragment](v2Ex0012ExTagText.md)