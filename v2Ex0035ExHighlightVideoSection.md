<table width='100%'>
<tr>
<td>
<a href='v2Main.md'>&lt;&lt; Back to Main</a>
</td>
<td align='right'>
ex0035: <img src='http://annotation-ontology.googlecode.com/svn/trunk/images/misc/in_progress.gif' /> in progress<br>
</td>
</tr>
</table>

## Highlight of a portion of a video fragment ##

For annotating temporal media - such as videos and audios - fragments, we suggest to implement the recommendations collected in the [W3C Media Fragment specification](http://www.w3.org/2008/WebVideo/Fragments/WD-media-fragments-spec/) document. This allows the identification of a specific fragment of the target by defining a URI that usually embeds a specific time interval (read more [here](http://www.w3.org/2008/WebVideo/Fragments/WD-media-fragments-spec/)).

For detecting sections the video fragment we suggest to use the [basic shapes](http://www.w3.org/TR/SVG/shapes.html) of [Scalable Vector Graphics (SVG)](http://www.w3.org/Graphics/SVG/). This is possible through the [SVG Selector](v2SvgSelector.md).

### Example ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0035%20Note%20on%20Shaped%20highlight%20video%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0035%20Note%20on%20Shaped%20highlight%20video%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: this use case consists in highlighting, with a red rectangle, a section of a video fragment. For this example we assume the rectangle is in the same location for the entire video fragment. You might notice the label 'video URI fragment'. The URI, in the case of the fragment from second 10 to second 20, would look something like this http://www.example.com/video.ogv#t=10,20 or from second 120 to 121.5 something like  http://www.example.com/video.ogv#t=0:02:00,121.5 ._

### Representation in AO ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0035%20Note%20on%20Shaped%20highlight%20video%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0035%20Note%20on%20Shaped%20highlight%20video%20fragment%20-%20Annotation%20Ontology%20AO%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: It depicts annotation of a section of a video fragment. The section is identified through a SVG rectangular shape defined through a SVG Selector._