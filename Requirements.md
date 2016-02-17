With Annotation Ontology (AO) we would like to:

  * **Annotate any document on the web (text, images, audio, video) and it’s parts**. Unfortunately, if documents are easily identified by a URI, document parts or fragments are harder to identify. We would like to create a uniform mechanism to refer to all possible kinds of document parts.
  * **Annotate datasets or records in the datasets**
  * **Annotate simultaneously multiple parts of the document**.
  * **Allow performing different kinds of annotation**. Tags are only an example of annotation, others are: notes, semantic tags, errata, examples, hypothesis, citations...
  * **Foster reuse of existing domain ontologies** and not creating new ones. We want to be able to reuse entities such as claim and hypothesis from the SWAN Ontology, citations from CiTO, OBO Foundry ontologies for biomedicine and so on.
  * **Allow multiple annotation perspectives on the same document at the same time**. If you consider a biomedical journal article it is possible to annotate: genes, proteins, biological processes, cell types... but also the rhetorical structure of the document or the scientific discourse embedded in the content. Also multiple curators can have multiple opinions and produce different annotation results.
  * **Persist the annotation separately from the document**. This approach always allow to integrate the annotation back into the document if needed. [RDFa](http://www.w3.org/TR/xhtml-rdfa-primer/) is one possibility for performing the last task.
  * **Allow creation of manual annotation and integration of text mining results**. Annotation can be produced manually - some annotation like the one representing the scientific discourse is usually produced only manually - or automatically through text mining services. The latter method is particularly useful for analyzing big quantity of content or for optimizing curators' job.
  * **Allow curation of annotation** by users, curators or online communities. Allow to produce and persist curation of automatic annotation is particularly useful to provide feedback to the text mining services providers and for optimizing the annotation process when the same text mining services have to be run multiple times.
  * **Allow organizing the annotation** in different forms.
  * **Support publication processes**. Support multiple curations and publishing.