[<< Back to Main](v2Main.md)

# Principles #

## Traceability ##
Annotation Ontology has been designed to assure completeness of the information about every step in the annotation process chain. A rich set of provenance data based on the PAV ontology (1) can be defined for each piece of the annotation model.

## Orthogonality and Scalability ##
The scalability of the Semantic Web hinges upon factoring information components into orthogonal ontologies. In addition to limiting the combinatorial explosion implicit in multifunction ontologies, it allows people to share code and understanding of core ontologies. Annotation Ontology has been designed to be orthogonal with any domain ontology. This approach guarantees both to keep the Annotation Ontology simple and to allow Annotation Ontology adopters to use any domain ontology they desire.

## Generality ##
As direct consequence of the previously listed principle of Orthogonality, Annotation Ontology is a generic framework for content improvement. Biomedicine and Astronomy are only two possible areas of application. Also AO is not only about documents but it is also about images, audio files, databases, and data in general.

## Interoperability ##
Annotation Ontology has been designed to be easy to integrate with other tools proper of the Semantic Web. For this reason the model has been defined in OWL (2) and is serialized in RDF (3) format. Also, we want AO to be integrated and interoperable with valuable already available ontologies.

## Modularity ##
Annotation Ontology has been designed as a collection of modules. This will allow users to use the pieces of AO they need to without necessarily become familiar with the entire framework and the set of related ontologies.

## Extensibility ##
We know Annotation Ontology can be used in several different ways. Therefore, in its design we are making sure to allow users to build on the top of the basic ontological framework to cover additional requirements.

## Adequate Documentation ##
When proposing Annotation Ontology, we want to make sure users will find an adequate number of documents and examples about its usage. Adequate documentation is much more than good definitions.

1. [PAV - Provenance, Authoring and Versioning Ontology v.2](http://code.google.com/p/pav-ontology/)<br />
2. [OWL - Ontology Web Language v. 2](http://www.w3.org/TR/owl2-overview/)<br />
3. [RDF - Resource Description Framework](http://www.w3.org/RDF/)<br />