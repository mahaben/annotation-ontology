<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0029: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Qualifier on ontological terms or Ontology Mapping ##

### The Example ###

While creating notes with free text is common practice, creating annotation pointing to URIs can be more powerful and easier to understand by machines. In Annotation Ontology (AO) we can create annotation pointing to URIs through the relationship _ao:hasTopic_.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0029%20Qualifier%20on%20term%20or%20ontology%20mapping%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0029%20Qualifier%20on%20term%20or%20ontology%20mapping%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: in this example the Wikipedia link to the town of Ogunquit, Maine is attached to an image as annotation._

### Representation with AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0029%20Qualifier%20on%20term%20or%20ontology%20mapping%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0029%20Qualifier%20on%20term%20or%20ontology%20mapping%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: this is how a linked annotation is represented in AO._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;ExactQualifier"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Qualifier"/>
   <rdf:type rdf:resource="&ao;Annotation"/>
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://ontology.neuinfo.org/NIF/BiomaterialEntities/
       NIF-Molecule.owl#nlx_mol_20090203"/> 
   <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PR_000004615"/>
</rdf:Description> 
```

### Adding provenance: human annotation ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0029%20Qualifier%20on%20term%20or%20ontology%20mapping%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0029%20Qualifier%20on%20term%20or%20ontology%20mapping%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: the same example displaying also provenance data._

The RDF of the example in figure 3 - which include provenance data - would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/21315"> 
   <rdf:type rdf:resource="&ao;ExactQualifier"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Qualifier"/>
   <rdf:type rdf:resource="&ao;Annotation"/>
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://ontology.neuinfo.org/NIF/BiomaterialEntities/
       NIF-Molecule.owl#nlx_mol_20090203"/> 
   <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PR_000004615"/>
   <pav:createdOn>2011-08-30</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```