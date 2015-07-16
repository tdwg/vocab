#TDWG Hierarchy Model
Preliminary Draft 2015-07-15 - Steve Baskauf - TDWG Vocabulary Management Task Group

Note: This document has no official standing. It is subject to change at any time and should not be considered to be stable nor citable.

![](https://raw.githubusercontent.com/tdwg/vocab/master/tdwg-standards-hierarchy-2015-07-15.png)


Note: each kind of resource described here can exist as a current resource and as versioned resources as described in the [version model](version-model.md)


##Definitions
**TDWG Standard** - a TDWG standard as an abstract entity.  A TDWG standard will have a human-readable component.  It may or may not include vocabulary(s) that define terms. 

The "permanent URL" (i.e. the IRI identifier) of the standard should dereference through content negotiation to a human-readable landing web page and to a machine-readable RDF description containing metadata about the standard.

rdf:type [unknown]

*Example:* 

`http://www.tdwg.org/standards/450/`

**umbrella vocabulary** - Each standard that defines a vocabulary will have one to many umbrella vocabularies.  Each vocabulary standard must define a basic vocabulary that includes all of the terms that are defined by the standard or are included in the standard by being imported from other sources. The inclusion of terms is accomplished by importing subvocabularies. Additional umbrella vocabularies may be created to apply additional semantics to the basic vocabulary.

rdf:type owl:Ontology, voaf:Vocabulary (?)

*Examples (made up):*

`http://rs.tdwg.org/dwc/basic-ontology`

**subvocabulary** - A subvocabulary is a particular grouping of terms that are included within one or more umbrella vocabularies. The subvocabulary IRI should dereference through content negotiation to a human-readable document that describes the terms included within that subvocabulary and to a machine-readable document that allows a semantic client to discover all of the terms that are part of that subvocabulary. The link between a subvocabulary and the terms it includes is made via a **dcterms:hasPart** property. Conversely, a term may be related to its containing subvocabulary using a **dcterms:isPartOf** property.

rdf:type owl:Ontology, dcat:Dataset(?), voaf:Vocabulary(?)

*Examples:*

`http://rs.tdwg.org/dwc/terms/`
`http://rs.tdwg.org/dwc/dcmi/`

**representations/distributions** - 

*<< It is not clear to me whether it is appropriate to use the terms of the [DCAT W3C Recommendation](http://www.w3.org/TR/vocab-dcat/) with vocabularies. The property **dcat:distribution** would be convenient, but it entails that the subject is a dcat:Dataset.  Is that how we want to type vocabularies?  What about the [VOAF vocabulary](http://lov.okfn.org/vocommons/voaf/v2.3/) (not part of any standard)?>>*

Standards, umbrella vocabularies, and subvocabularies are abstract resources. Humans and machines acquire information about these resources by retrieving documents.  The IRI of a standard, umbrella vocabulary, or subvocabulary should be persistent and should not change if the location of an associated document changes.  Therefore, the IRI of a subvocabulary must be distinct from a URL that facilitates retrieval of a representation of that subvocabulary.  

Content negotiation should be used to allow a human or machine to discover documents of a desired format.  

*<< Not sure where to go with this.  DCAT also allows distributions to include things like SPARQL endpoints and interactive websites that do not comprise retrievable documents.>>*

rdf:type dcat:Distribution(?)

*Example:*

```turtle

```

## Kinds of subvocabularies 

**root subvocabularies**

Each standard that defines a vocabulary will have at least one subvocabulary that defines terms that are managed by TDWG. A root vocabulary (is "base vocabulary" a better term for this?) contains the human-readable text that comprises the normative definition for each of the terms. The subvocabulary IRI for a TDWG root vocabulary will probably be the namespace for the terms defined by that vocabulary so that a client dereferencing one of the terms will discover the root subvocabulary document through content negotiation. For example, the main Darwin Core namespace **dwc:** (http://rs.tdwg.org/dwc/terms/) should return the defining RDF/XML document **dwcterms.rdf** .  For convenience or historical reasons, there may be more than one root subvocabulary/namespace (e.g.  **dwc:**, **dwciri:**, **dwcattributes:**).  Terms included in a root subvocabulary are linked to their containing subvocabulary by the term **rdfs:isDefinedBy** in addition to the more generic **dcterms:isPartOf** property. A root vocabulary should NOT include properties that  directly establish semantic relationships with another vocabulary term (e.g. **rdfs:subPropertyOf**), that place restrictions on the term (e.g. **owl:minCardinality**), or that establish a range or domain for the term (e.g. **rdfs:range**).  A root vocabulary may include properties that entail unstated relationships if those entailments are caused by the definition of a well-known property (e.g. the defined range of **dcterms:creator**). 

*Example:*

```turtle
<http://rs.tdwg.org/dwc/terms/> a owl:Ontology;
                                dcterms:hasPart dwc:recordedBy.
dwc:recordedBy rdfs:comment "A list (concatenated and separated) of names of people, groups, or organizations responsible for recording the original Occurrence. The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first."@en;
               rdfs:label "Recorded By"@en;
               dcterms:description """The recommended best practice is to separate the values with a vertical bar (' | '). The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first. Examples: \"José E. Crespo\", \"Oliver P. Pearson | Anita K. Pearson\" where the value in recordNumber \"OPP 7101\" corresponds to the number for the specimen in the field catalog (collector number) of Oliver P. Pearson."""@en;
               rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms/>;
               dcterms:isPartOf <http://rs.tdwg.org/dwc/terms/>.
```

**external subvocabularies**

Vocabulary standards that borrow terms from other vocabularies will have at least one subvocabulary that links to the terms defined outside that standard.  The IRI for an external subvocabulary should dereference through content negotiation to a human-readable document that will allow a person to find the documents that provide the normative definitions for the terms included in the terms.  A external vocabulary IRI should also dereference through content negotiation to an RDF document that links the subvocabulary to the terms that it contains via the **dcterms:hasPart** property.  If a term IRI dereferences to machine-readable RDF (e.g. **dcterms:references** imported by Darwin Core), providing additional properties of that term (e.g. **rdfs:label**) are optional since the other properties of that term are machine-discoverable.  However, if a term IRI does not dereference to machine-readable RDF (e.g. **xmpRights:UsageTerms** imported by Audubon Core), then the RDF in the subvocabulary document should also contain at a minimum an **rdfs:comment** property whose value is a literal that comprises the human-readable definition of the term.   

```turtle
<http://rs.tdwg.org/ac/borrowed/>  dcterms:hasPart dcterms:identifier;
                                   dcterms:hasPart xmpRights:UsageTerms;
                                   a owl:Ontology.
dcterms:identifier rdfs:label "Identifier"@en;
                   dcterms:isPartOf <http://rs.tdwg.org/ac/borrowed/>.
xmpRights:UsageTerms rdfs:label "License Terms"@en;
                     rdfs:comment "The license statement defining how resources may be used. Information on a collection applies to all contained objects unless the object has a different statement.";
                     dcterms:isPartOf <http://rs.tdwg.org/ac/borrowed/>.
```
**semantically-enhanced subvocabularies**

Vocabulary standards may include zero-to-many subvocabularies that establish more complex semantics by applying additional properties to terms defined in a different subvocabulary.  The terms referenced in such semantically-enhanced subvocabularies should be related to the containing subvocabulary using **dcterms:partOf** and **dcterms:isPartOf**.

```turtle
<http://rs.tdwg.org/dwc/enhanced/>  dcterms:hasPart dwciri:recordedBy;
                                   dcterms:hasPart dwc:MaterialSample;
                                   a owl:Ontology.
dwciri:recordedBy a owl:ObjectProperty;
                  dcterms:isPartOf <http://rs.tdwg.org/dwc/enhanced/>.
dwc:MaterialSample rdfs:subClassOf obi:0100051;
                  dcterms:isPartOf <http://rs.tdwg.org/dwc/enhanced/>.
```
## Competency questions
The following SPARQL queries show how this model enables the discovery of all resources that are part of a vocabulary standard.

The screenshots show what happens when the query is run on the [Ontology Vocabulary sample file](https://github.com/tdwg/vocab/blob/master/code-examples/ontology-vocabulary.ttl)

----------


List all of the terms that are included within the basic Darwin Core vocabulary and list the subvocabulary that contains each term.

```sparql
SELECT DISTINCT ?term ?subvocab WHERE {
  <http://rs.tdwg.org/dwc/basic-vocabulary>  owl:imports ?subvocab.
  OPTIONAL { ?subvocab dcterms:hasPart ?term. }
  OPTIONAL { ?term dcterms:isPartOf ?subvocab. }
}
```

![](https://raw.githubusercontent.com/tdwg/vocab/master/code-examples/query4.png)

Note: Since DCMI does not declare `dcterms:hasPart owl:inverseOf dcterms:isPartOf`, the query must allow either of the possible triple patterns involving those two terms.

----------

List all of the property terms that are defined by a Darwin Core subvocabulary and list the subvocabulary that defines each term.

```sparql
SELECT DISTINCT ?term ?subvocab WHERE {
  <http://www.tdwg.org/standards/450/> dcterms:hasPart ?vocab.
  ?vocab a owl:Ontology.
  ?vocab owl:imports ?subvocab.
  ?term rdfs:isDefinedBy ?subvocab.
  ?term a rdf:Property.
}
```

![](https://raw.githubusercontent.com/tdwg/vocab/master/code-examples/query5.png)

----------

List all of the properties and values dwciri:recordedBy from any subvocabulary

```sparql
SELECT DISTINCT ?property ?value WHERE {
  dwciri:recordedBy ?property ?value.
}
```

![](https://raw.githubusercontent.com/tdwg/vocab/master/code-examples/query6.png)

Notice that the type declarations from both subvocabularies are included (primary and semantic relations).

Note: the triplestore included all triples in the [Ontology Vocabulary sample file](https://github.com/tdwg/vocab/blob/master/code-examples/ontology-vocabulary.ttl).  To restrict queries to only the Basic Vocabulary or the Enhanced Vocabulary, the vocabulary definitions would need to be placed in different documents and the query performed on named graphs (or whatever that's called when you use the FROM keyword).
