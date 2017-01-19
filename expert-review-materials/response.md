# Response to Expert Reviewer 1

## Standards Documentation Specification comments

[TODO: simplify examples]

**Status description in section 3.1.5**

The status is required metadata on the landing page for the standard, not on the particular descriptive documents included in the standard.  In the case of the Standards Documentation specification, the landing page would be loaded when dereferencing http://www.tdwg.org/standards/147, whereas the descriptive document (for example, the document currently under review) would be loaded when dereferencing the latest version of the document (in this example the placeholder URI: "http://something.tdwg.org/x").  The analog for Darwin Core would be http://www.tdwg.org/standards/450/ (landing page for standard) vs. http://rs.tdwg.org/dwc/terms/ (particular document). In the past, the distinction between these two entities has been fuzzy.  But since the documentation specification requires that each document be linked to the landing page, that landing page can serve as the single source informing users of the status of the standard as a whole.  In the future, landing pages should conform to this specification, but they don't at the moment.  


**use of dcat:Dataset (4.5.4.1, 4.4.2.3, 4.4.1.1)**

We brought this issue to the attention of the TDWG RDF Task Group for advice.  (See https://groups.google.com/forum/#!topic/tdwg-rdf/t7Gik4BxFes for the thread.)  Although the consensus was that it was probably technically OK to use dcat:Dataset as a type for term lists, there was a feeling among multiple members that it was not a good idea.  So we removed all references to dcat:Dataset, dcmitype:Dataset, the word "dataset", and the DCAT specification.  Instead, we minted the two classes tdwgutility:TermList  (http://rs.tdwg.org/dwc/terms/attributes/TermList) and tdwgutility:Vocabulary (http://rs.tdwg.org/dwc/terms/attributes/Vocabulary) to type term lists and vocabularies respectively.  See the change list for details.


**dc: vs. dcterms: (4.2.2)**

In creating the Darwin Core RDF Guide, one of the issues that was considered was how to handle cases where literals were being used to identify physical and conceptual entities that would better be identified in the object position of RDF triples using IRI references.  It was recognized that it would be a burden to require that the community immediately shift from using literals to IRIs, particularly in cases where no consensus IRIs had been minted for the object resources.  Thus, the Darwin Core RDF guide specified a dual system where objects of particular terms (those in the dwciri: namespace) should be used only with IRI- or blank node objects.  In cases where object resources were physical or conceptual entities best represented by IRIs, no assumptions were made about the objects of terms in the previously existing dwc: namespace; they were likely to be literals that were either names of those resources or literals whose values were the string representations of IRIs.  A burden would be placed on consuming applications to parse and undertake string matching with literal objects of dwc: terms, while a consuming application could simply "follow it's nose" to additional information linked to the node that was the object of a dwciri: term.  See Section 1.4.3 at http://rs.tdwg.org/dwc/terms/guides/rdf/index.htm#1.4_Use_of_terms_in_RDF

Audubon Core followed a similar strategy by defining two terms for properties that would best be identified by IRIs.  For example, ac:provider expects that a URI value will be provided, whereas ac:providerLiteral allows for the provider agent to be identified by a string that is the name of the provider.  (see https://terms.tdwg.org/wiki/Audubon_Core_Term_List#Literal-_vs._URI-valued_Terms)

In this spirit, for several Dublin Core terms, the Standards Documentation Specification differentiates between the variants of those terms in the dc: namespace (http://purl.org/dc/elements/1.1/) and the dcterms: namespace (http://purl.org/dc/terms/; called "dct:" by the reviewer).  It is common practice to use the dc: variants with names, while the dcterms: variants are expected to be used with non-literal values.  Thus, dc:contributor is recommended for use with a literal that is the name of an agent, while dcterms:contributor is recommended for use with an IRI representing the agent.  As the review manager notes, the FAQ at http://wiki.dublincore.org/index.php/FAQ/DC_and_DCTERMS_Namespaces notes that it is a good practice to use the dcterms: terms in a manner consistent with their ranges (i.e. as non-literal IRIs) whereas the dc:terms may be used in any way.  Since the dc: terms are widely used with string literals, the Documentation Specification specifies using them in that way.  

To clarify this point, the following text has been added to section 4.2 of the Documentation Specification:

"In accordance with the distinction made in the Dublin Core FAQ on DC and DCTERMS Namespaces [NAMESPACES] and following the precedent of Sections 1.4 and 3.3 of the Darwin Core RDF Guide [DWC-RDF], when a Dublin Core term has analogs in both the dc: (http://purl.org/dc/elements/1.1/) and dcterms: (http://purl.org/dc/terms/) namespaces, the dc: analog should be used with literal values (i.e. name strings), while the dcterms: analog should be used with an IRI or blank node denoting the object resource.  When an IRI is available to denote an object resource, it is desirable include the dcterms: analog in the metadata describing a resource. "

Added at end:

"[DWC-RDF] http://rs.tdwg.org/dwc/terms/guides/rdf/ TDWG Darwin Core RDF Guide.
[NAMESPACES] http://wiki.dublincore.org/index.php/FAQ/DC_and_DCTERMS_Namespaces FAQ/DC and DCTERMS Namespaces. Dublin Core Metadata Initiative."

The reviewer also questioned why we recommended using dc:creator with a literal but did not mention dcterms:creator.  Since the creator of the standards document is probably going to be the task group that created it, and since task groups are probably not going to have assigned IRIs, the specification did not prescribe that a dcterms:creator property be given.  That would not prevent the addition of this property if such an IRI existed.  Although not mentioned by the reviewer, the same would be true for the publisher value of the standard since the name "Biodiversity Information Standards (TDWG)" exists, but there is not currently any IRI denoting TDWG as an organization.


**owl:versionInfo (4.3.1)**

The specification distinguishes between an abstract resource and the versions of that resource.  In the example of section 4.3.1, the resource <http://rs.tdwg.org/dwc/terms/guides/text> is an abstract resource and therefore doesn't have versionInfo.  To discover the most recent version (and all versions), the dcterms:hasVersion link can be followed.  (see Fig. 5 for a graphical diagram of this relationship)


**example in section 4.4**

The example has been removed and replaced with a text description. Other examples of use are in subsequent sections.


**trailing slash 4.4.1.1**

The main point of section 4.4.1 was that if vocabulary and term list IRIs were designed so that they would dereference to the same document, they must be distinct from each other.  Although the examples given all had term list IRIs ending with slash, the specification does not make any particular recommendation about the form of the IRIs.  Nevertheless, for the sake of consistency, a slash was added to the example as suggested.


**4.4.2 (recommended namespace prefix)**

As noted by the review manager in his footnote, the suggestion is with regards to specifying a value for vann:preferredNamespacePrefix.  I've clarified the text accordingly.  As recommended, I removed the SKOS example, since the pattern described there is fairly well known.  


**4.4.2.3 (basic and enhanced vocabularies)**

I am not clear about the reviewer's objection to importing http://rs.tdwg.org/ac/enhanced/.  The IRI of the vocabulary is http://rs.tdwg.org/ac-enhanced/ (with a "-" after "ac"), while the IRI of the term list is http://rs.tdwg.org/ac/enhanced/ (with a "/" after "ac").  So the enhanced vocabulary (ontology) is importing a different entity.  

I followed Reviewer #1's suggestion for simplifying the example, but would note that the example that I gave was verbatim from the existing non-normative list at https://terms.tdwg.org/wiki/Audubon_Core_Term_List_RDF_Version


**4.5.4.1 regarding controlled values**

The recommendations of section 4.5.4.1 represent a somewhat hybrid approach on "controlled values".  Because TDWG vocabularies are widely used with text-based systems such as Simple Darwin Core (http://rs.tdwg.org/dwc/terms/simple/), many datasets will use particular recommended strings as "controlled values" to transmit the value of a property as part of the dataset.  It is therefore desirable in defining a controlled vocabulary to specify what specific string should be used by all users in this circumstance, regardless of their preferred language.  

This is a different situation from the approach taken by SKOS.  SKOS uses URIs rather than strings to designate particular controlled values.  Each controlled value URI may have multiple preferred labels, since one preferred label is allowed for each different language tag.  

Here is an example.  For the Darwin Core term dwc:country, the definition says "The name of the country or major administrative unit in which the Location occurs. Recommended best practice is to use a controlled vocabulary such as the Getty Thesaurus of Geographic Names."  The human-readable page in the Getty Thesaurus for China says that the preferred name is "Zhongguo".  Thus for text-based systems such as simple Darwin Core, conformant users should use the string "Zhongguo" in their spreadsheets or CSV documents.  For machine-readable data transmission, a URI value would be preferable and the URI tgn:1000111 (http://vocab.getty.edu/tgn/1000111) can be used.  However, the SKOS metadata for that term gives the following values for skos:prefLabel:

"China"@en
"China"@es
"Chine"@fr
"中国"@zh
"Китай"@ru
"اصًين"@ar
"Chung-hua"@zh-latn-wadegile

The value that a human spreadsheet user would use ("Zhongguo") is not one of the values since it is a transliteration of the Chinese.

Thus, although providing a URI removes ambiguity for machines, and providing various skos:prefLabel values can guide human users of different languages to the controlled value, SKOS itself does not provide a way to indicate in the machine-readable version of the vocabulary what string should be used in text-based systems.  We chose to co-opt the utility term rdf:value for the purpose of designating that string, which seems consistent with its definition, and with the way it has been used in the DCMI RDF recommendation (http://dublincore.org/documents/dc-rdf/).  

The dual dwc:/dwciri: namespace system described in the Darwin Core RDF Guide (section 2.5) makes it possible to translate text-based records directly into RDF by exposing the existing string values as literal values of the dwc: analog, whereas cleaned values, or values generated by human users selecting from a pick-list of skos:prefLabel labels can be exposed as RDF as URI values of the dwciri: analog.  In the China example, we would have these alternative ways to express the same controlled value:

:resource1 dwc:country "Zhongguo";
                  dwciri:country tgn:1000111.

The use of both dwc: and dwciri: terms was what was being illustrated in the last example of section 4.5.4.1.  I have added a reference to Section 2.5 of the RDF Guide after this example for clarification.

## Vocabulary Maintenance Specification comments

Two figures have been added as suggested by the reviewer.

**Use of RFC 2119 in the specification**

There was significant discussion within the task group about the circumstances under which it was appropriate to use RFC in TDWG standards documents.  The sentiment was expressed that RFC 2119 was appropriate within technical specifications in cases where it was necessary to indicate how a product could be judged to be conformant to the specification.  In other words, a product that failed to follow prescriptions expressed using the RFC 2119 keywords could be judged to be non-compliant with the specification.  The consequences of that non-compliance would be failure of the product to satisfy the use cases that the specification was designed to accomplish.  So for example, one of the goals of the Documentation Specification was to enable a machine client to discover all parts of a TDWG standard.  Keywords such as MUST, SHOULD etc. indicate that failure to comply could result in it being impossible for a client to achieve that or other goals of the specification.  

This use of words such as MUST and SHOULD as in RFC 2119 is somewhat different from the goal of what is essentially a best practice document like the Vocabulary Maintenance Specification.  If we say something like "the maintaining interest group must review all open issues at least once a year", that "must" does not indicate that failure to conform will prevent some product from working or achieving interoperability.  Rather it means that people will be annoyed, the Executive Committee might disband the group, etc.  

I went through both of the specifications to look for instances where my use of "should", "must", etc. actually indicated that compliance was necessary for a product to be conformant to the specification.  In those cases, I changed the words to all caps.  If not, then I tried to re-word to avoid using the keywords.  There were no cases in the Vocabulary Maintenance Specification where I thought that RFC 2119 keywords were appropriate, so I didn't use any.  

My choices were judgment calls, so it's quite possible that others might have done differently.  It would be helpful to call out particular places in the specifications where use of RFC 2119 keywords should (or should not) be in use.



# Response to Expert Reviewer 2 general comments

This reviewer noted that the maintenance system described in the Vocabulary Maintenance Specification may make it difficult to extend and manage vocabularies.  The reviewer also made reference to the RDA Standard as an exemplar for vocabulary management.  There are several points that can be made in response to these comments:

1. In contrast to some other organizations that might seek to develop and expand vocabularies rapidly, TDWG is a standards organization.  Thus TDWG vocabularies are not just vocabularies, but also international standards.  As such, long-term stability is desirable, and rapid change is not necessarily conducive to stability.  Also, the consensus-driven nature of TDWG makes change somewhat difficult.  Whether or not that is good or not, that is an essential feature of TDWG and can't really be changed without a significant change in the culture and rules of the organization.

2. Although it is true that the two specifications under review describe the use and modification of documents in the context of vocabulary management, they do not require any particular mechanism for generating those documents.  Thus human- and machine-readable documents describing vocabulary terms and lists could be hand-written and curated by people, but they also could be generated by software systems, SPARQL queries, or some other kind of automated system.  The specifications state that those documents should contain certain kinds of metadata, and that their versions should be stable and consistent among representations.  But the specification is largely silent about the technical details of the management of documents.  It is allowable and possible for the documents to be generated by some system that is more efficient than manual curation.  I believe that such a system (Semantic Mediawiki) is already in use for the management of Audubon Core documents.

3. The Task Group's charter charges it to produce a maintenance specification based on existing Darwin Core policy.  The Task Group also took into consideration existing precedents on how human-readable documents have been structured within the organization.  These considerations have shaped the documents under review.  It is possible that it would have been better to have created a system that diverges radically from current TDWG practice.  However, that was not what the Task Group was asked to do.

The Task Group has taken into consideration the comments of Reviewer 2 in revision of the drafts.  However, in the absence of concrete suggestions for changes, it has not made any modifications of the drafts to address the issues raised by Reviewer 2.
