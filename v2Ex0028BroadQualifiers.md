<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0028: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Broad Qualifier with note on image fragment ##

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0028%20Broad%20Qualifier%20on%20image%20fragment%20provenance%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0028%20Broad%20Qualifier%20on%20image%20fragment%20provenance%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: example with a BroadQualifier represented by a term from a controlled vocabulary on an image fragment. The free text Note attempt to give a precise definition of the image section_

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0028%20Broad%20Qualifier%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0028%20Broad%20Qualifier%20on%20image%20fragment%20provenance%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: example with a BroadQualifier with a note on an image fragment. The entity 'Skull Fracture' is a more generic concept representing the portion of the image which is tagged as a 'Linear Skull Fracture' as can be read in the ann:body._

The RDF of the example would look like the following:
```
<rdf:Description rdf:about="http://my.example.org/ann/21332">
   <rdf:type rdf:resource="&ao;BroadQualifier"/>
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Qualifier"/>
   <rdf:type rdf:resource="&ao;Annotation"/>
   <rdf:type rdf:resource="&ann;Annotation"/>
   --> 
   <ao:body>This is the Linear Skull Fracture</ao:body>
   <ao:context rdf:resource="http://my.example.org/sel/10301"/>
   <ao:annotatesResource rdf:resource="http://my.ex.org/img102"/>
   <ao:hasTopic rdf:resource="&ontoexample;46560"/>
   <pav:createdOn>2010-03-21</pav:createdOn>
   <pav:createdBy rdf:resource="http://www.paolociccarese.info/#me"/>
</rdf:Description> 
```

The image selector:

```
<rdf:Description rdf:about="http://my.example.org/sel/10301">
    <rdf:type rdf:resource="&ao;RectangularImageSelector"/>
    <!-- The following can be added for querying with SPARQL 
    <rdf:type rdf:resource="&ao;ImageSelector"/>
    <rdf:type rdf:resource="&ao;Selector"/>
    --> 
    <ao:onResource rdf:resource="http://my.ex.org/img102"/>
    <ao:init>(304,507)</ao:init>
    <ao:end>(380,618)</ao:end>
    <ao:unit>px</ao:unit>
</rdf:Description>
```