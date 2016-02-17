[SIOC (Semantically-Interlinked Online Communities)](http://sioc-project.org/) is an initiative that aims to enable the integration of online community information. AO integrates with SIOC as follows.

The SIOC _classes_ of interest are coming from two different namespaces:

| SIOC core | sioc | [Specs](http://rdfs.org/sioc/spec/) | Namespace http://rdfs.org/sioc/ns# |
|:----------|:-----|:------------------------------------|:-----------------------------------|
| SIOC types | sioct |                                     | Namespace http://rdfs.org/sioc/types# |

and are:

| [sioc:Item](http://rdfs.org/sioc/ns#Item) | An Item is something which can be in a Container |
|:------------------------------------------|:-------------------------------------------------|
| [sioc:Container](http://rdfs.org/sioc/ns#Container) | An area in which content Items are contained     |
| [sioct:AnnotationSet](http://rdfs.org/sioc/types#AnnotationSet) | Describes a set of annotations, for example, those created by a particular user or related to a particular topic |

![http://annotation-ontology.googlecode.com/svn/trunk/images/AO%20and%20SIOC%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/AO%20and%20SIOC%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 1: AO (Annotation Ontology) classes integration with SIOC</b>