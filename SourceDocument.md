In the following AO documentation we visually refer to the document depicting a simple box usually containing some text or an image.

![http://annotation-ontology.googlecode.com/svn/trunk/images/Reference%20to%20part%20of%20documents%20-%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Reference%20to%20part%20of%20documents%20-%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1: This is how documents parts will be visually depicted in the rest of the documentation.</b>

In general, the target document is identified by a URI. When performing annotation we could refer only to it or, if the resource is not stable or if we want to specify a set of transient properties about the document - might be helpful for detecting changes -, we need to introduce another entity - that we call _SourceDocument_ - as in the following picture:

![http://annotation-ontology.googlecode.com/svn/trunk/images/Source%20Document%202%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Source%20Document%202%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2: A Source Document is basically defining a set of metadata for a Document in a particular moment in time. In this case we have only a date of when the document has been accessed but we can add other metadata such as: title of the page, length of the page and so on.</b>

```
    <rdf:Description rdf:about="http://my.example.org/sd/2332">
    	<rdf:type rdf:resource="&pav;SourceDocument"/>
        <pav:retrievedFrom rdf:resource="http://tinyurl.com/ykjn87p"/>
        <pav:sourceAccessedOn>2010-05-10</pav:sourceAccessedOn>
    </rdf:Description> 

    <rdf:Description rdf:about="http://tinyurl.com/ykjn87p">
        <rdf:type rdf:resource="&foaf;Document"/>
    </rdf:Description> 
```

It is important to notice that tracking the resource access date is a good practice but it is not mandatory. The direct link to the document can still be defined without any other additional triple when the document is stable or when we don't need to store transient metadata about the document.

### Why using only the Document is not good enough ###

When web pages are stable, it is possible to refer to the foaf:Document only. Unfortunately, content on the web is often changing and different content can be found along time for the same URI. Therefore, if two different users create annotation on a particular document in two different moments in time we would end up with something like in the following picture:

![http://annotation-ontology.googlecode.com/svn/trunk/images/Source%20Document%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Source%20Document%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 3: Same document accessed in two different moments in time probably for two different annotation instances.</b>

Translated in triples this would be:

```
   http://tinyurl.com/ykjn87p pav:sourceAccessedOn 2010-04-21
   http://tinyurl.com/ykjn87p pav:sourceAccessedOn 2010-05-26
```

As you can imagine this does not make a lot of sense as it will be impossible to understand what triple is associated with each specific annotation.

---

[Namespaces used above](Namespaces.md)