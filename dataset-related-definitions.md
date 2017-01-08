# Definitions of "dataset" and other classes that may or may not be disjoint

**dctype:Dataset**
from 	http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=dcmitype#Dataset

Definition: Data encoded in a defined structure.

Comment: Examples include lists, tables, and databases. A dataset may be useful for direct machine processing.

**dcat:Dataset**
from https://www.w3.org/TR/vocab-dcat/#class-dataset

Definition: A collection of data, published or curated by a single agent, and available for access or download in one or more formats.

Sub class of: dctype:Dataset

**owl:Ontology**
RDF says:
```
owl:Ontology a rdfs:Class;
rdfs:comment "The class of ontologies."
```
[very circular definition]

From https://www.w3.org/TR/2012/REC-owl2-primer-20121211/#What_is_OWL_2.3F

"An ontology is a set of precise descriptive statements about some part of the world (usually referred to as the domain of interest or the subject matter of the ontology). Precise descriptions satisfy several purposes: most notably, they prevent misunderstandings in human communication and they ensure that software behaves in a uniform, predictable way and works well with other software.

In order to precisely describe a domain of interest, it is helpful to come up with a set of central terms – often called vocabulary – and fix their meaning. Besides a concise natural language definition, the meaning of a term can be characterized by stating how this term is interrelated to the other terms. A terminology, providing a vocabulary together with such interrelation information constitutes an essential part of a typical OWL 2 document. …"

**skos:ConceptScheme**

Human-readable definition refers to "Section 4. Concept Schemes" in the SKOS reference as follows:

From https://www.w3.org/TR/skos-reference/#schemes

"A SKOS concept scheme can be viewed as an aggregation of one or more SKOS concepts. Semantic relationships (links) between those concepts may also be viewed as part of a concept scheme. This definition is, however, meant to be suggestive rather than restrictive, and there is some flexibility in the formal data model stated below."

RDF says:
```
skos:ConceptScheme a owl:Class ;
    rdfs:label "Concept Scheme"@en ;
    rdfs:isDefinedBy <http://www.w3.org/2004/02/skos/core> ;
    owl:disjointWith skos:Concept ;
    skos:definition "A set of concepts, optionally including statements about semantic relationships between those concepts."@en ;
    skos:example "Thesauri, classification schemes, subject heading lists, taxonomies, 'folksonomies', and other types of controlled vocabulary are all examples of concept schemes. Concept schemes are also embedded in glossaries and terminologies."@en ;
    skos:scopeNote "A concept scheme may be defined to include concepts from different sources."@en .
```
