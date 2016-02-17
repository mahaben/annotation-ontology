<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0010: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Highlight of text fragments ##

Highlighting a text fragment is another common operation that can be addressed by AO as follows:

### The Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: highlight of a text fragment_

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20prefixsuffix%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20prefixsuffix%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: example of text fragment highlight identified through the [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)_

The RDF of the example in picture 1 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21300"> 
   <rdf:type rdf:resource="&ao;Highlight"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:context rdf:resource="http://my.example.org/sel/10402"/> 
   <pav:createdOn>2011-08-17</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

and the text selector ([OffsetRangeTextSelector](v2PrefixSuffixTextSelector.md)):

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

The same annotation could be expressed using any another type of text selector, for instance the [OffsetRangeTextSelector](v2OffsetRangeTextSelector.md):

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20offsetrange%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20offsetrange%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: example of text fragment highlight identified through the [OffsetRangeTextSelector](v2OffsetRangeTextSelector.md)_

And the text selector ([OffsetRangeTextSelector](v2OffsetRangeTextSelector.md)):

```
<rdf:Description rdf:about="http://my.example.org/sel/10403"> 
   <rdf:type rdf:resource="&ao;OffsetRangeTextSelector"/> 
   <!-- 
   <rdf:type rdf:resource="&ao;TextSelector"/> 
   <rdf:type rdf:resource="&ao;Selector"/> 
   --> 
   <ao:offset>420</ao:offset> 
   <ao:range>81</ao:range> 
   <ao:exact>The process of tagging allows association of free text to web resources,</ao:exact> 
   <ao:onResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20prefixsuffix%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0010%20Highlight%20on%20text%20prefixsuffix%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 4: example of text fragment highlight identified through the [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)_