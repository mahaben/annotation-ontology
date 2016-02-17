<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0023: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Semantic tag or qualifier on image ##

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: a semantic tag or Qualifier. A term from PRO ['amyloid beta a4 protein' identified by a URI 'PRO:000004168'](http://pir.georgetown.edu/cgi-bin/pro/entry_pro?id=PR:000004168) is attached, as annotation, to an entire document._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: representation of a Qualifier in AO_

The RDF of the example in picture 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Qualifier"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://www.neuronlab.org/images/1228067928.jpg"/> 
   <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004168"/>
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: representation of a Qualifier and provenance in AO_

The RDF of the example in picture 3 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Qualifier"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://www.neuronlab.org/images/1228067928.jpg"/> 
   <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004168"/>
   <pav:createdOn>2010-03-21</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

## See also ##

  * [Qualifier on document](v2Ex0022QualifierOnDocument.md)
  * [Qualifier on document fragment](v2Ex0024QualifierOnDocument.md)