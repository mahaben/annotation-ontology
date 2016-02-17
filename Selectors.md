A **Selector** identifies a portion of a resource, and may work differently for different types of documents and content types. Also for a specific content type, multiple kind of selector can be defined to cover specific needs. The Selector instance for a specific Annotation instance is identified through the property _ao:context_.

**Every Selector is identified by a URI** and we recommend the use of the same URI for identifying the same document fragment multiple times. As there is not current standard mechanism for defining every possible document fragment through URIs this has to be currently enforced at the application level.

| OWL File | http://annotation-ontology.googlecode.com/svn/trunk/annotation-selectors.owl  |
|:---------|:------------------------------------------------------------------------------|

### Using XPointer ###

The _aos:context_ property is sub-property of the Annotea property _ann:context_. Therefore, for those of you that want to use [XPointer](http://www.w3.org/TR/xptr/)  context definition it is still possible to do it directly - without using the Selectors - the way that Annotea was doing it:

```
  <ann:context>
    http://serv1.example.com/some/page.html#xpointer(id("Main")/p[2])
  </ann:context>
```

the RDF of the annotation will look something like:

```
    <rdf:Description rdf:about="http://my.example.org/ann/29332">
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <rdf:type rdf:resource="&ao;Annotation"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <ann:context>http://serv1.example.com/some/page.html#xpointer(id("Main")/p[2])</ann:context>
        <aof:annotatesDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

Using the pure XPointer approach is not always a good choice - when a document is changing, for instance going through revision, we may end up with orphan annotations or annotations pointing to wrong places. Also, we want to keep track of the [Source Document or Document Provenance](SourceDocument.md) and we need to point to portion of documents that are not XML documents. For these reasons we introduced the Selector mechanism.


### Classes Of Selectors ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Reference%20to%20part%20of%20documents%20-%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Reference%20to%20part%20of%20documents%20-%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1: This is how documents parts will be visually depicted in the rest of the documentation.</b>

**Selector** is a generic class that can be customized/sub-classed for the different kind of content types:
  * **XPointer Selector**: identifies any part of an XML document by using the [XPointer](http://www.w3.org/TR/xptr/)  technology. Even if XPointer can be used directly with the property ann:context, it is also possible to use an instance of a selector. This approach is more laborious but allows to integrate Document Provenance - [read more about this selector](XPointerSelector.md)

  * **Text Selector**: identifies a chunk of a text. Some sub-types:
    * **Offset Range Selector**: identifies a chunk of text specifying the offset from the beginning of the document and the range - number of characters from the offset - [read more about this selector](OffsetRangeSelector.md)
    * **Prefix Postfix Selector**: identifies a chunk of text specifying a reasonable amount of characters before it (prefix) and a reasonable amount of characters after it  (postfix) - [read more about this selector](PrefixPostfixSelector.md)

  * **Image Selector**: identifies a portion of an image.
    * **Init End Corner Selector**: identifies a rectangular region of an image through the definition of the top left and bottom right corners - [read more about this selector](InitEndCornerSelector.md)
    * **...**

  * **Audio Selector**: identifies a section of an audio file.
    * **...**

  * **Video Selector**: identifies a section of an video file.
    * **...**

### Examples ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20PrefixPostfix%20Selector%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Text%20PrefixPostfix%20Selector%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2 - Example of text selector where a chunk of text is identified through a prefix and a postfix.</b>

The text selector:

```
    <rdf:Description rdf:about="http://my.example.org/sel/10300">
        <rdf:type rdf:resource="&ao;Selector"/>
        <rdf:type rdf:resource="&aos;TextSelector"/>
        <rdf:type rdf:resource="&aos;PrefixPostfixSelector"/>
        <aos:exact>BACE1</aos:exact>
        <aos:prefix>Cognitive and behavioral deficits related to</aos:prefix>
        <aos:postfix>inhibition may be magnified in humans who</aos:postfix>
        <aof:onDocument rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:onSourceDocument rdf:resource="http://my.example.org/sd/2332"/>
    </rdf:Description>
```

The source document:

```
    <rdf:Description rdf:about="http://my.example.org/sd/2332">
        <rdf:type rdf:resource="&pav;SourceDocument"/>
        <pav:retrievedFrom rdf:resource="http://tinyurl.com/ykjn87p"/>
        <pav:sourceAccessedOn>2010-05-10</pav:sourceAccessedOn>
    </rdf:Description> 
```

![http://annotation-ontology.googlecode.com/svn/trunk/images/Image%20InitEndCorner%20Selector%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Image%20InitEndCorner%20Selector%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 3 - Example of image selector where a rectangular area within the document image is specified.</b>

The image selector:

```
    <rdf:Description rdf:about="http://my.example.org/sel/22300">
        <rdf:type rdf:resource="&ao;Selector"/>
        <rdf:type rdf:resource="&aos;ImageSelector"/>
        <rdf:type rdf:resource="&aos;InitEndCornerSelector"/>
        <aof:onDocument rdf:resource="http://tinyurl.com/35a6fnq"/>
        <ao:onSourceDocument rdf:resource="http://my.example.org/sd/2339"/>
        <aos:init>(280,30)</aos:init>
        <aos:end>(380,120)</aos:end>
    </rdf:Description>
```

The source document:

```
    <rdf:Description rdf:about="http://my.example.org/sd/2339">
    	<rdf:type rdf:resource="&pav;SourceDocument"/>
        <pav:retrievedFrom rdf:resource="http://tinyurl.com/35a6fnq"/>
        <pav:sourceAccessedOn>2010-05-10</pav:sourceAccessedOn>
    </rdf:Description> 
```

### Define New Selectors ###

We are not assuming we are able to provide every possible way to select any part of a any kind of document. Therefore, if the selector you have in mind is not yet existing, it is sufficient to define a new one sub-classing one of the existing **Selector** classes.

---

[Namespaces used above](Namespaces.md)