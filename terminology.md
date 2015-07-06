# Notes on terminology related to vocabularies

This document contains some reference notes and has no official standing. It is subject to change at any time and should not be considered to be stable nor citable.

From the [W3C Semantic Web Vocabularies](http://www.w3.org/standards/semanticweb/ontology) page:

> On the Semantic Web, vocabularies define the concepts and relationships (also referred to as “terms”) used to describe and represent an area of concern. Vocabularies are used to classify the terms that can be used in a particular application, characterize possible relationships, and define possible constraints on using those terms. ...
> 
> There is no clear division between what is referred to as “vocabularies” and “ontologies”. The trend is to use the word “ontology” for more complex, and possibly quite formal collection of terms, whereas “vocabulary” is used when such strict formalism is not necessarily used or only in a very loose sense. ...

From the [Data on the Web Best Practices
W3C (Working Draft 25 June 2015)](http://www.w3.org/TR/dwbp/#dataVocabularies):

> Several categories of vocabularies have been coined, for example, ontology, controlled vocabularies, thesaurus, taxonomy, semantic network.
> 
> There is no strict division between the artifacts referred to by these names. “Ontology” tends however to denote the vocabularies of classes and properties that structure the descriptions of resources in (linked) datasets. In relational databases, these correspond to the names of tables and columns; in XML, they correspond to the elements defined by an XML Schema. ...
> 
> On the other hand, “controlled vocabularies”, “concept schemes”, “knowledge organization systems” enumerate and define resources that can be employed in the descriptions made with the former kind of vocabulary. A concept from a thesaurus, say, “architecture”, will for example be used in the subject field for a book description (where “subject” has been defined in an ontology for books). For defining the terms in these vocabularies, complex formalisms are most often not needed. Simpler models have thus been proposed to represent and exchange them, such as the ISO 25964 data model or W3C's Simple Knowledge Organization System.

From the TDWG [Key to Standard Categories](http://www.tdwg.org/standards/status-and-categories/):

> **Technical Specification (TS)**
> 
> Any description of a protocol, service, procedure, convention, or format, as described in RFC 2026.
> 
> **Applicability Statement (AS)**
> 
> Specifies how, and under what circumstances, one or more TS (from TDWG or other standardization bodies) may be applied to support a particular feature or capability. An AS identifies the relevant TSs and the specific way in which they are to be combined, and may also specify particular values or ranges of TS parameters or subfunctions of a TS protocol that must be implemented. An AS also specifies the circumstances in which the use of a particular TS is required, recommended, or elective. For more information, see RFC 2026. 
> 
> **Best Current Practice (BCP)**
> 
> A description of standardized practices and the results of community deliberations. A BCP document is a vehicle by which the biodiversity information community can define and ratify the community's best current thinking on a statement of principle or on what is believed to be the best way to perform some operations or TDWG process function. For more information, see RFC 2026. 
> 
> **Data Standard (DS)**
> 
> Specifies valid values in controlled vocabularies.

Current TDWG standards include examples of Technical Specification (including the Darwin Core and Audubon Core vocabularies) and Applicability Statement.  There are no current examples of Best Current Practice nor of Data Standard.

## Summary comments
1. A vocabulary defines terms.
2. A term may be a property, class, or controlled vocabulary value.
3. An ontology typically defines properties and classes, including the relationships among them and possible constraints on term use. The term "ontology" is most typically used to describe vocabularies containing complex, formal definitions, often specified using a language like OWL. However, there is no strict definition that differentiates between a complex ontology and a simpler vanilla "vocabulary".
4. A controlled vocabulary (concept scheme, KOS) can provide values for properties defined in an ontology. These value terms may be less formally defined using a model such as SKOS.
5. In the context of TDWG, an ontology (vocabulary that defines classes and properties) would fall into the Standard Category of Technical Specification. A controlled vocabulary would fall into the Standard Category of Data Standard.

## Terms related to the status of parts of standards documents

TODO: Define "normative", "non-normative", "informative", etc. in the context of standards documents.