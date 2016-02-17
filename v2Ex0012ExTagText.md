<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0012: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Tagging a text fragment ##

| _**Tagging** means 'attaching a label'. When using the word 'Tag' we here refer only to free text labels._ |
|:-----------------------------------------------------------------------------------------------------------|

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0012%20Tag%20on%20text%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0012%20Tag%20on%20text%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: annotation of a text fragment with a free text label or tag._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0012%20Tag%20on%20text%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0012%20Tag%20on%20text%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: annotation of a text fragment with a free text label or tag. The nature of the annotation - Tag - is specified through the annotation type ao:Tag. The text fragment is identified through the [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)_

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10402"/>
   <ao:body>Web 2.0</ao:body> 
</rdf:Description> 
```

and the text selector ([PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)):

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
   <ao:onResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0012%20Tag%20on%20text%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0012%20Tag%20on%20text%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: annotation of a text fragment with a free text label or tag - with provenance._

The RDF of the example in figure 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Tag"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/3ecvhzu"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10402"/>
   <ao:body>Web 2.0</ao:body> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

### See also ###

  * [Tag on Document](v2Ex0002TagOnDocument.md)
  * [Tag on Image](v2Ex0001TagOnImage.md)
  * [Tag on image fragment](v2Ex0013ExTagImage.md)