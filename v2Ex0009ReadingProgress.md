<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0009: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Recording the reading progress location ##

When reading a document we might want to be able to record the last position of our 'reading cursor' so we can resume the reading from the right location. This is pretty simple to obtain with AO and it consists in creating a very simple Annotation with a proper [Selector](v2Selectors.md)

### The example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: defining the 'reading cursor'_

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20prefixpostfix%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20prefixpostfix%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: a visual representation of the AO way of defining the 'reading cursor' through a [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)_

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0009"> 
   <rdf:type rdf:resource="&ao;Cursor"/> 
   <!-- 
   The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/>     
   <ao:context rdf:resource="http://my.example.org/sel/10400"/> 
</rdf:Description> 
```

and the text selector ([PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)):

```
<rdf:Description rdf:about="http://my.example.org/sel/0009a"> 
   <rdf:type rdf:resource="&ao;PrefixSuffixTextSelector"/>
   <!--
   <rdf:type rdf:resource="&ao;TextSelector"/> 
   <rdf:type rdf:resource="&ao;Selector"/> 
   -->   
   <ao:exact></ao:exact> 
   <ao:prefix>have become increasingly popular with the advent of Web 2.0 [26].</ao:prefix> 
   <ao:suffix>The process of tagging allows association of free text to web resources, 
   thus improving</ao:suffix>     
   <ao:onResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
</rdf:Description> 
```

The same annotation could be expressed using any another type of text selector, for instance the [OffsetRangeTextSelector](v2OffsetRangeTextSelector.md):

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20offsetrange%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20offsetrange%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: AO representation of the 'reading cursor' through a [OffsetRangeTextSelector](v2OffsetRangeTextSelector.md)_

And the alternative text selector ([OffsetRangeTextSelector](v2OffsetRangeTextSelector.md)):

```
<rdf:Description rdf:about="http://my.example.org/sel/0009b"> 
   <rdf:type rdf:resource="&ao;OffsetRangeTextSelector"/>
   <!--
   <rdf:type rdf:resource="&ao;TextSelector"/> 
   <rdf:type rdf:resource="&ao;Selector"/> 
   -->   
   <ao:offset>420</ao:offset> 
   <ao:range>0</ao:range>     
   <ao:onResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
</rdf:Description> 
```

### Adding provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20prefixpostfix%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20prefixpostfix%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 4: Keeping track of the 'reading cursor' through a [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md) - with provenance_

```
<rdf:Description rdf:about="http://my.example.org/ann/0009"> 
   <rdf:type rdf:resource="&ao;Cursor"/> 
   <!-- 
   The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/>     
   <ao:context rdf:resource="http://my.example.org/sel/10400"/> 
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```