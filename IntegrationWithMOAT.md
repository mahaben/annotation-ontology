[MOAT](http://moat-project.org/) defines a lightweight ontology  to represent how different meanings (i.e. URIs of Semantic Web resources) can be related to a tag. Its goal is slightly different than AO where, in the case of Qualifiers, we want to associate a precise meaning to a resource or a portion of it. In AO it is possible to reuse MOAT content and...

(coming soon)

### Restricted Tagging ###

![http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png](http://annotation-ontology.googlecode.com/svn/trunk/images/Document%20Annotation%20-%20AO%20Annotation%20Ontology%20-%20by%20Paolo%20Ciccarese.png)<br />
<b>Figure 2 - Example of annotation on the whole document with AO.</b>

The example inf figure 1:

```
    <rdf:Description rdf:about="http://my.example.org/ann/21332">
        <rdf:type rdf:resource="&aot;Qualifier"/>
        <rdf:type rdf:resource="&ann;Annotation"/>
        <ann:annotates rdf:resource="http://tinyurl.com/ykjn87p"/>
        <ao:hasTopic rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
        <pav:createdOn>2010-03-21</pav:createdOn>
        <pav:createdBy rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
    </rdf:Description> 
```

can be transposed in MOAT and the [tag ontology](http://www.holygoat.co.uk/projects/tags/) as:

```
    <tag:RestrictedTagging>
       <tag:taggedResource rdf:resource="http://my.example.org/ann/21332"/>
       <foaf:maker rdf:resource="http://www.hcklab.org/foaf.rdf#me"/>
       <tag:tagName>BACE1</tag:tagName>
       <moat:tagMeaning rdf:resource="http://purl.obolibrary.org/obo/PRO_000004615"/>
    </tag:RestrictedTagging>
```

### Namespaces ###

Namespaces used above:

| foaf | Friend Of A Friend | http://xmlns.com/foaf/0.1/ |
|:-----|:-------------------|:---------------------------|
| ann  | Annotea            | http://www.w3.org/2000/10/annotation-ns# |
| ao   | **Annotation Core** |  http://purl.org/ao/core/  |
| aot  | **Annotation Selectors** | http://purl.org/ao/types/  |
| pav  | Provenance, Authoring and Versioning | http://purl.org/pav/provenance/ |
| tag  | Tag Ontology       | http://www.holygoat.co.uk/owl/redwood/0.1/tags/ |
| moat | MOAT Ontology      | http://moat-project.org/ns# |