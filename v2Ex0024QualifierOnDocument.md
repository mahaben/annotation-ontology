<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0024: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Semantic tag or qualifier on document fragment ##

While creating notes with free text is common practice, creating annotation pointing to terms or entities coming from controlled vocabularies, ontologies and knowledge bases can be more powerful and easier to understand by machines. In Annotation Ontology (AO) we can create annotation pointing to a 'semantic' entity - identified by a URI - through the relationship _ao:hasTopic_ and through appropriate Annotation Types.

### Example ###

With AO we can attach topics expressed through URIs, for instance, to documents as in the following example where a term from the [PRotein Ontology (PRO)](http://pir.georgetown.edu/pro/) is linked to a document.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: a semantic tag or Qualifier. A term from PRO 'beta-secretase 1' identified by a URI 'PRO:000004615' is attached, as annotation, to a document fragment._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: representation of a Qualifier on a document fragment in AO_


The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Qualifier"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:context rdf:resource="http://my.example.org/sel/10402"/> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
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
   <ao:exact>BACE1</ao:exact> 
   <ao:prefix>Cognitive and behavioral deficits related to</ao:prefix> 
   <ao:suffix>inhibition may be magnified in humans who,</ao:suffix> 
   <ao:onResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
</rdf:Description> 
```

### Adding Provenance ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: representation of a Qualifier in AO including provenance data_


The RDF of the example in figure 3 - which includes provenance data - would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;Qualifier"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:context rdf:resource="http://my.example.org/sel/10402"/> 
   <ao:annotatesResource rdf:resource="http://tinyurl.com/ykjn87p"/> 
   <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```

## See also ##

  * [Qualifier on document](v2Ex0022QualifierOnDocument.md)
  * [Qualifier on image](v2Ex0023QualifierOnImage.md)