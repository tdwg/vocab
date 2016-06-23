# TDWG Standards Documentation Specification #

This draft was revised following the VOCAB Task Group call of 2015-05-04.  However, it still should be considered neither stable nor citable.

**Title:** TDWG Standards Documentation Specification

**Date Issued:**

**Date Modified:**

**Contributors:** Steve Baskauf (TDWG Vocabulary Maintenance Specification Task Group), Roger Hyam (TDWG Infrastructure Project), Stan Bloom (TDWG Process Interest Group), Bob Morris (TDWG Imaging Interest Group), Joel Sachs (TDWG RDF Task Group), Greg Whitbread (TDWG Technical Architecture Group), John Wieczorek (TDWG Darwin Core Task Group).

**Creator:** TDWG Vocabulary Maintenance Specification Task Group

**Abstract:** This document defines how TDWG standards should be presented.  It provides details about the hierarchical structure of standards and versioning of standards components.  It specifies how the properties of standards and their components should be described in human-readable and machine-readable terms.

**Legal:** This document is governed by the standard legal, copyright, licensing provisions and disclaimers issued by Biodiversity Information Standards (TDWG).

**Part of TDWG Standard:**

### Table of Contents ###

[generate when complete]

## **1 Introduction** ##

Standards adopted by Biodiversity Information Standards (TDWG) may include a number of components that are expressed in human- and machine-readable documents. It is important that users of a standard be able to locate all of these components. Users should be able to easily determine which parts of the standard are definitive (normative) and which are informative (non-normative). It should also be apparent which components are current and which are maintained for historical reasons or to support legacy applications. Machine-readable documents should be linked and described consistently to facilitate automated discovery and processing. This standard specifies how documents should be presented to achieve these requirements.

### **1.1 Audience** ###

This document is intended primarily for those who are writing TDWG standards and vocabularies.  It may also be useful for those who are developing applications that use TDWG vocabularies, since it defines the structure of terms and term lists in those vocabularies, and kinds of available metadata about those terms.

### **1.2 Content** ###

This is the only document associated with the Standards Documentation Specification.  Unless otherwise designated, all sections of it are normative.  It first describes the overall structure of a TDWG standard, then details how standards documents should be written so that they contain the necessary information to be understood by humans and by machines.

### **1.3 Examples in this document** ###

RDF examples in this document are included to clarify the normative text, although they are not themselves normative.  In some cases, IRIs represent actual standards, documents, or terms, but in many cases they are fictitious.  Additionally, in cases where the IRIs represent real resources, the properties and values shown in the examples may not represent real metadata about those resources.  The triples included in the examples do not represent a complete graph containing all of the triples necessary to comply with this standard.  Rather, they show triples that illustrate the relationships described in the sections that precede the example.  

RDF/Turtle is used in all of the examples because it is generally the easiest machine-readable serialization for humans to comprehend.  Use of Turtle does not imply that it is a preferred serialization for representing the metadata and relationships among resources in machine-readable form.  Other serializations such as RDF/XML, RDFa, and JSON-LD might also be used to represent the same information.  Best-practices with respect to serialization should be established by community consensus in an effort outside of this standard.

### **1.4 Definitions** ###

**content negotiation** - a mechanism by which a client and server determine the best representation to send to the client based on the client's expressed preferences [HTTP-1.1]

**controlled vocabulary** - prescribed list of terms, each representing a concept. Controlled vocabularies are designed for applications in which it is useful to identify each concept with one consistent label. Metadata properties can interact with controlled vocabularies when the value of a property is constrained to be a term from a controlled vocabulary. [ISO-25964-2]

**current resource** - a resource as it exists in its current state.  The current state reflects the most recent version of the resource.

**deprecated** - a resource is no longer valid for use.  To avoid breaking existing applications, the resource is not deleted, but rather is marked as deprecated in its metadata.  If the resource has been replaced by an alternative, the resource's metadata should specify the recommended replacement.

**dereference** - to use an IRI to obtain a representation of a resource through an Internet protocol such as HTTP

**distribution** - a specific available form of a dataset.  In the context of this standard, distributions are available forms of vocabulary term lists, such as downloadable files in RDF/XML or RDF/Turtle. [DCAT]

**document** - In this context, a document is a unit of information that can be stored or retrieved electronically as a single file.

**HTTP IRI** - A subset of IRIs that enable retrieval of a representation using Hypertext Transfer Protocol (HTTP).  HTTP IRIs begin with "http://".

**IRI** - Internationalized Resource Identifier. A superset of Uniform Resource Identifier (URI) that uniquely identifies a resource using characters from any character set. [IRI]

**metadata scheme** - a vocabulary used to make assertions about individuals (sensu OWL [OWL-OVERVIEW]). Terms (or "elements") in the scheme may represent classes or properties. Axioms may describe term properties to form an ontology. [NISO] [ISO-25964-2]

**normative** - the prescriptive part of a standard that specifies that which is necessary to comply with the standard

**non-normative** - an informative part of a standard that provides supplemental information such as history, examples, and additional explanation beyond the information necessary to comply with the standard.

**representation** - a view of a resource at a particular time. Representations can differ in language or format. [HTTP-1.1]

**resource** - Any kind of thing that can be identified. Resources can include documents, people, physical objects, and abstract concepts [RDF-PRIMER].

**term list** - A document that is part of a vocabulary and that lists the terms within the vocabulary that are grouped in a particular way, such as falling within a particular namespace.  

**user** - This standard refers to two categories of users.  A user may be a human user interacting with a server through a user-agent (software such as a Web browser), and referred to in brief as a "human".  A user can also be a semantic client: computer software interacting semi-autonomously with a server, and referred to in brief as a "machine".  Both a user-agent assisting the human, and a semantic client are referred to generically as "clients".

**version** - a “snapshot” of a resource in time.  A version is created at a particular moment in time and documents the state of the resource until that version is replaced by a later version.  

**vocabulary** - a collection of standardized terms and their definitions.  Terms may represent classes, properties, or concepts.

**vocabulary extension term list** - a specialized type of term list that asserts additional properties for terms beyond their basic human-readable definitions.  For example, a vocabulary extension may assert for a term subclass or subproperty relations, class restrictions, ranges or domains, etc.  

### **1.5 Namespaces used in this document** ###

 In the text and examples, IRIs are frequently abbreviated using namespace abbreviations.  The abbreviations used in this document are shown in the following table.

| **Prefix**   | **Namespace**                               |
|--------------|---------------------------------------------|
| dc           | http://purl.org/dc/elements/1.1/            |
| dcat         | http://www.w3.org/ns/dcat#                  |
| dcterms      | http://purl.org/dc/terms/                   |
| dcmitype     | http://purl.org/dc/dcmitype/                |
| dwc          | http://rs.tdwg.org/dwc/terms/               |
| dwcattributes| http://rs.tdwg.org/dwc/terms/attributes/    |
| dwciri       | http://rs.tdwg.org/dwc/iri/                 |
| owl          | http://www.w3.org/2002/07/owl#              |
| rdf          | http://www.w3.org/1999/02/22-rdf-syntax-ns# |
| rdfs         | http://www.w3.org/2000/01/rdf-schema#       |
| skos         | http://www.w3.org/2004/02/skos/core#        |
| vann         | http://purl.org/vocab/vann/                 |
| xmpRights    | http://ns.adobe.com/xap/1.0/rights/         |

## **2 The structure of TDWG standards** ##

If a standard were composed of a single, human-readable document, then identifying and retrieving that document via the Internet would be relatively simple.  But TDWG standards may be composed of multiple documents that may change over time and that may be delivered in a variety of formats.  This section describes the structure of TDWG standards and the relationships among the structured components of a standard.

![](graphics/representations.png)

Fig. 1. An abstract resource and its representations.

### **2.1 Abstract resources and representations** ###

A TDWG standard may be composed of several types of components.  For example, the standard may contain an explanatory document that describes how the standard should be applied in certain circumstances.  A standard may also include a vocabulary description that defines the terms included in that vocabulary.  We can consider each of these particular resources as an abstract entity that manifests itself in one or more than concrete representations.  For example, a document may exist in PDF format or as an HTML web page (Fig. 1), or a document may exist as translations in several languages.  

**2.1.1 IRIs**

Particular resources are assigned globally unique identifiers (GUIDs) to distinguish them from all other resources.  TDWG identifies resources using HTTP IRIs, a type of GUID which makes it possible to retrieve a representation of a resource using HTTP (hypertext transfer protocol).  

Both the abstract resource and specific representations of that resource are identified with HTTP IRIs.  

The IRI for abstract resources should be generic.  That is, the abstract resource IRI should not specify a file extension nor should it be structured in a way that is dependent on a particular technology or query format [COOL-URIS].  In contrast, IRIs of particular resource representations may use an IRI structure or file extension that is useful for retrieving a copy of that resource. The IRIs of abstract resources should be stable, allowing them to be used in citations of the resource.

**2.1.2 Content negotiation**

A resource will normally be permanently identified by its abstract resource IRI.  When client that attempts to retrieve a representation of that resource by dereferencing its abstract IRI, it should be redirected through content negotiation to a URL that can be used to retrieve a representation of the content type or language requested by the client (Fig. 1) [GUID, Recommendation 7].  A resource may be available as several content types, but all resources should be retrievable in a human-readable form when media type text/html is requested.  It is also best practice to make a machine-readable representation available.  If the resource is a document that is primarily intended for human consumption, then the machine-readable representation should at a minimum contain descriptive metadata about the document. In some cases (such as vocabularies), the machine-readable representation of the resource will contain a complete description of the resource.  

![](graphics/std-parts.png)

Fig. 2. A standard and its components.

### **2.2 Standards components hierarchy** ###

TDWG standards consist of several IRI-identified components.  This section describes these components and how they are related to each other.

**2.2.1 Standards landing page**

Each TDWG standard will be identified by an HTTP IRI (formerly known as the "permanent URL" of the standard) that represents the standard as an abstract entity.  When the standard's IRI is dereferenced by a client requesting media type text/html (e.g. a Web browser), that IRI should redirect to a human-readable landing webpage that describes the status of the standard, contains an abstract of the standard, and contains hyperlinks to the various components that comprise the standard.  When the standard's IRI is dereferenced by a client requesting a machine-readable format such as RDF, the client should be redirected to a document that contains machine-readable metadata about the standard.  That document should link the components of the standard to the standard using the property dcterms:isPartOf (Fig. 2) as described in Section 4.2.  Components can include descriptive documents and vocabularies.

**2.2.2 Descriptive documents**

Each TDWG standard will have at least one human-readable document that describes the purpose of the standard and that contains information about how the standard is to be used.  That document should follow the formatting guidelines of Section 3.  When the IRI of the descriptive document is dereferenced by machine clients, the client should retrieve a machine-readable description of the document's metadata.  

![](graphics/vocabulary-documents.png)

Fig. 3. Relationship of a vocabulary to its component term list documents.

**2.2.3 Vocabulary documents**

TDWG vocabularies will be associated with an HTTP IRI that represents the vocabulary itself.  The vocabulary is distinct from the standard, since the vocabulary is just one part of the standard.  For this reason, the vocabulary IRI will not be the same as the IRI that identifies the standard.  When the vocabulary IRI is dereferenced by a client requesting media type text/html, the client should obtain a web page that links to term list documents (Fig. 3).  Each term list document corresponds to one or more namespaces that include sets of terms.  Usually, there will be at least one document that lists and describes terms defined in a namespace controlled by TDWG.  The human-readable representation of that document will contain the normative definition of each TDWG-defined term.  The machine-readable representation of that document will contain the minimal machine-readable metadata described in Sections 4.2 and 4.4.2.  There may also be documents that list terms in namespaces outside of the standard or terms that are not defined by TDWG.  Human-readable representations of these documents will contain links to the websites that define those terms.  

Term lists may include terms that are defined elsewhere, but assert additional properties for those terms that are not included in those terms' definitions.  Such extensions can add semantic layers that are desired by some users, but that are not desired by other users who need only the basic term definitions.  

![](graphics/distributions.png)

Fig. 4. Relationship of a term list document to its distributions.

**2.2.4 Distributions**

Vocabulary term lists as abstract resources also exist as more concrete entities that can be stored and delivered.  A human user or semantic client may discover these entities through the content negotiation process (Section 2.1.2) when dereferencing the term list IRI.  However, that process is somewhat akin to trial and error, since a user would not know that the abstract resource was available in forms that were not requested.  In addition, the term list may be available for download in a form such as Markdown that is rendered as HTML when the term list URI is dereferenced requesting media type text/html, yet availability of the list in Markdown form may not be apparent to users that see the content rendered in a browser.  To enable discovery of the all forms by users or catalogers, the available forms of a resource, known as "distributions" (Fig. 4), should be made known to both humans and machines.  To accomplish that discovery, the Data Catalog Vocabulary [DCAT] should be used to indicate the links from a vocabulary's term list to its available distributions.

All distributions of a term list should contain substantively the same information about the terms on the list.  Thus a user retrieving any of the distributions should be able to learn the same properties and their values for all of the terms.

![](graphics/version-model.png)

Fig. 5. Relationship of a resource to its versions over time.

### **2.3 Versioning model** ###

Resources associated with TDWG standards may change over time.  TDWG uses a versioning model that relates the current resource and versions of the resource that have changed over time.  The purpose of the versioning model is to enable a user to start with the current resource or any version of the resource and trace the changes that have occurred to that resource over time.

**2.3.1 Current resources**

Each resource (document, vocabulary, term, etc.) exists in a current state.  That current state reflects the most recent version of that resource.  The current resource is identified by an IRI that does not change over time.  The current resource IRI can be used by humans or machines to retrieve a representation of the resource as it exists at the present time.  Because the current resource IRI does not change, it is stable and should be the IRI that is cited and is linked to whenever one wishes to refer to the resource in general.  

**2.3.2 Versions**

Each resource also exists as versions that document “snapshots” of the resource over time (Fig. 5).  A version is issued at a particular moment in time and documents the state of the resource until the version is replaced by a later version.  Each version of a resource is identified by an IRI that is distinct from the IRI of the current resource and from all other versions of that resource.  Typically, the IRI of a version is formed by appending the ISO 8601 creation date of the resource to the IRI of the abstract resource.  

A current resource is related to one of its versions by the property dcterms:hasVersion.  A version is related to its current resource by the property dcterms:isVersionOf, to a version that it supersedes by dcterms:replaces, and to a version that supersedes it by dcterms:isReplacedBy.  The metadata for a current resource should specify the IRI of the current resource, the IRI of the most recent version, and the IRI of any previous version that was superseded.  Metadata of a past version should specify that version's IRI, specify the IRI of the current resource, and link to any previous or subsequent versions.  

The versioning model is specific to neither humans nor machines, and either should be able to use the resource IRIs and properties to traverse the links from one version to another.  


## **3 Human-readable documents** ##

In order for a standard to achieve its purpose, it must include documents that permit human users to understand what is necessary to comply with the requirements of the standard.  This section describes how human-readable documents should be constructed to make this possible.

### **3.1 Landing page for the standard** ###

When the HTTP IRI of a standard is dereferenced by a client requesting text/html (for example, when a human uses a Web browser), the client should receive a human-readable document that describes basic information about the standard as described in the subparts of this section.  

**3.1.1 Name of the standard**

The full name must be in English and
must be unique within the scope of TDWG standards, but otherwise is not
controlled and may contain any combination of characters.

**3.1.2 IRI of the standard**

The landing page should include the HTTP IRI that identifies the standard.  The text of the landing page should indicate that the identifying HTTP IRI is the IRI that should be cited and is the IRI to which hyperlinks should be made.  Providing this information is important because content negotiation may redirect users to some other IRI that is specific to the delivery mechanism and that might be subject to change at some time in the future.

**3.1.4 Link to TDWG**

The landing page should make it clear that this is a TDWG standard and should provide a link to the TDWG home page.  

**3.1.5 Abstract**

An abstract should provide a brief description of the purpose of the standard.

**3.1.6 Status of the standard:**

One of the status categories listed at [http://www.tdwg.org/standards/status-and-categories/](http://www.tdwg.org/standards/status-and-categories/).

**3.1.7 Preferred citation**

The landing page should indicate a preferred citation for the standard that includes at least the name of the standard and the IRI. The exact format and content of the citation is not specified by this standard.

**3.1.8 Links to parts of the standard**

Each part of the standard should be listed, with a hyperlink that leads to that part (Section 2.2).  The parts must include at least one descriptive document, whose form is described in section 3.2.

### **3.2 Descriptive documents** ###

A standard has one or more descriptive documents that describe the purpose of the standard, and that contain information about how the standard is to be used. The choice of whether to place all of this material in a single document or to separate it into several documents should be made based on what will make the standard the most easy to understand and use.  

**3.2.1 Normative and non-normative sections of descriptive documents**

The normative and non-normative parts of standards should be clearly labeled as such.  If all of the content of a document is normative, this should be stated in the introduction to the document.  If a single document contains both normative and non-normative content, material in a single section should be of a single type.  The introduction should state that content is normative unless otherwise noted and headings should indicate if material in that section is non-normative.

It is also permissible to indicate in the introduction that content of a particular type (e.g. examples or diagrams) is non-normative.

**3.2.2 Versioning**

Descriptive documents are resources that follow the versioning model described in Section 2.3.  Each particular document version will represent the state of the generic document from the time it was issued until the time that version was superseded by a later version.  Thus, the date issued that is stated on a particular document version will reflect the date that particular version was issued (dcterms:issued).  Date created (dcterms:created) should be reserved to indicate the date that the first version of the document was issued.

**3.2.3 Layout and style**

Descriptive documents should be divided into four main sections:

-   A header section
-   Table of contents
-   A body section
-   A footer section

**3.2.3.1 Header Section**

The header section must contain the following parts:

**Title:** The title of the document.

**Date Issued:** The date of publication of this version in ISO 8601 Date format.

**Part of TDWG Standard:** The IRI of the standard of which this document is part. The IRI should dereference to the standard's landing page.

**This version:** The IRI of the specific version of the document that is being displayed.

**Latest version:** The current resource IRI that will always return the latest version of the document.

**Previous version:** The IRI of the previous version (if any).

**Replaced by:** The IRI of the next version (if any).

**Abstract:** A single paragraph summary of the document.

**Contributors:** A list of the people who are responsible for the
document's creation. The first person in the list should be the
principal contact.

Contributors’ names should be listed in full in the form that they typically use professionally.

A contributor's name may be followed by his or her affiliation in parentheses. Affiliation is the organization or group the contributor is working with in relation to the document.

**Creator:** The Task Group that created the document.

**Bibliographic Citation:** How the document should be cited.

If the document is no longer recommended for use (i.e. deprecated), this should be noted in a **Status Note**, with a description of the reason, and links to recommended alternatives.  This deprecation is distinct from replacement by a newer version of the same document, which should be indicated in the "Replaced by" field.  This applies to documents that are vocabulary descriptions (section 3.3), although usually particular vocabulary terms are deprecated rather than the entire vocabulary.  

**3.2.3.2 Table of Contents Section**

The table of contents section should contain an ordered list of all the headings (along with their numbers) that occur in the body section.

**3.2.3.3 Body Section**

The body text should be divided by a hierarchy of subheadings. The subheadings must be numbered consecutively using simple decimal system. The final number must not be followed by a decimal point. An example:

1 First Main Section

1.1 First subsection within first main section.

1.12.5 The fifth sub-subsection within the twelfth subsection of the first section.

2 Second Main Section

The first section of the body should be an introduction.  At a minimum, the introduction should explain the purpose of the document.  In the case of a standards landing page, the introduction should describe the general purpose of the entire standard.  The introductory section may include subsections as the authors deem necessary to introduce other information relevant to the entire document.

**3.2.3.4 Footer section**

The footer should contain a copyright statement and licensing information.  Typically, the copyright is held by Biodiversity Information Standards (TDWG) and the license is [Creative Commons Attribution](http://creativecommons.org/licenses/by/4.0/) (CC BY).  It should also include a preferred citation in human-readable form and provide access to one or more standardized machine-readable citation export formats.

[This used to say: "A reference or link to a document containing the Copyright, Licensing and Disclaimer statements that govern this document. This will usually be the standard one supplied by TDWG."  This has been included in some standards documents, but not consistently.]

**3.2.4 Language**

Standards documents must be written in English. Translations of standards documents are encouraged, but to simplify management of the standard they will be treated as ancillary documents that are not included in the standard.

### **3.3 Vocabulary descriptions** ###

Documents that describe vocabularies make up a special category of human-readable descriptive documents.  As such, vocabulary descriptions will comply with the requirements of Section 3.2.  However, they will also have additional characteristics as described in the following sections.

**3.3.1 Landing page for the vocabulary**

Although a standard may define a vocabulary, the standard may also include other documents such as guides that describe how the vocabulary may be used in different contexts.  It is also possible for a standard to define several vocabularies that may share subsets of terms defined by the vocabulary.  Thus it is clear that a vocabulary is an entity that is distinct from the standard that defines it.  As such, the vocabulary will have an IRI that is distinct from the standard's IRI.  The vocabulary's landing page is the page that is presented to a human user when the vocabulary IRI is dereferenced and media type text/html is requested.

In its header, the landing page will contain the metadata described in Section 3.2.3.1, with the most recent release date serving as the Date Issued, and the vocabulary IRI serving as the Latest Version IRI.

As with other descriptive documents, the body of the landing page should contain an explanation of the purpose of the vocabulary.  However, it must also contain links to the term lists that indicate the terms that make up the vocabulary (Section 3.3.3).  

**3.3.2 Terms as versioned resources**

A term is a resource that persists over time (Fig. 5) and that complies with Section 2.3 of this standard. The current state of the term is represented by the term IRI, which does not change and which can be dereferenced to discover the current term definition.  

The state of the term at particular times is recorded via versions of the term.  A new version of the term is issued on a particular date and the term version IRI should be dereferenceable to discover the definition of the term version when it was issued.  

**3.3.3 Term list documents**

A term list is a document that contains a series of term entries that can be easily read and understood by humans.  Each vocabulary will have at least one term list that contains terms that are defined by the standard that contains it.  Vocabularies may also have term lists that contain terms that are borrowed from other vocabularies that define those terms.  For lists of terms that are defined by the standard, the term list will be identified by an IRI that corresponds to the namespace used with the listed terms, and that IRI will dereference to the term list document that describes the terms from that namespace.  For lists of terms borrowed from other vocabularies, any IRI may be used.  Although the lists of borrowed terms will be identified by a different IRI, it is permissible for the borrowed terms to be included in the same human-readable term list document as the terms defined by the standard.  In that case, the borrowed term list IRI should be designed so that it will dereference to the page on which the borrowed terms are listed (e.g. through use of a hash appended to the namespace IRI).

Term lists may also be vocabulary extensions.  A vocabulary extension describes additional properties of a term that are not included in the basic human-readable definition.  A vocabulary extension must be identified by a different IRI from the basic term list.  Because the mechanism of importing machine-readable representations of vocabulary extension term lists requires that those lists be included in separate documents, achieving content negotiation for both human- and machine-readable representations is simplest if the human-readable representations are also in separate documents from other human-readable term list documents that form parts of vocabulary standards.  

**3.3.3.1 Term list metadata**

Term lists containing terms defined by TDWG must include the following items in their header in addition to those required for documents in general:

**Namespace URI** - the IRI that identifies the term list.

**Preferred namespace abbreviation** - the preferred abbreviation for the term list namespace.

Each term entry on the list should include the following items.

**Term name** (required) - The term name is a controlled value that represents the class, property, or concept described by the term definition.  The term name is composed of the local name part of the term IRI, with a prepended namespace abbreviation (QName) that is defined in the header section of the vocabulary list document. [RECIPES] The term name is often related to the meaning of the term, but users must not attempt to understand the meaning of the term by interpreting its name.  Rather, the term definition should be consulted.

**Label** (required) - The label is a word or short phrase that serves as a human-readable name for the term.

**Value** (required for controlled vocabularies, not applicable to metadata schemes) - A string that is unique within a controlled vocabulary that identifies the concept in the context of a text-based metadata transfer system.  The value should consist of Unicode characters.

**Term IRI** (required) - The HTTP IRI that uniquely identifies the current term

**Term version IRI** (required if defined by the containing vocabulary) - The HTTP IRI that identifies the version of the term that is currently in force.

**Modified** (required if defined by the containing vocabulary) - The date in ISO 8601 Date format on which the most recent version of the term was issued.

**Decision** (required if the term was created or modified as the result of an Executive Committee decision) - The HTTP IRI representing the record of the decision affecting the term.

**Definition** (required) - The normative definition of the term, written in English.  The definition should include precisely the wording required to describe the class, property, or concept.  Additional informative content should be presented in comments or notes.

**Type** (required) - Values include "Class", "Property", and "Concept".

The term list may contain other properties of the term that are deemed to be useful, including informative comments or notes that provide examples or clarification.

**3.3.3.2 Term list distributions**

The term list document should contain a section listing the available distributions for the term list.  Each item on the list should contain a description of the form of the distribution, the IRI of the distribution, and the download or access URL for the distribution.  If the distribution is a file, the format should be described.  If the distribution is an endpoint, the type of endpoint (for example, SPARQL or an API delivering JSON) should be described. If the distribution is viewable in a human-friendly web page, the distribution IRI may be hyperlinked to that page.  The download or access URL should be listed and hyperlinked to the raw file or access URL for the endpoint.  A client should be able to retrieve the raw file in the described format directly from the download URL.  A client should be able to make calls directly to the access URL of the endpoint.

**3.3.3.2.1 Example distributions record (non-normative)**

Distributions for the term list of core terms that are defined in the Darwin Core dwc: namespace

| Description | IRI | Download URL |
|-------------|-----|--------------|
| HTML file   | [http://rs.tdwg.org/dwc/terms/index.htm](https://github.com/tdwg/dwc/blob/master/terms/index.htm) | https://raw.githubusercontent.com/tdwg/dwc/master/terms/index.htm |
| RDF/XML file | [http://tdwg.github.io/dwc/rdf/dwcterms.rdf](https://github.com/tdwg/dwc/blob/master/rdf/dwcterms.rdf) | https://raw.githubusercontent.com/tdwg/dwc/master/rdf/dwcterms.rdf |

**3.3.4 Term version lists**

A term version list provides a historical record of all versions of terms that are defined as part of a standard.  It is similar to the term list described in section 3.3.3, except that the entries on the list are versions of terms rather than current terms.  

The term version list should be identified by an IRI that facilitates discovery of the term versions that it lists when the term version IRIs are dereferenced.  

Each term version entry must include the following items.

**Term name** - The term name will be the same as the name used for the current term when the version was recommended.  Because there may be several versions of the term on the list, the term name will not necessarily be unique on the list.  

**Term version IRI** - The HTTP IRI that identifies the particular version of the term.

**Version of** - The HTTP IRI that uniquely identifies the current term associated with the version.

**Issued** - The date in ISO 8601 Date format on which the version was issued.

**Definition** - The normative definition of the term as it stood in that version.

**Replaces** - The IRI of the previous version (if any) that the subject version replaces.  

**Is replaced by** - The IRI of the subsequent version (if any) that replaces the subject version.

The term list may contain other properties of the term that are deemed to be useful.

## **4 Machine-readable documents** ##

It is desirable for semantic clients (machines) to be able to discover and process metadata associated with standards documents and vocabularies without human intervention. This section describes how machine-readable documents should be constructed to make this possible.

The relationships described in this section may be expressed as Resource Description Framework (RDF), but that is not to the exclusion of other methods that may be available for expressing the same relationships in a manner that also facilitates machine processing.

In the same way that immutability of human-readable documents is important for the stability of a standard, the content of machine-readable documents must also be immutable. Thus, the set of machine-readable relationships (a graph in RDF) must be unchanged within a version of a document or vocabulary. Regardless of the serialization in which the machine-readable metadata are provided, that serialization should parse to the same set of relationships (i.e. the same RDF graph).

### **4.1 Identifying a resource and the machine-readable document that describes it** ###

In the description of any resource, it is important to distinguish between the identifier for the resource and the identifier for the machine-readable document that describes it.  When describing a resource, the resource IRI should be the subject of statements about the current resource.  The machine-readable document that describes it must have a different IRI.  The resource should be linked to the document that describes it by the property dcterms:isReferencedBy, while the machine-readable document should be linked to the resource it describes by the property dcterms:references.  In the case of vocabulary term lists, the machine-readable document that describes the list may be one of the term list distributions.

When a client dereferences the resource IRI, it is desirable that content negotiation result in return of a machine-readable document that describes the resource in the format requested in the request header.

**4.1.1 Example of linking a resource to the machine-readable document that describes it (non-normative)**

The following example is expressed in RDF/Turtle:

```
<http://rs.tdwg.org/dwc/terms/guides/text>
     dcterms:title "Darwin Core Text Guide";
     dcterms:isReferencedBy <https://github.com/tdwg/dwc/blob/master/terms/guides/text/index.ttl>.

<https://github.com/tdwg/dwc/blob/master/terms/guides/text/index.ttl>
     dcterms:references <http://rs.tdwg.org/dwc/terms/guides/text>;
     dc:format "text/turtle".
```

When the resource IRI http://rs.tdwg.org/dwc/terms/guides/text is dereferenced requesting media type text/turtle, the server should redirect to the document https://github.com/tdwg/dwc/blob/master/terms/guides/text/index.ttl which contains the RDF description of the Darwin Core Text Guide in Turtle serialization.

### **4.1.2 Types of resources** ###

Indicate the class of which a resource is an instance by using rdf:type [GUID, Recommendation 11].  The following classes should be used:

|**Class**                          | **Machine-readable value**|
|-----------------------------------|---------------------------|
| Standard                          | dcterms:Standard          |
| Vocabulary                        | dcmitype:Dataset          |
| Term List                         | dcat:Dataset *            |
| Vocabulary Extension List         | owl:Ontology              |
| Distribution                      | dcat:Distribution         |
| Property                          | rdf:Property              |
| Class                             | rdfs:Class                |
| Term from a controlled vocabulary | skos:Concept              |         

\* The semantics of the DCAT Recommendation entail that an instance of dcat:Dataset is also an instance of dcmitype:Dataset.

Documents should be typed according to a well-known vocabulary.  

### **4.2 General metadata** ###

The same metadata that is presented in the header section of the human-readable representations of descriptive documents and vocabulary landing pages (Section 3.2.3.1) should be provided in corresponding machine-readable documents.  The following properties with appropriate values should be used to describe the document or vocabulary:

|**Human-readable label** | **Machine-readable property** | **Type of value** |
|-------------------------|-------------------------------|-------------------|
| Title                   | dcterms:title, rdfs:label *   | literal           |
| Part of TDWG Standard   | dcterms:isPartOf              | IRI that denotes the containing standard; omit for the standard itself|
| Contributors            | dc:contributor                | literal; repeat property for each contributor's name; omit for the standard itself since the contributors of each part will be listed |
| Creator                 | dc:creator                    | literal providing the name of the Task Group responsible for creating the document |
| License                 | dcterms:license               | IRI for a license; use CC BY for descriptive documents and CC0 for vocabularies |
| Legal                   | xmpRights:UsageTerms          | literal containing this text "This document is governed by the standard legal, copyright, licensing provisions and disclaimers issued by Biodiversity Information Standards (TDWG)."|
| Abstract                | dcterms:description           | literal containing the human-readable abstract of the document minus any references or hyperlinks |
| Bibliographic Citation  | dcterms:bibliographicCitation | literal           |

\* Both of these terms are well-known properties used to indicate a human-readable label for a resource.  Including both increases the likelihood that a consuming application will be able to present that label to human users.

The property dcterms:contributor should be used to link the document or vocabulary to an IRI that denotes the contributor. If a well-known IRI for the contributor is not available, dcterms:contributor may be used to link to a blank node that contains parsed components of the contributor's name.

[How do we decide the level at which contributors are acknowledged? For something like best-practice guides, it's clear.  But what about vocabularies and term lists?  Also, does TDWG have a policy that vocabularies (as opposed to descriptive documents) should be licensed CC0?  If not, it should!]

**4.2.1 Example of expressing general metadata (non-normative)**

```
<http://rs.tdwg.org/dwc/terms/guides/text>
     dcterms:title "Darwin Core Text Guide"@en;
     rdf:label "Darwin Core Text Guide"@en;
     dcterms:isPartOf <http://www.tdwg.org/standards/450/>;
     dc:contributor "Tim Robertson (GBIF)",
                    "John Wieczorek (MVZ)",
                    "Markus Döring (GBIF)",
                    "Renato de Giovanni (CRIA)",
                    "Dave Vieglais (KUNHM)";
     dcterms:contributor <http://orcid.org/0000-0001-6215-3617>,
                         [foaf:familyName "Wieczorek"; foaf:givenName "John"],
                         <http://orcid.org/0000-0001-7757-1889>,
                         [foaf:familyName "de Giovanni"; foaf:givenName "Renato"],
                         <http://orcid.org/0000-0002-6513-4996>;
     dc:creator "TDWG Darwin Core Task Group";
     dcterms:license <http://creativecommons.org/licenses/by/4.0/>;
     xmpRights:UsageTerms "This document is governed by the standard legal, copyright, licensing provisions and disclaimers issued by Biodiversity Information Standards (TDWG).";
     dcterms:description "Guidelines for implementing Darwin Core in Text files.";
     dcterms:bibliographicCitation "Darwin Core Task Group, Biodiversity Information Standards (TDWG). 2009. Darwin Core Text Guide. http://rs.tdwg.org/dwc/terms/guides/text/ (accessed on [date]).".
```

**4.2.2 Deprecating resources**

Deprecation of a resource is an indication that the resource is invalid or no longer recommended for use.  This is different from the situation where a resource is replaced by a newer version that is a modification of a previous version (section 4.3).  In all cases, deprecation of a resource is indicated by assigning the property owl:deprecated with a value of "true" datatyped as xsd:boolean.  An rdfs:comment property should provide a human-readable description of the circumstances of the deprecation.  If another resource provides additional information or a possible replacement, a link should be made from the deprecated resource to the other resource using rdfs:seeAlso.

When a resource is deprecated, that action represents a modification of that resource. Therefore, the value of dcterms:modified should be set to the date on which the decision to deprecate was made.  After the resource is deprecated, there should be no additional modifications to the resource.  So the dcterms:modified value of a deprecated resource represents the ending date of that resource's lifespan.

At the standard level, deprecation occurs when a standard is assigned to the [Retired Standard](http://www.tdwg.org/standards/status-and-categories/) category.

For information about deprecation of terms within vocabularies, see section 4.5.3.  

**4.2.2.1 Example of deprecation of a resource (non-normative)**

```
<http://rs.tdwg.org/ontology/Core>
     dcterms:title "TDWG Ontology - Core";
     owl:deprecated "true"^^xsd:boolean;
     rdfs:comment "This ontology is no longer under development and is no longer recommended for use.  See https://github.com/tdwg/ontology for information about recommended replacements.";
     rdfs:seeAlso <https://raw.githubusercontent.com/tdwg/ontology/master/replacements.rdf>.
```

### **4.3 Metadata describing and linking versions** ###

The property owl:versionInfo, which is expected to have a literal value, should be used to provide information about the version of a resource [GUID, Recommendation 13].  This standard does not specify a particular version identifying system; however, it should be understood that version information is intended for a human audience.  Therefore, a system should be used that makes it apparent to a human that a certain version precedes or follows another version.

A current resource is related to its versions by dcterms:hasVersion, [GUID, Recommendation 13] while a version is related to its current resource by dcterms:isVersionOf.  A version is related to a previous version by dcterms:replaces, while a version is related to a subsequent version by dcterms:isReplacedBy  [GUID, Recommendation 13].

The property dcterms:issued should be used to indicate the date on which a version was published.  The property dcterms:created should be used to indicate the date that the first version of a resource was issued.  The property dcterms:modified should be used to indicate the date that the most recent version was issued.

**4.3.1 Example of linking a current resource to its versions (non-normative)**

The following example is expressed in RDF/Turtle:

```
<http://rs.tdwg.org/dwc/terms/guides/text>
     dcterms:title "Darwin Core Text Guide"@en;
     rdfs:label "Darwin Core Text Guide"@en;
     dcterms:created "2009-12-07"^^xsd:date;
     dcterms:modified "2014-11-08"^^xsd:date;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/2014-11-08/terms/guides/text>;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/2009-12-07/terms/guides/text>.

<http://rs.tdwg.org/dwc/2014-11-08/terms/guides/text>
     dcterms:title "Darwin Core Text Guide (2014-11-08 release)"@en;
     rdfs:label "Darwin Core Text Guide (2014-11-08 release)"@en;
     owl:versionInfo "2014-11-08";
     dcterms:isVersionOf <http://rs.tdwg.org/dwc/terms/guides/text>;
     dcterms:issued "2014-11-08"^^xsd:date;
     dcterms:replaces <http://rs.tdwg.org/dwc/2009-12-07/terms/guides/text>.

<http://rs.tdwg.org/dwc/2009-12-07/terms/guides/text>
     dcterms:title "Darwin Core Text Guide (2009-12-07 release)"@en;
     rdfs:label "Darwin Core Text Guide (2009-12-07 release)"@en;
     owl:versionInfo "2009-12-07";
     dcterms:isVersionOf <http://rs.tdwg.org/dwc/terms/guides/text>
     dcterms:issued "2009-12-07"^^xsd:date;
     dcterms:isReplacedBy <http://rs.tdwg.org/dwc/2014-11-08/terms/guides/text>.
```

See also the example in section 4.5.3, which illustrates versioning of terms.

### **4.4 Vocabularies, term lists, and terms** ###

A vocabulary is a resource that may form part of a standard.  A vocabulary is described by the general metadata specified in section 4.2.  A vocabulary also includes lists of terms that the vocabulary contains.  Term lists are also described by metadata specified in section 4.2 as well as additional properties described in section 4.4.2.  Terms, term lists, and vocabularies have hierarchical relationships that are expressed using the property dcterms:isPartOf:

```
<:term> dcterms:isPartOf <:termList>.
<:termList> dcterms:isPartOf <:vocabulary>.
```

**4.4.1 Relationships between vocabularies and term lists**

Vocabularies consist of at least one term list (section 2.2.3).  In a case where it is likely that a vocabulary will never include terms beyond those defined by that vocabulary, it may be convenient to construct IRIs for the vocabulary and term list that will dereference to the same document.  For example, the vocabulary IRI might be http://rs.tdwg.org/ex, with the term list IRI http://rs.tdwg.org/ex/, or the vocabulary IRI might be http://rs.tdwg.org/ex/#vocab, with the term list IRI http://rs.tdwg.org/ex/.  With suitable server settings, these pairs of IRIs could dereference to the same representation.  This approach is not recommended when a vocabulary consists of, or is likely in the future to consist of terms from multiple namespaces.  In every case, in the interest of consistency with the hierarchy model, the term list IRI and the vocabulary IRI should be distinct and linked by dcterms:isPartOf.

**4.4.1.1 Example of relationships between vocabularies and term lists (non-normative)**

The following example is expressed in RDF/Turtle:

```
<http://rs.tdwg.org/dwc/basic>
     dcterms:title "Darwin Core Basic Vocabulary"@en;
     rdfs:label "Darwin Core Basic Vocabulary"@en;
     dcterms:isPartOf <http://www.tdwg.org/standards/450/>;
     a dcmitype:Dataset.

<http://rs.tdwg.org/dwc/enhanced-vocabulary>
     dcterms:title "Darwin Core Semantically Enhanced Vocabulary"@en;
     rdfs:label "Darwin Core Semantically Enhanced Vocabulary"@en;
     dcterms:isPartOf <http://www.tdwg.org/standards/450/>;
     a dcmitype:Dataset.

<http://rs.tdwg.org/dwc/terms/>
     dcterms:title "Core terms defined by Darwin Core"@en;
     rdfs:label "Core terms defined by Darwin Core"@en;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/basic>;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/enhanced-vocabulary>;
     dcterms:modified "2014-11-08"^^xsd:date;
     a dcat:Dataset.

<http://rs.tdwg.org/dwc/dwcattributes/>
     dcterms:title "Attributes defined by Darwin Core"@en;
     rdfs:label "Attributes defined by Darwin Core"@en;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/basic>;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/enhanced-vocabulary>;
     dcterms:modified "2009-12-07"^^xsd:date;
     a dcat:Dataset.

<http://rs.tdwg.org/dwc/dcmi-terms>
     dcterms:title "Dublin Core terms borrowed by Darwin Core"@en;
     rdfs:label "Dublin Core terms borrowed by Darwin Core"@en;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/basic>;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/enhanced-vocabulary>;
     dcterms:modified "2009-12-07"^^xsd:date;
     a dcat:Dataset.

<http://rs.tdwg.org/dwc/semantics/>
     dcterms:title "Darwin Core Semantic Relationships"@en;
     rdfs:label "Darwin Core Semantic Relationships"@en;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/enhanced-vocabulary>;
     dcterms:modified "2015-03-19"^^xsd:date;
     a dcat:Dataset.
```

**4.4.2 Metadata terms describing term lists**

Each set of terms defined by a TDWG standard that share a namespace will be included in a term list that corresponds to that namespace.  Thus, when the IRI of a term that is defined by the standard is dereferenced with a request for machine-readable metadata, a document may be returned through content negotiation that contains the metadata for those terms.  Other terms that are borrowed from other vocabularies will be grouped in one or more additional term lists.  

All terms are related to the term list that contains them by the property dcterms:isPartOf.    

Each term list containing terms defined by a particular standard will be the defining authority for those terms.  The special relationship between a term and the term list that defines it is indicated by rdfs:isDefinedBy.  Authoritative term lists should provide guidance to user about how namespaces should be abbreviated by using the following terms:

| **Human-readable label**    | **Machine-readable literal-value property**|
|-----------------------------|--------------------------------------------|
| Preferred namespace prefix  | vann:preferredNamespacePrefix              |
| Namespace IRI               | vann:preferredNamespaceUri                 |

When a preferred namespace prefix is chosen, care should be taken to ensure that there is no collision with other commonly used prefix abbreviations. The namespace IRI will often be the same as the IRI that identifies the term list, although this is not always the case, particularly when hash URIs are used.  For example, the SKOS ontology is identified by http://www.w3.org/2004/02/skos/core, but the SKOS namespace (usually abbreviated skos:) is http://www.w3.org/2004/02/skos/core#.

Term lists for borrowed terms are simply used to group those terms and are not authoritative.  So information about preferred namespace abbreviations and IRIs should not be included in the metadata about that term list.  However, if the defining authority for terms within a namespace fails to provide that information, it can be asserted within the document that contains the metadata about the term list.  

**4.4.2.1 Normative and non-normative content in machine-readable representations of term lists**

Although term lists are a form of descriptive document, they differ from generic descriptive documents in an important way.  The machine-readable representation of a descriptive document that is primarily human-readable will contain metadata about the document, but will not generally include most of the content of the document.  However, the machine-readable representation of a term list will contain substantively the same information as the human-readable document.  For that reason, it is important that any notations explaining the categories of term data that are normative must be preserved in the machine-readable data as well.  Such notations should be included as the value of an rdfs:comment property of the term list. For example, if the human-readable representation of the term list notes that term definitions are normative, but that comments are not, this note should be included as an rdfs:comment.  

**4.4.2.2 Vocabulary extension term lists**

If a vocabulary is extended by asserting properties of terms that generate machine-computable entailments (that is, axioms), those properties should be asserted in a machine-readable document that is separate from the machine-readable document that asserts the basic properties described in Section 4.5.  This separate document is a specialized kind of term list known as a vocabulary extension term list.   The axioms contained in the extension list can be combined with the metadata about terms contained in a basic term definition list to create an semantically enhanced ontology.  The annotation owl:imports is used by an ontology vocabulary to gain access to the entities and axioms contained in the basic and extension term lists [OWL-SYNTAX].  

The rdf:type of a vocabulary extension list is owl:Ontology. This is entailed by the range of owl:imports; nevertheless, it is desirable to assert this explicitly.  The type of a basic term definition list should not be declared explicitly to be owl:Ontology, since this implies a level of semantics that may not concern all users of the basic term list.  

**4.4.2.3 Examples (non-normative)**

An example of metadata about an authoritative term list:

```
<http://rs.tdwg.org/ac/>
     dcterms:title "Basic Audubon Core Vocabulary"@en;
     rdfs:label "Basic Audubon Core Vocabulary"@en;
     a dcmitype:Dataset;
     dcterms:hasPart <http://rs.tdwg.org/ac/terms/>,
                     <http://rs.tdwg.org/ac/borrowed/>.

<http://rs.tdwg.org/ac/terms/>
     dcterms:title "Audubon Core Term List"@en;
     rdfs:label "Audubon Core Term List"@en;
     vann:preferredNamespacePrefix "ac";
     vann:preferredNamespaceUri "http://rs.tdwg.org/ac/terms/";
     dcterms:isPartOf <http://rs.tdwg.org/ac/>;
     a dcat:Dataset.
<http://rs.tdwg.org/ac/terms/metadataLanguage>
     rdfs:label "Metadata Language";
     rdfs:isDefinedBy <http://rs.tdwg.org/ac/terms/>;
     dcterms:isPartOf <http://rs.tdwg.org/ac/terms/>;
     a rdf:Property.
<http://rs.tdwg.org/ac/terms/caption>
     rdfs:label "Caption";
     rdfs:isDefinedBy <http://rs.tdwg.org/ac/terms/>;
     dcterms:isPartOf <http://rs.tdwg.org/ac/terms/>;
     a rdf:Property.
```

An example of metadata about a non-authoritative term list:

```
<http://rs.tdwg.org/ac/borrowed/>
     dcterms:title "Audubon Core Borrowed Terms"@en;
     rdfs:label "Audubon Core Borrowed Terms"@en;
     dcterms:isPartOf <http://rs.tdwg.org/ac/>;
     a dcat:Dataset.
<http://iptc.org/std/Iptc4xmpExt/2008-02-29/WorldRegion>
     rdfs:label "World Region";
     dcterms:isPartOf <http://rs.tdwg.org/ac/borrowed/>;
     a rdf:Property.
<http://purl.org/dc/terms/format>
     rdfs:label "Format";
     dcterms:isPartOf <http://rs.tdwg.org/ac/borrowed/>;
     a rdf:Property.

# IPTC terms have URIs that are not dereferenceable, so give some information about their namespace
<http://iptc.org/std/Iptc4xmpExt/2008-02-29/>
     vann:preferredNamespacePrefix "Iptc4xmpExt";
     vann:preferredNamespaceUri "http://iptc.org/std/Iptc4xmpExt/2008-02-29/".
```

An example showing how normative and non-normative term data are designated:

```
<http://rs.tdwg.org/cvterms/disposition/>
     dcterms:title "Term list for the dwc:disposition controlled vocabulary"@en;
     rdfs:label "Term list for the dwc:disposition controlled vocabulary"@en;
     rdfs:comment "For each term in this list, the controlled value (rdf:value), and definition (rdfs:comment) are normative.  Labels (rdfs:label) and comments (dcterms:description) are non-normative.";
     a dcat:Dataset.

<http://rs.tdwg.org/cvterms/disposition/inCollection>
     rdfs:label "In Collection"@en;
     rdfs:comment "The collection item is present in the collection."@en;
     skos:definition "The collection item is present in the collection."@en;
     rdf:value "in collection";
     dcterms:description "It is recommended that collection items that are on temporary loan continue to have a value of \"in collection\".";
     rdfs:isDefinedBy <http://rs.tdwg.org/cvterms/disposition/>;
     dcterms:isPartOf <http://rs.tdwg.org/cvterms/disposition/>;
     a skos:Concept.
```

An example showing how basic and extension term lists can be used to create several vocabularies with differing levels of semantics.  Note that the mechanism of ontology import requires that sets of axioms be contained in distinct documents [OWL-SYNTAX].

```
# Document 1:
<http://rs.tdwg.org/ac/>
     dcterms:title "Basic Audubon Core Vocabulary"@en;
     rdfs:label "Basic Audubon Core Vocabulary"@en;
     a dcmitype:Dataset;
     dcterms:hasPart <http://rs.tdwg.org/ac/terms/>,
                     <http://rs.tdwg.org/ac/borrowed/>.
# Note that these metadata about the Basic Vocabulary do not entail that it or its component term lists are ontologies.

# Document 2:
<http://rs.tdwg.org/ac-enhanced/>
     dcterms:title "Semantically Enhanced Audubon Core Vocabulary"@en;
     rdfs:label "Semantically Enhanced Audubon Core Vocabulary"@en;
     a dcmitype:Dataset,
       owl:Ontology;
     owl:imports <http://rs.tdwg.org/ac/terms/>,
                 <http://rs.tdwg.org/ac/borrowed/>,
                 <http://rs.tdwg.org/ac/enhanced/>;
     dcterms:hasPart <http://rs.tdwg.org/ac/terms/>,
                     <http://rs.tdwg.org/ac/borrowed/>,
                     <http://rs.tdwg.org/ac/enhanced/>.
# Note that use of owl:imports entails that the basic and borrowed term lists are ontologies, even though that is not asserted in the metadata for those term lists.

# Document 3:
<http://rs.tdwg.org/ac/enhanced/>
     dcterms:title "Audubon Core Axioms"@en;
     rdfs:label "Audubon Core Axioms"@en;
     a dcat:Dataset,
       owl:Ontology;
### Restriction: Metadata Language Required ###
ac:MediaResource a rdfs:Class;
                   rdfs:subClassOf
                            [ a owl:Restriction;
                              owl:minCardinality "1"^^xsd:nonNegativeInteger ;
                              owl:onProperty <http://rs.tdwg.org/ac/terms/metadataLanguage> ].
### Restriction: Metadata Language Not Repeatable ###
ac:MediaResource a rdfs:Class;
                   rdfs:subClassOf
                            [ a owl:Restriction;
                              owl:maxCardinality "1"^^xsd:nonNegativeInteger ;
                              owl:onProperty <http://rs.tdwg.org/ac/terms/metadataLanguage> ].

### Restriction: Format Not Repeatable ###
ac:MediaResource a rdfs:Class;
                   rdfs:subClassOf
                           [ a owl:Restriction;
                             owl:maxCardinality "1"^^xsd:nonNegativeInteger ;
                             owl:onProperty <http://purl.org/dc/terms/format> ].
```

**4.4.3 Linking to and describing distributions**

The guidelines expressed in the W3C Data Catalog Vocabulary [DCAT] should be followed for linking to and describing distributions of term lists.  Since term lists are typed as dcat:Dataset, they may be assigned any of the properties that are appropriate for instances of dcat:Dataset.  Term lists are linked to their distributions using the property dcat:distribution. Distributions may be assigned any properties that are appropriate for dcat:Distribution instances; however, at a minimum, they should have the properties dcterms:modified, dcat:accessURL or dcat:downloadURL (whichever is appropriate), and dcat:mediaType or dcterms:format.  If an IANA media type exists for the format of the distribution, dcat:mediaType should be used in preference over dcterms:format. [IANA]

**4.4.3.1 Example (non-normative)**

```
<http://rs.tdwg.org/dwc/terms/>
     dcterms:title "Core terms defined by Darwin Core"@en;
     rdfs:label "Core terms defined by Darwin Core"@en;
     dcterms:modified "2014-11-08"^^xsd:date;
     dcat:landingPage <http://rs.tdwg.org/dwc/terms/index.htm>;
     dcat:distribution <http://rs.tdwg.org/dwc/terms/index.htm>,
                       <http://tdwg.github.io/dwc/rdf/dwcterms.rdf>;
     a dcat:Dataset.
<http://rs.tdwg.org/dwc/terms/index.htm>
     dcterms:title "HTML distribution of the term list of core terms defined by Darwin Core"@en;
     rdfs:label "HTML distribution of the term list of core terms defined by Darwin Core"@en;
     dcterms:modified "2016-01-12"^^xsd:date;
     dcat:mediaType "text/html";
     dcat:downloadURL <https://raw.githubusercontent.com/tdwg/dwc/master/terms/index.htm>;
     a dcat:Distribution.
<http://tdwg.github.io/dwc/rdf/dwcterms.rdf>
     dcterms:title "RDF/XML distribution of the term list of core terms defined by Darwin Core"@en;
     rdfs:label "RDF/XML distribution of the term list of core terms defined by Darwin Core"@en;
     dcterms:modified "2015-07-03"^^xsd:date;
     dcat:mediaType "application/rdf+xml";
     dcat:downloadURL <https://raw.githubusercontent.com/tdwg/dwc/master/rdf/dwcterms.rdf>;
     a dcat:Distribution.
```

### **4.5 Metadata properties for describing vocabulary terms** ###

Because terms are resources, they are versioned and the terms used for relating current resources to versions (Section 4.3) apply to them as well.

The following properties are required for current terms and term versions. Note that the term or term version IRI will be present as the subject of the property

| **Human-readable label** | **Machine-readable property** | **Type of value** |
|--------------------------|-------------------------------|-------------------|
| Term name                | rdfs:label                    | Literal           |
| Definition               | rdfs:comment                  | Literal           |
| Type                     | rdf:type                      | IRI               |

Values for rdfs:label and rdfs:comment should be English language-tagged plain literals.  Values in other languages may be provided, but should be included in other ancillary documents that are associated with, but not included within the standard (see section 4.5.2).

Types should be rdf:Property for properties, rdfs:Class for classes, and skos:Concept for controlled values.

The property dcterms:description may optionally be used to provide additional information that is not part of the definition of the term.  

If the term was created or modified as the result of an Executive Committee decision, the property dwcattributes:decision should be used to link to the HTTP IRI representing the record of the decision affecting the term.

Properties that extend the meaning of terms by introducing machine-computable entailments should not be included with the basic properties listed in this section.  Rather they should be included in a vocabulary extension list as described in Section 4.4.2.2.

**4.5.1 Example metadata for terms (non-normative)**

The following example of terms in a metadata scheme is expressed in RDF/Turtle.  Note that it follows the pattern where the term list URI would dereference to a different document than the vocabulary URI.

```
<http://rs.tdwg.org/dwc/>
     dcterms:title "Basic Darwin Core Vocabulary"@en;
     rdfs:label "Basic Darwin Core Vocabulary"@en;
     a dcmitype:Dataset.

<http://rs.tdwg.org/dwc/terms/>
     dcterms:title "Core terms defined by Darwin Core"@en;
     rdfs:label "Core terms defined by Darwin Core"@en;
     vann:preferredNamespacePrefix "dwc";
     vann:preferredNamespaceUri "http://rs.tdwg.org/dwc/terms/";
     dcterms:isPartOf <http://rs.tdwg.org/dwc/>;
     a dcat:Dataset.

<http://rs.tdwg.org/dwc/terms/recordedBy>
     rdfs:label "Recorded By"@en;
     rdfs:comment "A list (concatenated and separated) of names of people, groups, or organizations responsible for recording the original Occurrence. The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first."@en;
     dcterms:description "The recommended best practice is to separate the values with a vertical bar (' | '). The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first. Examples: "José E. Crespo", "Oliver P. Pearson | Anita K. Pearson" where the value in recordNumber "OPP 7101" corresponds to the number for the specimen in the field catalog (collector number) of Oliver P. Pearson."@en;
     a rdfs:Property;
     dcterms:modified "2014-10-23"^^xsd:date;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/terms/history/#recordedBy-2014-10-23>;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/terms/history/#recordedBy-2009-04-24>;
     rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms/>;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/terms/>.

<http://rs.tdwg.org/dwc/terms/history/>
     dcterms:title "Darwin Core Terms Complete History"@en;
     a dcat:Dataset.

<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2014-10-23>
     rdfs:label "Recorded By"@en;
     rdfs:comment "A list (concatenated and separated) of names of people, groups, or organizations responsible for recording the original Occurrence. The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first."@en;
     dcterms:description "The recommended best practice is to separate the values with a vertical bar (' | '). The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first. Examples: "José E. Crespo", "Oliver P. Pearson | Anita K. Pearson" where the value in recordNumber "OPP 7101" corresponds to the number for the specimen in the field catalog (collector number) of Oliver P. Pearson."@en;
     a rdfs:Property;
     dcterms:issued "2014-10-23"^^xsd:date;
     dcterms:isVersionOf <http://rs.tdwg.org/dwc/terms/recordedBy>;
     dcterms:replaces <http://rs.tdwg.org/dwc/terms/history/#recordedBy-2009-04-24>;
     rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms/history/>;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/terms/history/>.

<http://rs.tdwg.org/dwc/terms/history/#recordedBy-2009-04-24>
     rdfs:label "Recorded By"@en;
     rdfs:comment "A list (concatenated and separated) of names of people, groups, or organizations responsible for recording the original Occurrence. The primary collector or observer, especially one who applies a personal identifier (recordNumber), should be listed first."@en;
     dcterms:description "Example: "Oliver P. Pearson; Anita K. Pearson" where the value in recordNumber "OPP 7101" corresponds to the number for the specimen in the field catalog (collector number) of Oliver P. Pearson."@en;
     a rdfs:Property;
     dcterms:issued "2009-04-24"^^xsd:date;
     dcterms:isVersionOf <http://rs.tdwg.org/dwc/terms/recordedBy>;
     dcterms:isReplacedBy <http://rs.tdwg.org/dwc/terms/history/#recordedBy-2014-10-23>;
     rdfs:isDefinedBy <http://rs.tdwg.org/dwc/terms/history/>;
     dcterms:isPartOf <http://rs.tdwg.org/dwc/terms/history/>.
```

**4.5.2. Labels in other languages**

In addition to following the generic practice of using rdfs:label to assign a name to the term (section 4.5), it may also desirable to use the specific SKOS properties skos:prefLabel and skos:altLabel to indicate the preferred and alternative labels for vocabulary terms in other languages.  However, assignment of such labels falls outside the TDWG Standards process, so these preferred and alternate labels should be include in ancillary documents associated with, but not included within the standard itself.

**4.5.3 Status of terms**

Current terms that are no longer valid should have the property owl:deprecated with a literal value of "true" datatyped as boolean.  Note that in this context, a "current" term does not necessarily mean that it is recommended or valid for use.  Rather, it means that the term IRI can be dereferenced by a client that wants to obtain information about it.  If a deprecated term has been replaced by another term, the property dcterms:isReplacedBy must be used to link the deprecated term to its replacement, and the term dcterms:replaces must be used to link the replacement to the deprecated term.

Term versions should have the property dwcattributes:status with possible values of "recommended" (for the most recent term version of a term that is currently valid), "superseded" (for term versions having more recent versions), or "deprecated" (for the most recent version of a term that is no longer valid).  As is the case for all described resources, previous and subsequent versions should be linked using dcterms:replaces and dcterms:isReplacedBy. This includes cases where the replacement for a version of a deprecated current term is a version of a current term with a different URI.

**4.5.3.1 Example metadata showing the status of terms (non-normative)**

This example illustrates the case where a term is replaced by another term with a different IRI.

```
dwc:individualID
     a rdf:Property;
     dcterms:description """Examples: \"U.amer. 44\", \"Smedley\", \"Orca J 23\""""@en;
     rdfs:comment "An identifier for an individual or named group of individual organisms represented in the Occurrence. Meant to accommodate resampling of the same individual or group for monitoring purposes. May be a global unique identifier or an identifier specific to a data set."@en;
     rdfs:label "Individual ID"@en;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/terms/individualID-2009-04-24>;
     dcterms:created "2009-04-24"^^xsd:date;
     dcterms:modified "2009-04-24"^^xsd:date;
     dwcattributes:decision "http://rs.tdwg.org/dwc/terms/history/decisions/#Decision-2014-10-26_14";
     owl:deprecated "true"^^xsd:boolean;
     dcterms:isReplacedBy dwc:organismID.

dwc:organismID
     a rdf:Property;
     rdfs:comment "An identifier for the Organism instance (as opposed to a particular digital record of the Organism). May be a globally unique identifier or an identifier specific to the data set."@en;
     rdfs:label "Organism ID"@en;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/terms/organismID-2014-10-23>;
     dcterms:created "2014-10-23"^^xsd:date;
     dcterms:modified "2014-10-23"^^xsd:date;
     dwcattributes:decision "http://rs.tdwg.org/dwc/terms/history/decisions/#Decision-2014-10-26_14";
     dcterms:replaces dwc:individualID.

<http://rs.tdwg.org/dwc/terms/individualID-2009-04-24>
     a rdf:Property;
     dcterms:isVersionOf dwc:individualID;
     dwcattributes:status "deprecated"^^xsd:string;
     dcterms:issued "2009-04-24"^^xsd:date;
     dcterms:description """Examples: \"U.amer. 44\", \"Smedley\", \"Orca J 23\""""@en;
     rdfs:comment "An identifier for an individual or named group of individual organisms represented in the Occurrence. Meant to accommodate resampling of the same individual or group for monitoring purposes. May be a global unique identifier or an identifier specific to a data set."@en;
     dcterms:isReplacedBy <http://rs.tdwg.org/dwc/terms/organismID-2014-10-23>.
<http://rs.tdwg.org/dwc/terms/organismID-2014-10-23>
     a rdf:Property;
     dcterms:isVersionOf dwc:organismID;
     dwcattributes:status "recommended"^^xsd:string;
     dcterms:issued "2014-10-23"^^xsd:date;
     rdfs:comment "An identifier for the Organism instance (as opposed to a particular digital record of the Organism). May be a globally unique identifier or an identifier specific to the data set."@en;
     dcterms:replaces <http://rs.tdwg.org/dwc/terms/individualID-2009-04-24>.
```

This example illustrates the case where a term version is superseded by a newer version of the term.

```
dwc:MaterialSample
     a rdfs:Class;
     rdfs:comment "A physical results of a sampling (or subsampling) event. In biological collections, the material sample is typically collected, and either preserved or destructively processed."@en;
     dcterms:description "Examples: A whole organism preserved in a collection. A part of an organism isolated for some purpose. A soil sample. A marine microbial sample."@en;
     rdfs:label "Material Sample"@en;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/terms/MaterialSample-2014-10-23>;
     dcterms:hasVersion <http://rs.tdwg.org/dwc/terms/MaterialSample-2013-03-28>;
     dcterms:created "2013-03-28"^^xsd:date;
     dcterms:modified "2014-10-23"^^xsd:date; # date of issue of most recent version
     dwcattributes:decision "http://rs.tdwg.org/dwc/terms/history/decisions/#Decision-2014-10-26_15".

<http://rs.tdwg.org/dwc/terms/MaterialSample-2013-03-28>
     a rdfs:Class;
     dcterms:isVersionOf dwc:MaterialSample;
     dwcattributes:status "superseded"^^xsd:string;
     dcterms:issued "2013-03-28"^^xsd:date;
     rdfs:comment "The category of information pertaining to the physical results of a sampling (or subsampling) event. In biological collections, the material sample is typically collected, and either preserved or destructively processed."@en;
     dcterms:isReplacedBy <http://rs.tdwg.org/dwc/terms/MaterialSample-2014-10-23>.
<http://rs.tdwg.org/dwc/terms/MaterialSample-2014-10-23>
     a rdfs:Class;
     dcterms:isVersionOf dwc:MaterialSample;
     dwcattributes:status "recommended"^^xsd:string;
     dcterms:issued "2014-10-23"^^xsd:date;
     rdfs:comment "A physical results of a sampling (or subsampling) event. In biological collections, the material sample is typically collected, and either preserved or destructively processed."@en;
     dcterms:description "Examples: A whole organism preserved in a collection. A part of an organism isolated for some purpose. A soil sample. A marine microbial sample."@en;
     dcterms:replaces <http://rs.tdwg.org/dwc/terms/MaterialSample-2013-03-28>.
```

**4.5.4 Metadata properties for describing controlled vocabulary terms**

Controlled vocabulary terms are instances of the class skos:Concept.  As such, it is appropriate to assign to such terms properties from the SKOS Simple Knowledge Organization System W3C Recommendation [SKOS] as necessary to define the relationships between that term and other resources.  (With the exception of skos:prefLabel and skos:altLabel, it is not generally appropriate to use SKOS vocabulary properties with terms from metadata schemes that are instances of the classes rdf:Property and rdfs:Class.)  Since it is a general practice to assign SKOS concepts to a concept scheme, controlled vocabulary terms should be linked to that scheme by skos:inScheme.  However, the structuring of such schemes is beyond the scope of this document.

To facilitate use by applications programmed to make use of SKOS properties, it is recommended that controlled vocabulary term descriptions include a skos:definition property that has the same value as the rdfs:comment property routinely used to indicate the human-readable definition for every TDWG vocabulary term.

As with all other TDWG vocabulary terms, controlled value terms will be assigned a term IRI.  That IRI may be used as the subject or object when expressing relationships with other resources.  However, in the context of information transfer, there may be cases where it is more desirable to represent the controlled vocabulary term by means of a unique text string.  To facilitate such use, each controlled vocabulary term should be assigned a string that is unique within that controlled vocabulary.  That string should be designated by making it a plan literal value (without language tag) of an rdf:value property of the term.  

**4.5.4.1 Example metadata for controlled vocabulary terms (non-normative)**

The following example of terms in a controlled vocabulary is expressed in RDF/Turtle.  Note that it follows the pattern where the term list URI dereferences to the same document as the vocabulary URI.  Also note that this example models the vocabulary as a skos:ConceptScheme.

```
<http://rs.tdwg.org/cvterms/disposition>
     dcterms:title "Controlled vocabulary for dwc:disposition"@en;
     rdfs:label "Controlled vocabulary for dwc:disposition"@en;
     a dcmitype:Dataset,
       skos:ConceptScheme.

<http://rs.tdwg.org/cvterms/disposition/>
     dcterms:title "Term list for the dwc:disposition controlled vocabulary"@en;
     rdfs:label "Term list for the dwc:disposition controlled vocabulary"@en;
     vann:preferredNamespacePrefix "dwcdisp";
     vann:preferredNamespaceUri "http://rs.tdwg.org/cvterms/disposition/";
     dcterms:isPartOf <http://rs.tdwg.org/cvterms/disposition>;
     a dcat:Dataset.

<http://rs.tdwg.org/cvterms/disposition/inCollection>
     rdfs:label "In Collection"@en;
     rdfs:comment "The collection item is present in the collection."@en;
     skos:definition "The collection item is present in the collection."@en;
     rdf:value "in collection";
     a skos:Concept;
     dcterms:created "2016-04-09"^^xsd:date;
     dcterms:modified "2016-04-09"^^xsd:date;
     skos:inScheme <http://rs.tdwg.org/cvterms/disposition>;
     dcterms:hasVersion <http://rs.tdwg.org/cvterms/disposition/inCollection-2016-04-09>;
     rdfs:isDefinedBy <http://rs.tdwg.org/cvterms/disposition/>;
     dcterms:isPartOf <http://rs.tdwg.org/cvterms/disposition/>.

<http://rs.tdwg.org/cvterms/disposition/destroyed>
     rdfs:label "Destroyed"@en;
     rdfs:comment "The collection item is no longer in the collection because it was destroyed."@en;
     skos:definition "The collection item is no longer in the collection because it was destroyed."@en;
     rdf:value "destroyed";
     a skos:Concept;
     dcterms:created "2016-04-09"^^xsd:date;
     dcterms:modified "2016-04-09"^^xsd:date;
     skos:inScheme <http://rs.tdwg.org/cvterms/disposition>;
     dcterms:hasVersion <http://rs.tdwg.org/cvterms/disposition/destroyed-2016-04-09>;
     rdfs:isDefinedBy <http://rs.tdwg.org/cvterms/disposition/>;
     dcterms:isPartOf <http://rs.tdwg.org/cvterms/disposition/>.

<http://rs.tdwg.org/cvterms/disposition/history/>
     dcterms:title "Version history for the dwc:disposition controlled vocabulary"@en;
     rdfs:label "Version history for the dwc:disposition controlled vocabulary"@en;
     a dcat:Dataset.

<http://rs.tdwg.org/cvterms/disposition/inCollection-2016-04-09>
     rdfs:label "In Collection"@en;
     rdfs:comment "The collection item is present in the collection."@en;
     skos:definition "The collection item is present in the collection."@en;
     rdf:value "in collection";
     a skos:Concept;
     dcterms:issued "2016-04-09"^^xsd:date;
     dcterms:isVersionOf <http://rs.tdwg.org/cvterms/disposition/inCollection>;
     rdfs:isDefinedBy <http://rs.tdwg.org/cvterms/disposition/history/>;
     dcterms:isPartOf <http://rs.tdwg.org/cvterms/disposition/history/>.

<http://rs.tdwg.org/cvterms/disposition/destroyed-2016-04-09>
     rdfs:label "Destroyed"@en;
     rdfs:comment "The collection item is no longer in the collection because it was destroyed."@en;
     skos:definition "The collection item is no longer in the collection because it was destroyed."@en;
     rdf:value "destroyed";
     a skos:Concept;
     dcterms:issued "2016-04-09"^^xsd:date;
     dcterms:isVersionOf <http://rs.tdwg.org/cvterms/disposition/destroyed>;
     rdfs:isDefinedBy <http://rs.tdwg.org/cvterms/disposition/history/>;
     dcterms:isPartOf <http://rs.tdwg.org/cvterms/disposition/history/>.
```

The following example illustrates the use of the controlled vocabulary terms from the previous example:

```
<http://arctos.database.museum/guid/MVZ:Mamm:115956#specimen> dwc:disposition "in collection".
<http://bioimages.vanderbilt.edu/vanderbilt/1-183> dwciri:disposition dwcdisp:destroyed.
```

## **5 Archiving of documents** ##

In order for a standard to enable compliance with a consensus community practice, a version of a standards document must be immutable and easily viewable by the public. This has several implications for the way in which documents are archived.

In order to ensure the stability of a human-readable document, it should be archived as a discrete file as opposed to being generated from a potentially changing database.  The archived document file must be in an open format for which parsers are commonly available. For this purpose an open format is defined as being one for which it would be possible to write a parser on the basis of a published specification without having to rely on code libraries for which the source code is not available or to pay a license fee.

In accordance with Section 2.1, the document may exist as files in a variety of formats that can be retrieved through content negotiation.  For example, a document may be available in any of HTML, PDF, and Markdown formats.  However, when rendered by a parser, each differently formatted file must render to a form that is substantively the same to a human reader.  At least one available form must be easily viewable to a human reader in a browser that requests text/html, regardless of whether the source file is actually in HTML format.

If a human-readable document is available in more than one format, the format that is delivered when that document's IRI is dereferenced requesting media type text/html will be considered to be the authoritative representation of the document.  The document in that format must be included in the archive for the standard. Other formats may be distributed by any mechanism, but in accordance with Section 3.2.3.1, those formats must include the "Latest version" IRI so that a reader can always retrieve the authoritative form of the document.  

If machine-readable documents are available in more than one serialization, they must all contain triples that would be interpreted as identical by a machine.  At least one of these serializations must be included in the archive for the standard.

Documents should be maintained as part of a publicly accessible version control system that ensures document files will not be lost and that previous document versions can be located and accessed through their immutable IRIs.  


## **6 References** ##

[COOL-URIS] http://www.w3.org/TR/cooluris/#cooluris Cool URIs for the Semantic Web

[DCAT] https://www.w3.org/TR/vocab-dcat/ Data Catalog Vocabulary (DCAT)

[GUID] http://www.tdwg.org/standards/150 TDWG GUID Applicability Statement

[HTTP-1.1] http://tools.ietf.org/html/rfc7231 Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content

[IANA] http://www.iana.org/assignments/media-types/media-types.xhtml Internet Assigned Numbers Authority (IANA) Media Types

[IRI] http://tools.ietf.org/html/rfc3987 Internationalized Resource Identifiers (IRIs)

[ISO-25964-2] ISO 25964-2. Information and documentation: Thesauri and interoperability with other vocabularis. Part 2: Interoperability with other vocabularies. 2013-03-15.

[NISO] http://www.niso.org/publications/press/UnderstandingMetadata.pdf Understanding Metadata. 2004. NISO Press.

[OWL-OVERVIEW] http://www.w3.org/TR/owl-overview OWL Web Ontology Language Document Overview (W3C Recommendation). World Wide Web Consortium.

[OWL-SYNTAX] http://www.w3.org/TR/owl-syntax OWL 2 Web Ontology Language
Structural Specification and Functional-Style Syntax (W3C Recommendation). World Wide Web Consortium.

[RECIPES] https://www.w3.org/TR/swbp-vocab-pub/ Best Practice Recipes for Publishing RDF Vocabularies. 2008.  W3C Working Group Note.

[RDF-PRIMER] http://www.w3.org/TR/rdf11-primer/ RDF 1.1 Primer

[REST] http://roy.gbiv.com/pubs/dissertation/rest_arch_style.htm Representational State Transfer (REST) from Architectural Styles and
the Design of Network-based Software Architectures

[SKOS] https://www.w3.org/TR/skos-reference/ SKOS Simple Knowledge Organization System
Reference

-----------------
This document is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/). ![http://creativecommons.org/licenses/by/4.0/](https://licensebuttons.net/l/by/4.0/88x31.png).

Copyright 201x - Biodiversity Information Standards - TDWG - [Contact Us](http://www.tdwg.org/about-tdwg/contact-us/)
