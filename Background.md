AO has been motivated by several [requirements](requirements.md) and [use cases](UseCases.md). It has also been influenced by an analysis of strengths and weaknesses of the [Annotea Project](http://www.w3.org/2001/Annotea/).

### Annotea ###

![http://www.w3.org/2001/Annotea/Papers/www10/annotation.png](http://www.w3.org/2001/Annotea/Papers/www10/annotation.png)<br />
<b>Figure 1 - Annotea Annotation model</b>

Annotea was developed as a Web-based shared annotation system based on a general-purpose open RDF infrastructure where annotations are modeled as a class of metadata. Annotations, identified by a URI, are viewed as statements or remarks made by an author about a Web document. In the Annotea model (see figure 1), the context defines where exactly inside the document the annotation is attached and the body is a link to the content of the annotation identified by a URI and conceived to contain textual or graphical content. Annotations are external to the documents and can be stored in one or more annotation servers that are responsible for controlling access - this allows us to implement local/private and remote/shared annotations.

![http://www.w3.org/2001/Annotea/Papers/KCAP03/bookmark.png](http://www.w3.org/2001/Annotea/Papers/KCAP03/bookmark.png)<br />
<b>Figure 2 - Annotea Bookmark model</b>

In the Annotea project have also been defined Bookmarks. Bookmarks are metadata about Web documents or other resources and share a similar structure with annotations (see figure 2).

The core of AO is inspired by the Annotea model with a some remarkable differences:

  * In AO we do not distinguish between Annotation and Bookmarks. The [Annotation Core](Annotation.md) model is combining the two.
  * In AO the context is defined through instances of document [Selector](Selectors.md) classes. Selectors can refer to text, images, audio files, video files...
  * In AO if the annotation context is not specified, the annotation is about the whole document.
  * In AO it is possible to create annotation types not only by sub-classing but also by composition.
  * In AO there are mechanisms for managing annotation curation
  * In AO there are mechanisms for managing collections of annotation items.
  * In AO there are mechanisms for managing annotation publishing