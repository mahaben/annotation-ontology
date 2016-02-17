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

### Structured annotation on single target resources ###

While creating notes with free text is common practice, creating annotation pointing to URIs can be more powerful and easier to understand by machines. In Annotation Ontology (AO) we can create annotation pointing to URIs through the relationship _ao:hasTopic_.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0021%20URI%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 1: in this example the Wikipedia link to the town of Ogunquit, Maine is attached to an image as annotation._

**[Annotating a resource with a URL](v2Ex0021LinkOnImage.md)**

With AO we can attach topics expressed through URIs, for instance, to documents as in the following example where a term from the [PRotein Ontology (PRO)](http://pir.georgetown.edu/pro/) is linked to a document.

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0022%20Qualifier%20on%20document%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0022%20Qualifier%20on%20document%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 2: a semantic tag or Qualifier. A term from PRO 'beta-secretase 1' identified by a URI 'PRO:000004615' is attached, as annotation, to an entire document._

**[How to represent a linked Note with AO](v2Ex0022QualifierOnDocument.md)**

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0023%20Qualifier%20on%20image%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 3: a semantic tag or Qualifier. A term from PRO ['amyloid beta a4 protein' identified by a URI 'PRO:000004168'](http://pir.georgetown.edu/cgi-bin/pro/entry_pro?id=PR:000004168) is attached, as annotation, to an entire document._

**[How to represent a Qualifier (or semantic tag) on an image with AO](v2Ex0023QualifierOnImage.md)**

![http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/v2/v2Ex0024%20Qualifier%20on%20document%20fragment%20-%20Example%20-%20by%20Paolo%20Ciccarese.png)<br />
_Figure 4: a semantic tag or Qualifier. A term from PRO 'beta-secretase 1' identified by a URI 'PRO:000004615' is attached, as annotation, to a document fragment._

**[How to represent a Semantic tag or Qualifier on document fragment with AO](v2Ex0024QualifierOnDocument.md)**