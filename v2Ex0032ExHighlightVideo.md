<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0032: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Note of a video fragment ##

| _A **note** is defined as a brief record of facts, topics, or thoughts, written down as an aid to memory. When using the term 'Note' we here refer only to free text notes._ |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

For annotating temporal media - such as videos and audios - fragments, we suggest to implement the recommendations collected in the [W3C Media Fragment specification](http://www.w3.org/2008/WebVideo/Fragments/WD-media-fragments-spec/) document. This allows the identification of a specific fragment of the target by defining a URI that usually embeds a specific time interval (read more [here](http://www.w3.org/2008/WebVideo/Fragments/WD-media-fragments-spec/)).

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0032%20Note%20on%20video%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0032%20Note%20on%20video%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: annotation of a video fragment. You might notice the label 'video URI fragment'. The URI, in the case of the fragment from second 10 to second 20, would look something like this http://www.example.com/video.ogv#t=10,20 or from second 120 to 121.5 something like  http://www.example.com/video.ogv#t=0:02:00,121.5_


### Representation with AO ###


![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0032%20Note%20on%20video%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0032%20Note%20on%20video%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: annotation of type Note of a video fragment._

The RDF of the example in figure 2 would look like the following:

```
<rdf:Description rdf:about="http://my.example.org/ann/0032"> 
   <rdf:type rdf:resource="&ao;Note"/> 
   <!-- The following can be added for querying with SPARQL 
   <rdf:type rdf:resource="&ao;Annotation"/> 
   <rdf:type rdf:resource="&ann;Annotation"/> 
   --> 
   <ao:annotatesResource rdf:resource="http://www.example.com/video.ogv#t=0:02:00,121.5"/> 
   <ao:body>Ogunquit, Maine</ao:body> 
   <pav:createdOn>2011-08-22</pav:createdOn> 
   <pav:createdBy rdf:resource="http://www.paolociccarese.info#me"/> 
</rdf:Description> 
```