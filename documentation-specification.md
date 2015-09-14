# TDWG Standards Documentation Specification #

TODO: 

- examine use of "must", "should", etc. throughout document and use consistently.

- decide on "human readable, machine readable" vs. "human-readable, machine-readable" and use consistently


**Title:** TDWG Standards Documentation Specification

**Date Issued:** 

**Date Modified:** 

**Contributors:** Steve Baskauf (TDWG Vocabulary Maintenance Task Group), Roger Hyam (TDWG Infrastructure Project)


**Abstract:** This document defines how TDWG standards should be presented. 

**Legal:** This document is governed by the standard legal, copyright, licensing provisions and disclaimers issued by the Taxonomic Databases Working Group.

**Part of TDWG Standard:**

Creator: TDWG Vocabulary Maintenance Specification Task Group

### Table of Contents ###

[generate when complete]

## **1 Introduction** ##

Standards adopted by Biodiversity Information Standards (TDWG) may include a number of components that are expressed in human- and machine-readable documents. It is important that users of a standard be able to locate all of these components. Users should be able to easily determine which parts of the standard are definitive (normative) and which are informative (non-normative). It should also be apparent which components are current and which are maintained for historical reasons or to support legacy applications. Machine-readable documents should be linked and described consistently to facilitate automated discovery and processing. This standard specifies how documents should be presented to achieve these requirements.

### **1.1 Definitions** ###

**resource** - Any kind of thing that can be identified. Resources can include documents, people, physical objects, and abstract concepts [RDF-PRIMER].

**document** - In this context, a document is a unit of information that can be stored or retrieved electronically as a single file.

**representation** - a view of a resource at a particular time. Representations can differ in language or format. [HTTP-1.1] 

**IRI** - Internationalized Resource Identifier. A superset of Uniform Resource Identifier (URI) that uniquely identifies a resource using characters from any character set. [IRI]

**HTTP IRI** - A subset of IRIs that enable retrieval of a representation using Hypertext Transfer Protocol (HTTP).  HTTP IRIs begin with "http://".

**dereference** - to use an IRI to obtain a representation of a resource through an Internet protocol such as HTTP

**content negotiation** - a mechanism by which a client and server determine the best representation to send to the client based on the client's expressed preferences [HTTP-1.1]

**current resource** - a resource as it exists in its current state.  The current state reflects the most recent version of the resource. 

**version** - a “snapshot” of a resource in time.  A version is created at a particular moment in time and documents the state of the resource until that version is replaced by a later version.  

**normative** - the prescriptive part of a standard that specifies that which is necessary to comply with the standard

**non-normative** - an informative part of a standard that provides supplemental information such as history, examples, and additional explanation beyond the information necessary to comply with the standard. 

**vocabulary** - a collection of standardized terms and their definitions.  Terms may represent classes, properties, or concepts.

**controlled vocabulary** - prescribed list of terms, each representing a concept. Controlled vocabularies are designed for applications in which it is useful to identify each concept with one consistent label. [ISO-25964-2]

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

A resource will normally be permanently identified by its abstract resource IRI.  When client that attempts to retrieve a representation of that resource by dereferencing its abstract IRI, it should be redirected through content negotiation to a URL that can be used to retrieve a representation of the content type or language requested by the client (Fig. 1).  A resource may be available as several content types, but all resources should be retrievable in a human-readable form when content-type text/html is requested.  It is also best practice to make a machine-readable representation available.  If the resource is a document that is primarily intended for human consumption, then the machine-readable representation should at a minimum contain descriptive metadata about the document. In some cases (such as vocabularies), the machine-readable representation of the resource will contain a complete description of the resource.  Although there are a number of possible machine-readable formats, by default each resource should be described using RDF in a serialization recommended by the TDWG Technical Architecture Group (TAG).

![](graphics/std-parts.png)

Fig. 2. A standard and its components.

### **2.2 Standards components hierarchy** ###

TDWG standards consist of several IRI-identified components.  This section describes these components and how they are related to each other.

**2.2.1 Standards landing page**

Each TDWG standard will be identified by an HTTP IRI (formerly known as the "permanent URL" of the standard) that represents the standard as an abstract entity.  When the standard's IRI is dereferenced by a client requesting content-type text/html (e.g. a Web browser), that IRI should redirect to a human-readable landing webpage that describes the status of the standard, contains an abstract of the standard, and which contains hyperlinks to the various components that comprise the standard.  When the standard's IRI is dereferenced by a client requesting RDF, the client should be redirected to a document that contains machine-readable RDF metadata about the standard.  That document should link the standard to its components using the property dcterms:hasPart (Fig. 2) as described in Section 3.2.

**2.2.2 Descriptive documents**

Each TDWG standard will have at least one human-readable document that describes the purpose of the standard and which contains information about how the standard is to be used.  This document should follow the formatting guidelines of Section 3.  When the IRI of the descriptive document is dereferenced by machine clients, the client should retrieve an RDF description of the document's metadata.  

![](graphics/vocabulary-documents.png)

Fig. 3. Relationship of a vocabulary to its component term list documents.

**2.2.3 Vocabulary documents**

TDWG vocabularies will be associated with an HTTP IRI that represents the vocabulary itself.  The vocabulary is distinct from the standard, since the vocabulary is just one part of the standard.  For this reason, the vocabulary IRI will not be the same as the IRI that identifies the standard.  When the vocabulary IRI is dereferenced by a client requesting content-type text/html, the client should obtain a web page that links to term list documents (Fig. 3).  Each term list document corresponds to a namespace that contains a set of terms.  There will be at least one document that lists and describes terms defined in a namespace controlled by TDWG.  The human-readable representation of this document will contain the normative definition of each term.  The machine-readable representation of this document will contain the minimal RDF metadata described in section 3.3.  There may also be documents that list terms in namespaces outside of the standard or terms that are not defined by TDWG.  Human-readable representations of these documents will contain links to the websites that define those terms.  Machine-readable representations of these documents will use the property dcterms:hasPart link to the machine-readable definitions of the external terms if those definitions exist.  

![](graphics/version-model.png)

Fig. 4. Relationship of a resource to its versions over time.

### **2.3 Versioning model** ###

Resources associated with TDWG standards may change over time.  TDWG uses a versioning model that relates the current resource and versions of the resource that have changed over time.  The purpose of the versioning model is to enable a user to start with the current resource or any version of the resource and trace the changes that have occurred to that resource over time.

**2.3.1 Current resources**

Each resource (document, vocabulary, term, etc.) exists in a current state.  That current state reflects the most recent version of that resource.  The current resource is identified by an IRI that does not change over time.  The current resource IRI can be used by humans or machines to retrieve a representation of the resource as it exists at the present time.  Because the current resource IRI does not change, it is stable and should be the IRI that is cited and is linked to whenever one wishes to refer to the resource in general.  

**2.3.2 Versions**

Each resource also exists as versions that document “snapshots” of the resource over time (Fig. 4).  A version is issued at a particular moment in time and documents the state of the resource until the version is replaced by a later version.  Each version of a resource is identified by an IRI that is distinct from the IRI of the current resource and from all other versions of that resource.  Typically, the IRI of a version is formed by appending the ISO 8601 creation date of the resource to the IRI if the abstract resource.  

A current resource is related to one of its versions by the property dcterms:hasVersion.  A version is related to its current resource by the property dcterms:isVersionOf, to a version that it supersedes by dcterms:replaces, and to a version that supersedes it by dcterms:isReplacedBy.  The metadata for a current resource should specify the IRI of the current resource, the IRI of the most recent version, and the IRI of any previous version that was superseded.  Metadata of a past version should specify that version's IRI, specify the IRI of the current resource, and link to any previous or subsequent versions.  

The versioning model is specific to neither humans nor machines, and either should be able to use the resource IRIs and properties to traverse the links from one version to another.  


## **3 Human readable documents** ##

In order for a standard to achieve its purpose, it must include documents that permit human users to understand what is necessary to comply with the requirements of the standard.  This section describes how human readable documents should be constructed to make this possible.

Determining what is necessary to comply with a standard is necessarily a human activity.  Therefore, the normative content of the standard should be contained exclusively in human readable documents.

### **3.1 Landing page for the standard** ###

When the HTTP IRI of a standard is dereferenced by a client requesting text/html (for example, when a human uses a Web browser), the client should receive a human-readable document that describes basic information about the standard as described in the subparts of this section.  

**3.1.1 Name of the standard**

The full name must be in English and
must be unique within the scope of TDWG standards, but otherwise is not
controlled and may contain any combination of characters.

**3.1.2 IRI of the standard**

The landing page should include the HTTP IRI that identifies the standard.  The text of the landing page should indicate that this is the IRI that should be cited and to which hyperlinks should be made.  This is important because content negotiation may redirect users to some other IRI that is specific to the delivery mechanism and which might be subject to change at some time in the future.

**3.1.4 Link to TDWG**

The landing page should make it clear that this is a TDWG standard and should provide a link to the TDWG home page.  

**3.1.5 Abstract**

An abstract should provide a brief description of the purpose of the standard.

**3.1.6 Preferred citation**

The landing page should indicate a preferred citation for the standard that includes at least the name of the standard and the IRI. The exact format and content of the citation is not specified by this standard.

**3.1.7 Links to parts of the standard**

Each part of the standard should be listed, with a hyperlink that leads to that part (Section 2.2).  The parts must include at least one descriptive document, whose form is described in section 3.2.

### **3.2 Descriptive documents** ###

A standard has one or more descriptive documents that describe the purpose of the standard and which contain information about how the standard is to be used. The choice of whether to place all of this material in a single document or to separate it into several documents should be made based on what will make the standard the most easy to understand and use.  

**3.2.1 Normative and non-normative sections of descriptive documents**

The normative and non-normative parts of standards should be clearly labeled as such.  If all of the content of a document is normative, this should be stated in the introduction to the document.  If a single document contains both normative and non-normative content, material in a single section should be of a single type.  The introduction should state that content is normative unless otherwise noted and headings should indicate if material in that section is non-normative. 

It is also permissible to indicate in the introduction that content of a particular type (e.g. examples or diagrams) is non-normative. 

**3.2.2 Versioning**

Descriptive documents are resources that follow the versioning model described in Section 2.3.  Thus each particular document version will represent the state of the generic document from the time it was issued until the time that version was superseded by a later version.  Thus, the date issued that is stated on a particular document version will reflect the date that particular version was issued (dcterms:issued).  Date created (dcterms:created) should be reserved to indicate the date that the first version of the document was issued.

**3.2.3 Layout and style**

Descriptive documents should be divided into three main sections:

-   A header section
-   Table of contents
-   A body section
-   A footer section

**3.2.3.1 Header Section**

The header section must contain the following parts:

**Title:** The title of the document.

**Date Issued:** The date of publication of this version in ISO 8601 Date format. 

**Part of TDWG Standard:** The IRI of the standard of which this document is part. The IRI should dereference to the standard's landing page.

**Latest version URI:** The current resource URI that will always return the latest version of the document.

**Previous version:** The URI of the previous version (if any). [should this be "Supersedes"?]

**Replaced by:** The URI of the next version (if any).  [should this be "Superseded by"?]

**Abstract:** A single paragraph summary of the document.

**Contributors:** A list of the people who are responsible for the
document's creation. The first person in the list should be the
principal contact.

Contributors’ names must be quoted in the following format: "FirstName
Initials LastName (Affiliation)" where:

Either one or both of FirstName and Initials must be present.

Affiliation is the organization or group the contributor is working with in relation to this document and is OPTIONAL.

Examples:

-   Roger D. Hyam (TDWG)
-   Roger Hyam (TDWG Infrastructure Project) 
-   R. Hyam 
   
**Document Status:** One of the status categories listed at [http://www.tdwg.org/standards/status-and-categories/](http://www.tdwg.org/standards/status-and-categories/).

**3.2.3.2 Table of Contents Section**

The table of contents section should contain an ordered list of all the headings (along with their numbers) that occur in the body section and
nothing else. The items in the list should be hypertext links to the headings in the body.

**3.2.3.3 Body Section**

[TODO: do we need to specify some features of existing standards documents, such as "Introduction", "Motivation", "Rationale", or do we leave this up to the authors?]

The body text should be divided by a hierarchy of subheadings. The subheadings must be numbered consecutively using simple decimal system.
The final number must not be followed by a decimal point. An example:

1 First Main Section

1.1 First subsection within first main section.

1.12.5 The fifth sub-subsection within the twelfth subsection of the first section.

2 Second Main Section

**3.2.3.4 Footer section**

The footer should contain a copyright statement and licensing information.  Typically, the copyright is held by TDWG and the license is [Creative Commons Attribution](http://creativecommons.org/licenses/by/4.0/) (CC BY).

[This used to say: "A reference or link to a document containing the Copyright, Licensing and Disclaimer statements that govern this document. This will usually be the standard one supplied by TDWG."  This has been included in some standards documents, but not consistently.]

**3.2.4 Language**

All normative content must be in English. Translations of normative documents may be included in the standard but the translations must be treated as informative documents. [This was copied from the earlier specification.  Do we really want to say that translations may be "included in the standard"?  That would imply that creating additional translations would require amending the standard.  Is that what we really want???]

**3.3 Archiving of documents**

In order for a standard to enable compliance with a consensus community practice, a version of a standards document must be immutable and easily viewable by the public. This has several implications for the way in which documents are archived.

In order to ensure the stability of a human readable document, it should be archived as a discrete file as opposed to being generated from a potentially changing database.  The archived document file must be in an open format for which parsers are commonly available. For this purpose an open format is defined as being one for which it would be possible to write a parser on the basis of a published specification without having to rely on code libraries for which the source code is not available or to pay a license fee. 

In accordance with Section 2.1, the document may exist as files in a variety of formats that can be retrieved through content negotiation.  For example, a document may be available in any of HTML, PDF, and MarkDown formats.  However, when rendered by a parser, each differently formatted file must render to a form that is substantively the same to a human reader.  At least one available form must be easily viewable to a human reader in a browser that requests text/html, regardless of whether the source file is actually in HTML format.

Documents should be maintained as part of a publicly accessible version control system that ensures document files will not be lost and that previous document versions can be located and accessed through their immutable IRIs.  

### **3.3 Vocabulary descriptions** ###

Vocabulary description is a special category of human-readable documents.  As such, vocabulary descriptions will comply with the previous parts of Section 3.  However, they will also contain additional information as described in the following sections.

**3.3.1 Terms as versioned resources**

A term is a resource that persists over time (Fig. 4) and complies with Section 2.3 of this standard. The current state of the term is represented by the term IRI, which does not change and which can be dereferenced to discover the current term definition.  

The state of the term at particular times is recorded via versions of the term.  A new version of the term is issued on a particular date and the term version IRI should be dereferenceable to discover the definition of the term version when it was issued.  

**3.3.2 Term list**

The body section of a vocabulary description will contain a series of term entries that can be easily read and understood by humans.  Each term entry may include the following items.

**Term name** - The term name is a human readable controlled value that represents the class, property, or concept described by the term definition.  The term name is usually related to the meaning of the term, but users must not attempt to understand the meaning of the term by interpreting its name.  Rather, the term definition should be consulted.  If the term is imported from another vocabulary rather than defined by the parent standard, the term name should include a namespace abbreviation (QName) that is defined in the introduction of the vocabulary description.  

**Term IRI** - The HTTP IRI that uniquely identifies the current term

**Term version IRI** - The HTTP IRI that identifies the version of the term that is currently in force.

**Modified** - The date in ISO 8601 Date format on which the most recent version of the term was issued. 

**Definition** - The normative definition of the term, written in English.  The definition should include precisely the wording required to describe the class, property, or concept.  Additional informative content should be presented in comments or notes.

The term list may contain other properties of the term that are deemed to be useful, including informative comments or notes that provide examples or clarification, but which do not form part of the normative definition of the term.

[I have not yet described a term **version** list, i.e. the historical record of all versions of terms that corresponds to [http://rs.tdwg.org/dwc/terms/history/index.htm](http://rs.tdwg.org/dwc/terms/history/index.htm).  This still needs to be done.]

-----------------
Material below this point has not yet been revised.

4 machine readable documents
4.1 descriptive metadata
4.2 links between documents
4.3 vocabularies


-----------------------

**4 Contents of Standards**

[evaluate]
At a minimum, each standard must contain:

-   the normative (prescriptive) form of the standard itself (e.g., an
    XML Schema or human readable text); and
-   a 'Cover Page' document that summarizes the content of the standard [what does this mean in the current context of GitHub, the TDWG website, etc.?]
    (see below).

A standard should also contain information on:

-   the 'Motivation' for the existence of the standard; and
-   the 'Rationale' for why the standard takes the form it does.

Standards may contain any number of files provided they are of an
appropriate format (see below).

**5 Packaging of Standards**

[evaluate this.  How does this concept of the standard as a "bundle" fit in with our experience in trying to "package up" frozen versions of Darwin Core and Audubon Core that actually "live" as web or wiki pages? This probably needs to be re-thought in the context of version control and GitHub repos.  Maybe it makes more sense to consider a packaged standard as a frozen release in some version control system.]

Standards take the form of a logical folder or directory, but may be
distributed as a zip or tar archive file. The name of the archive must
be the file name of the standard followed by a period and the
appropriate suffix if the standard is compressed.

**6 Naming of Standards**


Every standard must have two names, a full name and a file name.

The **full name** is used in the cover page and as the title of the main
document if it is human readable. The full name must be in English and
must be unique within the scope of TDWG standards, but otherwise is not
controlled and may contain any combination of characters.

[This does not seem to have been followed at all. The OJS system assigns numbers that seem entirely meaningless, so when the archived packages are downloaded there is no relationship between the file names and the standard names.]
The **file name** should be created as a shortened version of the full
name and is used for the logical folder or directory and any
distribution archive. Rules for constructing file names are given below.
The file name must also be unique among TDWG standards.

**7 File Naming**


The following rules govern file names used in standards and for
standards archives:

-   File names must start with ‘tdwg\_’ followed by a shortened version of the full name of the standard.
-   File names must consist of only lowercase letters, numbers, underscores and hyphens.
-   File names must not contain spaces (replace with underscore).
-   File names must not contain non ASCII characters.
-   File names must not contain periods other than the one used to separate the suffix.
-   Suffix should be the commonly used suffix for file type and the three letter version where possible; for example, jpg rather than jpeg and xsl rather than xslt. [Does this really matter? I thought .html was actually preferred over .htm now.]






**10 Referencing of Standards**

[This needs to be re-written in light of the hierarchy model. Replace use of URI with IRI.]
Each standard must have the following URIs (Uniform Resource
Identifiers)

-   A URI for the standard itself. This must resolve to human readable
    rendering of the information in the standard's cover page.
-   A URI that resolves to an archive file containing all the files in
    the standard. [I don't think this should be a requirement.  Let the cover page contain a link to the archive file, whose URL may change.]
-   A URI for each of the files within the standard. [Currently this is not followed - some files are only obtainable in the zip that's downloaded.]

The URIs are issued as part of the standards process by the
administrator of the standards repository and remain constant from the
point at which they are issued.

Some standards may involve technologies that make use of XML namespaces.
The URIs of the standard and its constituent parts should not be used
for this purpose. TDWG provides a facility for reserving URIs associated
with namespaces with the base namespace http://rs.tdwg.org/.  [what is the significance of this in the current landscape?]

**11 Human Readable Documents**




**12.2 Key Words Governing Compliance**

[we need to spell out the circumstances under which RFC 2119 keywords are appropriate]
This policy is specified in RFC 2119 (http://www.ietf.org/rfc/rfc2119.txt).

**13 Cover Page Contents**


This section specifies content for the Cover Page documents that must be
contained in all TDWG standards. The table below shows the components
that must be contained in the cover page of all TDWG standards. These
are based on a subset of the Dublin Core metadata initiative elements
and terms.

Table 2: Fields for Cover Page documents.


|**Name**      |           **Notes**|
|---------------|----------------|
| Title                   | **Required** The official TDWG title for the standard (see above)|
| Description      |        **Required** A brief (&lt;=250 words) description of the standard|
| Subject             |     **Required** Key words, key phrases and classification codes that describe the topic covered by the standard.|
| Creator           |       **Required** The primary author of the standard following the conventions outlined above. Should only occur once.|
| Contributor      |        A contributor to the standard following the conventions outlined above. This assertion may be repeated.|
|  Date Modified    |        The date the standard was last modified. Will be prior to Date Accepted if that is present.|
|  Date Accepted       |     **Required for accepted standards** The date the standard was officially ratified by TDWG and fixed. If a modified date is present it must be prior to this date.|
|  Identifier      |         The GUID of the standard.|
|  Publisher            |    **Required** Should always contain the text "Biodiversity Information Standards TDWG."|
|  Rights          |         **Required** One or more URLs linking to documents describing the copyright, licensing provisions and disclaimers associated with the standard. Typically this will be contained within another TDWG standard. (see Legal Statements below)|
|  Access Rights        |    **Required** Should always contain the single word 'public'. All TDWG standards should be freely accessible to all via the Internet.|
| Bibliographic Citation  | **Required** How this standard should be cited.|
|  Has Part           |      **Required** The full URL to a file within the standard. This assertion should be repeated for each file within the standard (other than cover.xml itself).|
| Replaced By             | **Required if this standard has been replaced by another.** If the standard has been replaced then this assertion should be present and contain the full URL to the new standard.|
| Replaces          |       **Required if this standard replaces another.** If this standard replaces a previous one then this assertion should be present and contain the full URI of the standard replaced.|


**14 Legal Statements**


TDWG standards must contain explicit statements of copyright (the
assertion of intellectual property rights), the licensing provisions for
the standard, and a disclaimer of liability. This section defines the
texts that should be included in TDWG standards and actions that should
be taken if these texts are deemed not to be suitable for a particular
standard.

**14.1 Copyright**

The usual practice will be for participants in TDWG activities to
contribute their intellectual works to TDWG freely, and to combine them
with the contributions of others to create a TDWG standard. TDWG
strongly recommends that TDWG standards be placed under TDWG copyright.

The following copyright notice should be included in all TDWG documents

Copyright © TDWG *(year)*. All Rights Reserved.

**14.2 Licensing Provisions**

TDWG intends its standards to be used as broadly as possible and should
impose no royalties or licensing fees for their use. TDWG will normally
publish its standards under the Creative Commons Attribution (CC BY)
license. Under this license users may copy, completely or in part, or
create derivative works for any purpose, whether commercial or public
benefit, subject only to the requirement that the original standard must
be cited.



**14.3 Disclaimer**

The following text must be included or referenced in all TDWG standards
documents:

Disclaimer: This document and the information contained herein are
provided on an "AS IS" basis. TDWG MAKES NO WARRANTIES REGARDING THE
INFORMATION PROVIDED, AND DISCLAIMS LIABILITY FOR DAMAGES RESULTING FROM
ITS USE.



**14.5 Departure from Usual Practice**

If the participants in a TDWG activity intend to depart from the legal
framework provided above, the alternative statements of intellectual
property rights and licensing must be described fully in the charter of
that activity as well as the standard itself. [should this be here?]

[Somewhere here we should specify the preferred citation  format for the document.]

**X. References**

[COOL-URIS] http://www.w3.org/TR/cooluris/#cooluris Cool URIs for the Semantic Web

[HTTP-1.1] http://tools.ietf.org/html/rfc7231 Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content

[IRI] http://tools.ietf.org/html/rfc3987 Internationalized Resource Identifiers (IRIs)

[ISO-25964-2] ISO 25964-2. Information and documentation: Thesauri and interoperability with other vocabularis. Part 2: Interoperability with other vocabularies. 2013-03-15.

[RDF-PRIMER] http://www.w3.org/TR/rdf11-primer/ RDF 1.1 Primer

[REST] http://roy.gbiv.com/pubs/dissertation/rest_arch_style.htm Representational State Transfer (REST) from Architectural Styles and
the Design of Network-based Software Architectures
