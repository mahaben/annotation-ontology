<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0011: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Highlight of image fragment ##

AO allows to highlight image fragments in a similar way that allows highlighting text fragments. The difference consists in having an appropriate selector for images.

### The Example ###

Highlighting an image fragment is equivalent to identify a particular region in an image.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0011%20Highlight%20of%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0011%20Highlight%20of%20image%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: highlight of an image fragment_

### Representation with AO ###

The fragment selection can be performed with an appropriate _Selector_. In the following example we are using the [RectangularImageSelector](v2RectangularImageSelector.md) which is simply identifying a rectangular region of the referenced image. More elaborate _Selectors_ can be defined for more specific use cases.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0011%20Highlight%20of%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0011%20Highlight%20of%20image%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: highlight of Amyloid beta peptides identified, in a larger image, through a [RectangularImageSelector](v2RectangularImageSelector.md)_

The RDF of the example in picture 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0011"> 
   <rdf:type rdf:resource="&ao;Highlight"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3zgsyo3"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10404"/> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

and the text selector ([RectangularImageSelector](v2RectangularImageSelector.md)):

```
<rdf:Description rdf:about="http://my.example.org/sel/0011"> 
   <rdf:type rdf:resource="&ao;RectangularImageSelector"/> 
   <!-- 
   <rdf:type rdf:resource="&ao;ImageSelector"/> 
   <rdf:type rdf:resource="&ao;Selector"/> 
   --> 
   <ao:init>(10, 200)</ao:init> 
   <ao:end>(60, 250)</ao:end> 
   <ao:unit>px</ao:unit> 
   <ao:onResource rdf:resource="http://tinyurl.com/3zgsyo3"/> 
</rdf:Description> 
```

### Adding Procenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0011%20Highlight%20of%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0011%20Highlight%20of%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: highlight of Amyloid beta peptides identified, in a larger image, through a [RectangularImageSelector](v2RectangularImageSelector.md) - with provenance_