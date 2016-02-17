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

### What is a Selector ###
A **Selector** identifies a portion of a resource and may work differently for different types of documents and content types. Also, for a specific content type, multiple kind of selector can be defined to cover specific needs. The _Selector_ instance for a specific _Annotation_ instance is specified through the property _ao:context_.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/Selector%20Overview%20-%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/Selector%20Overview%20-%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1 - An_Annotation_can refer to a fragment of any resource through an appropriate_Selector_. The link between the_Annotation_and the_Selector_is performed through the relationship_ao:context_. As resources can be of different kind - textual documents, hypertexts, images, databases... - several_Selectors_are made available._

**Every Selector is identified by a URI which should be dereferenceable**. We recommend the use of the same URI for identifying the same document fragment multiple times. As there is not current standard mechanism for defining every possible document fragment through URIs this has to be currently enforced at the application level. That is what we do, for instance, in the application [Domeo Web Annotation Toolkit](http://annotationframework.org).

_**Note**: the annotation in figure 1 is connected to the annotated resource twice, once through the ao:context+ao:Selector+ao:onResource and once through ao:annotatesResource. This is not random. We are assuming not all the applications will be able to interpret selectors. In that case such applications can still detect the resource as a whole._

### Classes Of Selectors ###
**Specific _Selectors_ can be defined simply subclassing the _Selector_ class**. Specific selectors can be defined simply subclassing the Selector class. With AO core, we provide a set of _Selectors_ we currently use in our applications. These cover mainly text and image resources. We are collaborating with other groups to define additional _Selectors_ for addressing more use cases. These will be listed on this wiki when they will be verified and implemented in real applications.

Selectors currently **in use** in existing applications:

:: _Text Selectors_:
  * _[Start End Selector](v2StartEndTextSelector.md)_: identifies a fragment of text specifying the location of its first and last characters.
  * _[Prefix and Suffix Selector](v2PrefixSuffixTextSelector.md)_: identifies a chunk of text specifying a reasonable amount of characters before it (prefix) and a reasonable amount of characters after it (suffix). _This selector assumes the content of the prefix, exact match and suffix to be plain text where the HTML has been removed._
  * _[Offset and Range Selector](v2OffsetRangeTextSelector.md)_: identifies a chunk of text specifying the offset from the beginning of the document and the range - number of characters from the offset.
:: _Image and Temporal Media Selectors_
  * _[Rectangular Image Selector](RectangularImageSelector.md)_: identifies a rectangular region of an image through the definition of the top left and bottom right corners.
  * _[SVG Image/Video Selector](v2SvgSelector.md)_: identifies a section of an image or video fragment through [SVG Basic Shapes](http://www.w3.org/TR/SVG/shapes.html).

### Create new Selectors ###
**New Selectors can be created according to specific needs**. However, before doing this, we suggest to check the list of the already available _Selectors_. There might be already a _Selector_ that can cover your use case as it is, or after a small modification that you can discuss with the current _Selector_ contact person. If what you need is not covered, you can proceed in creating your new _Selector_. It would be great if you could contribute the new _Selector_ back to the community so that we can avoid redundancies and foster integration between applications. **You will get credited for it**.