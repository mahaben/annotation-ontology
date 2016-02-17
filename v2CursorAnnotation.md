<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
<img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

# Cursor Annotation #

| ao:Cursor | Annotation type for recording a location in a resource. Normally used for textual documents, it can be extended to other media as well. |
|:----------|:----------------------------------------------------------------------------------------------------------------------------------------|

The _Annotation_ of type _ao:Cursor_ can be used to record the last position of the 'reading process' in a textual document. The location is identified through a proper [Selector](v2Selectors.md).

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20prefixpostfix%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0009%20Progress%20on%20text%20prefixpostfix%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: Keeping track of the 'reading cursor' through a [PrefixSuffixTextSelector](v2PrefixSuffixTextSelector.md)_

The RDF of the example in figure 1 would look like the following:

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